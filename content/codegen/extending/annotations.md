+++
weight = 4
draft = false
highlight_code = true
title = "Annotations"

[menu.main]
  Name = "Using Annotations"
  parent = "codegen-extending"
+++

With Dogma Source Analyzer code annotations can be instantiated to provide
metadata for the code generation process. This done through a combination of
the `analyzer` library and `dart:mirrors`. The analyzer will get the
information on the object and then mirrors are used to instantiate the object
so it can be interacted with.

# Creating an Annotation

The `dogma_source_analyzer` provides a simple mechanism to instantiate user
defined annotations. The amount of work required by the user depends on how the
annotation is structured.

Annotations should adhere to the following guidelines whenever possible.

* Use `this.value` in the constructor whenever possible.
* Do not import `dart:html` or any other library that requires a browser.

Both of these recommendations can be worked around but require more work by the
user.

A simple example of an annotation that uses these guidelines follows.

```dart
class MyAnnotation {
  String value;
  
  const MyAnnotation(this.value);
}
```

# Instantiating the Annotation

The `dogma_source_analyzer.analyzer` library contains a helper function which
will create the annotation when its encountered. To create the `MyAnnotation`
instances the following function is used.

```dart
var generator = analyzeAnnotation('MyAnnotation');
```

This creates a function of type `AnalyzeAnnotation` that can be passed into the
`libraryMetadata` function used to retrieve `LibraryMetadata` from a library.

```dart
var library = libraryMetadata(
    join('path/to/lib.dart'),
    analysisContext(),
    annotationCreators: [generator]
);
```

If any `MyAnnotation` values are encountered within the library they will be
properly instantiated and can be used directly within the codegen process. The
annotations can be contained on any dart construct that can contain metadata.

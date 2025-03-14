## Stateless Widgets
In FLutter, widgets are the building blocks of the UI. They can be categorized into two types: Stateless Widgets and <a href="https://github.com/PranavBawgikar/dart-notes/edit/main/stateful-widgets.md">Stateful Widgets</a>. Stateless Widgets are immutable, meaning their properties can't change once they're built. They can be used when the UI doesn't need to update dynamically. Stateless widgets (`StatelessWidget`) are those type of widgets where the state once created cannot be changed. That is, it can run only once which is when the app is loaded. Examples include text, icon and image.

Example 1:
```dart
import 'package:flutter/material.dart';

class MyStatelessWidget extends StatelessWidget {
  const MyStatelessWidget({super.key});

  @override
  Widget build(BuildContext context) {
    return const Scaffold(
      body: Center(
        child: Text('Hello World!');
      ), // Center
    ); // Scaffold
  }
}
```
So, whenever `MyStatelessWidget` is instantiated it will call the build function and draw that one widget on the screen.

Example 2:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomeScreen(),
    );
  }
}

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold (
      appBar: AppBar(
        title: Text('Demo'),
      ),
      body: const Center(
          child: Text('Hello World!'),
      ), // Center
    ); // Scaffold
  }
}
```
Certain widgets like `Text`, require a `Directionality` widget to determine the text's reading direction. In Flutter, the `Directionality` widget is typically provided by higher-level widgets such as `MaterialApp` or `WidgetsApp`. If you directly run `HomeScreen` without wrapping it in a `MaterialApp` it will lead to an error: `No directionality widget found`. Always use `MaterialApp` or `WidgetsApp` at the root level of your tree hierarchy.

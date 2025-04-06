import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: ColorBlocksScreen(),
    );
  }
}

class ColorBlocksScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Column(
        children: [
          // Top half
          Expanded(
            flex: 1,
            child: Row(
              children: [
                // Red block
                Expanded(
                  flex: 2,
                  child: Container(color: Colors.red),
                ),
                // Right side blocks
                Expanded(
                  flex: 2,
                  child: Column(
                    children: [
                      // Blue block
                      Expanded(
                        flex: 1,
                        child: Container(color: Colors.blue),
                      ),
                      // Black and Orange row
                      Expanded(
                        flex: 1,
                        child: Row(
                          children: [
                            Expanded(
                              flex: 1,
                              child: Container(color: Colors.black),
                            ),
                            Expanded(
                              flex: 1,
                              child: Container(color: Colors.orange),
                            ),
                          ],
                        ),
                      ),
                    ],
                  ),
                ),
              ],
            ),
          ),
          // Bottom half (Yellow block)
          Expanded(
            flex: 1,
            child: Container(color: Colors.yellow),
          ),
        ],
      ),
    );
  }
}
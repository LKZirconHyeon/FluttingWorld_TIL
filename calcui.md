import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: AndroidCalculatorUI(),
      debugShowCheckedModeBanner: false,
    );
  }
}

class AndroidCalculatorUI extends StatelessWidget {
  final List<String> buttons = [
    'C', '()', '%', '÷',
    '7', '8', '9', '×',
    '4', '5', '6', '-',
    '1', '2', '3', '+',
    '+/-', '0', '.', '=',
  ];

  Color getButtonColor(String text) {
    if (text == 'C') return Colors.red;
    if (text == '=' || text == '+' || text == '-' || text == '×' || text == '÷' || text == '%' || text == '()') {
      return Colors.green;
    }
    return Colors.black87;
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.white,
      body: SafeArea(
        child: Column(
          children: [
            // Display section (you can style it further if needed)
            Expanded(
              flex: 2,
              child: Container(
                alignment: Alignment.bottomRight,
                padding: EdgeInsets.symmetric(horizontal: 24, vertical: 16),
                child: Text(
                  '0',
                  style: TextStyle(
                    fontSize: 60,
                    color: Colors.black,
                  ),
                ),
              ),
            ),

            // Buttons
            Expanded(
              flex: 5,
              child: GridView.builder(
                padding: EdgeInsets.all(16),
                itemCount: buttons.length,
                gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                  crossAxisCount: 4,
                  mainAxisSpacing: 12,
                  crossAxisSpacing: 12,
                ),
                itemBuilder: (context, index) {
                  final text = buttons[index];
                  final isEqual = text == "=";

                  return Container(
                    decoration: BoxDecoration(
                      color: Colors.grey[200],
                      shape: BoxShape.circle,
                    ),
                    child: Center(
                      child: Text(
                        text,
                        style: TextStyle(
                          fontSize: 26,
                          color: getButtonColor(text),
                          fontWeight: FontWeight.bold,
                        ),
                      ),
                    ),
                  );
                },
              ),
            ),
          ],
        ),
      ),
    );
  }
}

import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: FirstPage(),
      // We do not need `routes:` here for pages with arguments
    );
  }
}

class Person {
  String name;
  int age;

  Person(this.name, this.age);
}

// --------- FirstPage (Stateless) ---------
class FirstPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    print('FirstPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text('First (Stateless)'),
      ),
      body: ElevatedButton(
        child: Text('다음 페이지로 (Stateful)'),
        onPressed: () {
          final person = Person('홍길동', 20);
          Navigator.push(
            context,
            MaterialPageRoute(
              builder: (context) => SecondStatefulPage(person: person),
            ),
          );
        },
      ),
    );
  }
}

// --------- SecondPage (Stateless) ---------
class SecondPage extends StatelessWidget {
  final Person person;

  const SecondPage({required this.person, Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    print('SecondPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text('Second (Stateless)'),
      ),
      body: ElevatedButton(
        child: Text('이전 페이지로'),
        onPressed: () {
          Navigator.pop(context);
        },
      ),
    );
  }
}

// --------- FirstPage (Stateful) ---------
class FirstStatefulPage extends StatefulWidget {
  const FirstStatefulPage({Key? key}) : super(key: key);

  @override
  _FirstStatefulPageState createState() => _FirstStatefulPageState();
}

class _FirstStatefulPageState extends State<FirstStatefulPage> {

  @override
  void initState() {
    super.initState();
    print('FirstStatefulPage: initState() called');
    // Initialization code here
  }

  @override
  void dispose() {
    print('FirstStatefulPage: dispose() called');
    // Clean-up code here
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    print('FirstStatefulPage: build() called');
    return Scaffold(
      appBar: AppBar(
        title: Text('First (Stateful)'),
      ),
      body: ElevatedButton(
        child: Text('다음 페이지로'),
        onPressed: () {
          final person = Person('홍길동', 20);
          Navigator.push(
            context,
            MaterialPageRoute(
              builder: (context) => SecondStatefulPage(person: person),
            ),
          );
        },
      ),
    );
  }
}


// --------- SecondPage (Stateful) ---------
class SecondStatefulPage extends StatefulWidget {
  final Person person;

  const SecondStatefulPage({Key? key, required this.person}) : super(key: key);

  @override
  _SecondStatefulPageState createState() => _SecondStatefulPageState();
}

class _SecondStatefulPageState extends State<SecondStatefulPage> {
  @override
  Widget build(BuildContext context) {
    print('SecondStatefulPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.person.name),
      ),
      body: ElevatedButton(
        child: Text('이전 페이지로'),
        onPressed: () {
          Navigator.pop(context);
        },
      ),
    );
  }
}

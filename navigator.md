import 'package:flutter/cupertino.dart';
import 'package:flutter/material.dart';

void main() => runApp(MaterialApp(home: FirstStatefulPage()));

class FirstPage extends StatelessWidget{
  @override
  Widget build(BuildContext context){
    print('FirstPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text('Second'),
      ),
      body: ElevatedButton(
        child: Text('이전 페이지로'),
        onPressed: (){
          Navigator.pop(context);
        },
      ),
    );
  }
}

class SecondPage extends StatelessWidget{
  @override
  Widget build(BuildContext context){
    print('SecondPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text('Second'),
      ),
      body: ElevatedButton(
        child: Text('이전 페이지로'),
        onPressed: (){
          Navigator.pop(context);
        },
      ),
    );
  }
}

class FirstStatefulPage extends StatefulWidget {
  @override
  _FirstStatefulPageState createState() => _FirstStatefulPageState();
}

class _FirstStatefulPageState extends State<FirstStatefulPage>{
  @override
  void initState(){
    super.initState();
    print('FirstPage initState()');
  }

  @override
  void dispose(){
    super.dispose();
    print('FirstPage dispose()');
  }

  Widget build(BuildContext context){
    print('FirstPage build()');
    return Scaffold(
      appBar: AppBar(
        title: Text('First'),
      ),
      body: ElevatedButton(
        child: Text('다음 페이지로'),
        onPressed: () {
          final person = Person('Second', 20);
          Navigator.push(
            context,
            MaterialPageRoute(builder: (context) => SecondStatefulPage(person: person)),
          );
        },
      ),
    );
  }
}

class Person {
  final String name;
  final int age;

  Person(this.name, this.age);
}

class SecondStatefulPage extends StatefulWidget{
  final Person person;

  SecondStatefulPage({super.key, required this.person});

  @override
  _SecondStatefulPageState createState() => _SecondStatefulPageState();
}

class _SecondStatefulPageState extends State<SecondStatefulPage> {

  @override
  void initState(){
    super.initState();
    print('SecondPage initState()');
  }

  @override
  void dispose(){
    super.dispose();
    print('SecondPage dispose()');
  }

  @override
  Widget build(BuildContext context) {
    print('SecondPage build()');
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
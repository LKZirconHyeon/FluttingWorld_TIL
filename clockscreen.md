import 'package:flutter/material.dart';
import 'dart:async';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: ClockHomePage(),
    );
  }
}

class ClockHomePage extends StatefulWidget {
  @override
  _ClockHomePageState createState() => _ClockHomePageState();
}

class _ClockHomePageState extends State<ClockHomePage> {
  late String _currentTime;
  late Timer _timer;

  @override
  void initState() {
    super.initState();
    _updateTime();
    _timer = Timer.periodic(Duration(seconds: 1), (Timer t) => _updateTime());
  }

  void _updateTime() {
    final now = DateTime.now();
    setState(() {
      _currentTime = "${_twoDigits(now.hour)}:${_twoDigits(now.minute)}:${_twoDigits(now.second)}";
    });
  }

  String _twoDigits(int n) => n.toString().padLeft(2, '0');

  @override
  void dispose() {
    _timer.cancel();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('현재 시각'),
        backgroundColor: Colors.blue,
      ),
      body: Center(
        child: Text(
          _currentTime,
          style: TextStyle(fontSize: 30),
        ),
      ),
    );
  }
}
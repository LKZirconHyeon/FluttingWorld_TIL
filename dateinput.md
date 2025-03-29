import 'dart:io';
import 'package:intl/intl.dart';
import 'package:intl/date_symbol_data_local.dart';

Future<void> main() async {
  await initializeDateFormatting('ko-KR');

  stdout.write('날짜를 입력하세요 (예: 1970/01/01): ');
  String? input = stdin.readLineSync();

  if (input == null || input.length < 10) {
    print("입력 형식이 잘못되었습니다.");
    return;
  }

  var inputYear = int.parse(input.substring(0, 4));
  var inputMonth = int.parse(input.substring(5, 7));
  var inputDay = int.parse(input.substring(8, 10));

  DateTime result = DateTime(inputYear, inputMonth, inputDay);
  String formattedDate = DateFormat.yMMMMd('ko-KR').format(result);
  String weekday = DateFormat.EEEE('ko-KR').format(result);

  print('$formattedDate ($weekday)');
}
# 별사탕 도형 만들기 프로그램
==============================
## Full Square (꽉 찬 사각형)
var result = '';
void main() {
  var n = 10;
  
  for (var i = 0; i < n; i++){
    for (var j = 0; j < n; j++){
        result += '*';
    }
    result += '\n';
  }
  print(result);
}

## Hollow Square (테두리 사각형)
var result = '';
void main() {
  var n = 10;
  
  for (var i = 0; i < n; i++){
    for (var j = 0; j < n; j++){
      if (i == 0 || i == (n-1) || j == 0 || j == (n-1)){
        result += '*';
      }else{
        result += ' ';
      }
    }
    result += '\n';
  }
  print(result);
}

## Left Diagonal Square (왼쪽 대각선 사각형)
var result = '';
void main() {
  var n = 10;
  
  for (var i = 0; i < n; i++){
    for (var j = 0; j < n; j++){
      if (i == 0 || i == (n-1) || j == 0 || j == (n-1) || (i == j)){
        result += '*';
      }else{
        result += ' ';
      }
    }
    result += '\n';
  }
  print(result);
}

## Right Diagonal Square (오른쪽 대각선 사각형)
var result = '';
void main() {
  var n = 10;
  
  for (var i = 0; i < n; i++){
    for (var j = 0; j < n; j++){
      if (i == 0 || i == (n-1) || j == 0 || j == (n-1) || (i + j == n - 1)){
        result += '*';
      }else{
        result += ' ';
      }
    }
    result += '\n';
  }
  print(result);
}

## X Mark Square (X자 사각형)
var result = '';
void main() {
  var n = 10;
  
  for (var i = 0; i < n; i++){
    for (var j = 0; j < n; j++){
      if (i == 0 || i == (n-1) || j == 0 || j == (n-1) || (i + j == n - 1) || (i == j)){
        result += '*';
      }else{
        result += ' ';
      }
    }
    result += '\n';
  }
  print(result);
}
==============================
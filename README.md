# Javascriptの習得
---
- ##オブジェクト型
### 定義
```js
//オブジェクトの生成
//一般的
var obj=new Object();
//他にも
var obj2={};
//これでもOK！
```
### リテラル
```js
var obj=new Object(){
  //aがキーで10は中に入っているリテラル
  //リテラルが２つ以上の場合は[,]で区切る
  a:10,
  //整数、実数、文字列、オブジェクト何でもOK！
  b:"value",
  //キーが文字列でもOK！
  "c":"value2"
}
```
### 定義したリテラルの使用
```js
//オブジェクト名.[ドット演算子]リテラル名
console.log(obj.a)//結果は10
//中身が何であろうが.[ドット演算子]で繋げればOK！
console.log(obj.b)//結果は"value"
//キーが文字列の際は2種類
//.で繋げる
console.log(obj.key)//結果は"value2"
// [ブラケット内に文字列でキー名を囲う]
console.log(obj["key"]);//結果は"value2"
```
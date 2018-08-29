# 夏休み中のスケジュール
---
 - ## 7月
---
 - ## 8月
--- 


[次へ](https://github.com/satoshigp/SummerVacation/edit/master/page01.md)

# インターンで習得,学んだこと
---
# JavaScript  
- ## スコープ
 スコープとは変数等が参照できる範囲のこと。
 スコープにも種類がある(知っているもののみ)。
 - グローバルスコープ
  1. いわゆるグローバル変数というやつでどこからでも参照可能
 - ブロックスコープ　
  1. ブロック単位でスコープ出来る、他ブロックの中に入ってしまったら、その変数を参照できない。
 - クロージャスコープ
  1. 分からん。
- ## 厳密等価演算子
```js
let Hoge=1;
//[==]は等価演算子
//数値と文字を同じ値としてみている。
console.log(Hoge=="1");//結果はtrue
//[===]は厳密等価演算子
//数値と文字を区別してみている。

console.log()
```
- ## 三項演算子
```js
let Hoge=0;
//console.logはデベロッパツールのconsole欄に表示する。
//ほとんどデバッグ専用
console.log(Hoge?Hoge:"NULL");//結果はNULL
```
`console.log` の中で行っている事は
```js
if(Hoge)
  {
    console.log(Hoge);
  }
  else
  {
    console.log("NULL")
  }
```
と上記の`if文`を三項演算子は省略している形になる。
  
- ## オブジェクト型
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
---
 - ## 非同期処理
 　- `非同期`とは？
  まずコードの評価の仕様として
   1. 同期処理(sync)[シンク]  
   1.非同期処理(async)[アシンク]  
 がある。
 コード例
 ```js
 console.log("aaa");
function hoge(num)
{
//戻り値にPrimiseのインスタンスを生成する
    return new Promise((resolve)=>
    {
    //setTimeoutとはJS内での一般的な非同期処理である。
        setTimeout(()=>{
            var i=0;
            for(var idx=1;idx<=num;idx++)
            {
                i+=idx;
            }
            //Promiseを生成した際に引数の中にさらに引数を渡してあげる。
            resolve(i);
        } , 10);
    });
}
//呼び出しは初めに宣言した関数名.then(function(引数)){処理})
//と初めて使う人からしたら魔法の言葉
hoge(1000).then(function(good)
{
    console.log(good)
    
})
console.log("bbb")
 ```
 

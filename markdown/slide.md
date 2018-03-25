2018/03/25 勉強会資料

---

ReatciveExtensions(Rx)の紹介

RxSwiftベース

---

### まず最初に

ReatciveExtensionsは
Swiftの__独自ライブラリではない__

JavaScript/Java/Python/C#などにも全く同じ性質のライブラリがある。

自分の書ける言語で同様のことができる

---

#### 背景

Web/アプリ問わず非同期処理を組み合わせることは一般的になっている

非同期処理の例
1. ネットワークアクセス
2. ファイルアクセス
3. ユーザー入力
などなど

---

#### 非同期処理の難しさ

同期処理
```
var array = [1,2,3]
for number in array {
  print(number)
}
```

非同期処理
```
var array = [1, 2, 3]

// 画面でボタンがクリックされた時に行われる処理
@IBAction func printNext(_ sender:Any) {
  for number in array {
    print(number)  <== ボタンがクリックされる瞬間まで何が表示されるか分からない
  }
}
```

---

#### Rxが解決する問題

#### 状態を持つ共有変数の排除

>>>

#### 命令的プログラミング

```
override func viewAppear(_ animated: Bool) {
  super.viewDidAppear(animated)

  // いつ何をするのかを列挙したプログラム
  // これらは順番を入れ替え可能かどうかが作った人にしか分からない
  setupUI()
  connectUIControls()
  createDataSource()
  listenForChanges()
}
```

>>>

#### 副作用

ある関数Aの実行前後によって、関数Bの結果が変わってしまうこと。
副作用があるプログラムは理解しにくい

---

#### Rxの特徴

* 宣言的なコード
* ReactiveSystem

NoReactive
```
a = 1
b = a * 3
a = 2
print b >>> 3
```

Reactive
```
a = 1
b = a * 3
a = 2
print b >>> 6
```

* b=3の代入を隠蔽してくれる仕組みとも言える

---

#### Rxの気持ちになるですよ

Everything is Sequence

すべてのデータも状態もイベントも時系列配列である！

http://rxmarbles.com/

---

#### ここまでで理解して欲しいこと

* Rxが解決したい課題
* RxはReactiveであること
* Everything is Sequence という響き

---

#### FizzBuzzアプリデモ

仕様
1. 毎秒1ずつカウントアップ
2. 数字ボタンタップでカウントアップ
3. Fizz/Buzz/FizzBuzzに該当するタイミングで画面に表示
4. 表示タイミングでユーザーが事前に入力した結果と答え合わせ
5. 正解不正解の表示
6. 正解で+1,間違えると-1で現在得点の表示
7. 10点を超えるとレベルアップして、Fizz/Buzzの正解が反転


---

# NoRxSwift

---

# RxSwift

---

Everything is Sequence

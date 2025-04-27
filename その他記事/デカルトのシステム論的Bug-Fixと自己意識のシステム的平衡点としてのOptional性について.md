デカルトのCogitoをシステム論的に分解しつつbug fixします。また自己意識を必要不可欠な本質的な存在から計算的な平衡状態である点についても論じます。また最終的には認知科学からの観点を入れつつ整合性を取っていきます。おまけで現象学的世界観へのつなぎもしてあります。

※専門家ではないので間違いがあるかもしれません。その点はご了承ください。

あとプログラムのbug fixレビューお待ちしております。
デカルト「我考える、故に我あり」

ざっくりと定義は何もかも疑って、自分の存在すら疑っても疑っている。でも疑っている自分は何かしらの形では存在している。故に我あり。
Cogitoにおけるシステム的欠陥

まずデカルトの論をプログラムに転写してみました。doubter()が疑う関数です。ぱっと見問題なさそうに見えます。しかしこれをよくよく考えるとこの実装ではdoubt()が返ってこない可能性があります。その場合は次の通りとなります。Aを疑っている私を疑っている私を疑っている….

要するに疑っていることの終了処理が疑う行為のみだと実装されていないのです。どこまで疑えば、疑っていることを終了できるのかということです。
2行で書くと次のようになり、実質的に「この文章は嘘である」と同じパラドックスになります。

```python
while(True):
  doubt("doubting-me") //疑っている状態が収束しない
```

```python
//cogito-org.ph

def doubt(x):
  //疑う処理

def doubter(x):
  return doubt(x)

int main(){

  //色々な事前処理

  While(true){
    a = doubter(X)

  if isVoid(a) == False:
    //自己が存在する
  else:
    //自己が存在しない

  }

//後の処理

}
```

# デカルトのシステム論的Bug Fix

一旦プログラムを抜けてデカルトをシステム論的に成り立たせていきます。要は観察者が必要なわけです。つまりdoubterノードと、observerノードの二つの相互承認関係によってIndeterminancyを回避する設計にすればよいのです。doubterノードが疑っている自分を疑っている自分を疑っている….という状態になったときにobserverノードが介入しそれを停止します。これでシステム的な安定を保つのです。
　
プログラム的に言えばある程度の自己参照ループに陥ったときは強制的に処理を落とすのです。

```python
//cogito-v2.ph
//v2 doubt()帰ってこない場合があることが分かったからバグfixしといた

def doubt(x):
//疑う処理

def doubter(x):
return cutoff_self_referential_state(doubt(x)) //自己参照バグ修正

int main(){

//色々な事前処理

while(true){
  a = doubter(X)

  if isVoid(a) == False:
    //自己が存在する
  else:
    //自己が存在しない

}

//後の処理

}
```

ミニマルに書くとこうなります。きちんとcutoff関数が動いていることが分かり、プログラムが美しく動いています。
```python
a = doubter("self")
  if isVoid(a) == False:
　  　//自己は存在する
```

# Cogitoのクラス設計

システムの必要条件が分かったので。Cogitoをクラス化していきます。
実装上の都合observerとdoubterだと内部で閉じてしまうので外部参照用にpublic関数のidentifySelfActivity()を入れました。これで外部から内部状態を参照できます。

```python
//cogito-class.ph

class Cogito::BaseClass_Cogito:
  def init(self):
    startSelfSystem()

  private doubter():
    //内部処理
  
  private observer():
    //内部処理

  private startSelfSystem():
    //doubter()とobserver()を起動する

  public identifySelfActivity()
    //doubter()とobserver()の交流状態を判定する

```

# 多重人格と多クラスインスタンス

クラス化できるということは多重インスタンス化も出来るわけです。ちょうど実際の例もあり、多重人格にあたるように見えます。ここから推論できるのは恐らくいわゆる本当の私というのは最も古いクラスインスタンスのことと読めます。システム上アクティブなインスタンスが今起動している人格。またこうなる人格の完全な乗っ取りに近い現象が起きていることもあるかもしれません。そして本人はそれに気づいていないこともあるかと思われます。しかしこれはシステム全体としてみれば平衡点の移動であり、恒常性の維持の観点から見てみれば自然に見えます。


# 自己意識のOptional性についてと認知科学的整合性

こうなると私は何なんだとなりますが、認知科学的に見れば私が存在するわけではないです。例えば心臓のように。自己意識は計算の結果であり、内部状態及び外部環境が変わればシフトします。要は今私たちが私だと思っているのは必然ではなく、システム上の最適均衡状態であり、必要に応じてその自己意識は変化するか切り替えが起き得ます。

# 現象学的世界観とのトポロジカル整合性

最後に現象学的世界観からの整合性も取っておきます。自己が分裂すると現象学的世界観が崩れてしまいます。深くはもぐりませんが、observerとdoubterはhomeomorphismであると考えれば都合は合わせられるかと思っています。

© 2025 [No Name Yet Exist]
All contents are protected under copyright law. Unauthorized reproduction or redistribution without explicit permission is prohibited.

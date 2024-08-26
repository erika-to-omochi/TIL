***
### 🍓8/25（136d） 3h/7569h
**🐰今日の学習**
- [x] paiza 復習 + Cランク3問
- [x] Next.js
- [x] Railsで遊ぶ（以前作ったアプリをいじる
***
### 🍓8/25（136d） 6h/765h（16ポモ)
**🐰今日の学習**
- [x] paiza Cランク2問
- [x] プロを目指す人のためのRuby入門(〜7.3.3)
- [x] Next.js
- [x] Railsで遊ぶ（以前作ったアプリをいじる
 
**🐣感想**

 initialize, @, attr_accessormは説明を読むと理解した気になりますが、自分の言葉で説明しようと思うと全く説明できないです…このあたり、なかなか腑に落ちた理解ができていないです。以下、自分なりの解釈メモ
```
class User
  def initialize(name)
    @name = name
  end

  def name
    @name
  end
end

user = User.new('Alice')
puts user.name #=> Alice


① User.newとすると、initializeメソッドが実行される
② 引数nameに Aliceが代入され、@name = Aliceとなる
③ @はインスタンス変数なので、Userクラスの外部からは取得できないので
    @nameを外部から参照するためのnameメソッドを作り、
　 nameメソッドを経由して@nameの内容を取得する
------------------------------------------------------------------------------------------------------
もしくは
class User
  attr_accessor :name

  def initialize(name)
    @name = name
  end
end

user = User.new('Alice')
user.name ='Bob'
puts user.name #=> Bob

① User.newとすると、initializeメソッドが実行される
② 引数nameに Aliceが代入され、@name = Aliceとなる
③ @はインスタンス変数なので、Userクラスの外部からは取得できないが、
　 attr_accessor :nameとあるため、@nameを読み書きするメソッドが自動的に定義される
④ user.name ='Bob'で@nameを変更でき、
　 puts user.nameで@nameを参照できる！！！

```

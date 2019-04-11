# ガチャアプリ
***
## １、押さえておくポイント、Swift言語特性
### 新しい画面を追加したい時
1. 右上のライブラリ（部品一覧が表示できるボタン）をクリックする。  
1. 「View Controller」を選択しMain Story Boardにドラックアンドドロップする。  
#### ※新しい画面を追加した際の注意  
コードを書くファイルは一つのView Controllerに対して一つ必要なので追加したView Controllerの分、クラスファイルを追加する必要がある。

---

### UI Image Viewの画像を画面いっぱいに広げたい時
UI Image ViewのModeを右側のタブの下矢印のところで「Scale to Fill」から「Aspect Fill」に変更する。  

---

### 作成したView Controllerに画面推移したい時（コードを用いて）
初級でボタンからコントロールを押しながら別のView Controllerにドラックアンドドロップさせて画面推移させる方法があったが、コードを用いて画面推移させる場合は以下のようにする。  

1. MainStoryBoardを開き左下の「View as...」の左隣のボタンをクリックする。  
1. 画面推移させる元のView ControllerをControlを押しながら選択し。画面推移させたいView Controllerにドラックアンドドロップする。  
1. View Controllerの間にあるある矢印をクリックし、右側の下矢印をクリックしIdentifierの部分を好きな文字列に変える  
※Identifierとは鍵のような役割をしていて、プログラムがどの画面推移を実行したらいいのか探すときに使う。  

#### 画面推移のプログラムの書き方  
画面推移されるときに押されるボタンが押された時のメゾットの中括弧の中(IBAction funcの中)に以下のようなコードを書く。  
```
self.performSegue(withIdentifier: "先ほど決めたIdentifier", sender: nil)
```
画面を元に戻したい場合は以下のように書く  
```
self.dismiss(animated: true, completion: nil)
```

---

### Swiftクラスファイルの追加の仕方
1. 画面左上のXcodeという文字の隣にあるFileを選択し、Newを選び、Fileを選択する。  
1. Cocoa Touch Classを選び、ファイル名を入力しNextを押す。  

---

#### クラスファイルをView Controllerに結びつける。
1. 結びつけたい、View Controllerを選択する。  
1. 右側にあるタブの左から3番目のボタンをクリックし、Custom ClassのなかのClassから先ほど作成したクラスファイルを選択する。  
___

## ２、エラー

### 画面推移されない
#### 原因

!MainStoryBoardで設定したIdentifierとコードに書いてあるIdentifierが違う可能性がある。  
whileの「〜出ない時」の部分の！を忘れている可能性があるのでそこがちゃんとついているか確認する。  
while文は中括弧が多いので正しい数より多くないか、また少なくないかを確認する。  

### 画像が表示されずにアプリが落ちる
#### 原因
アプリが画像を認識していない可能性がある。
#### 対処法
画像が入っているフォルダを丸々Assets.xcassetsに入れ、ImageViewの写真を拡張子（pngなど）がついていない物を選択する。  

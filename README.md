# mypkg
![test](http://github.com/ezawaaoi/robosys2022/actions/workflows/test.yml/badge.svg)

* このリポジトリはROS2のパッケージです。
* ワークスペースを作成し、移動した後に```git clone```を使用してパッケージをインストールしてください。
```
$ mkdir -p ros2_ws/src
$ cd ~/ros2_ws/src/
$ git clone https://github.com/ezawaaoi/mypkg.git
```

# talker・listener
* talkerを実行するとcountupというトピックを通じて、Int16型のメッセージを送信します。
* listenerを実行するとtalkerから送信されたInt16型のメッセージを受信して出力します。

## 実行例
端末を二つ用意してください。
* 端末１に入力
```
$ ros2 run mypkg talker
```
* 端末２に入力
```
$ ros2 run mypkg listener
```
* 端末２の出力結果
```
[INFO] [1672457722.407598100] [listener]: Listen: 0
[INFO] [1672457722.899632400] [listener]: Listen: 1
[INFO] [1672457723.398233700] [listener]: Listen: 2
[INFO] [1672457723.898263000] [listener]: Listen: 3
[INFO] [1672457724.398968000] [listener]: Listen: 4
[INFO] [1672457724.897690300] [listener]: Listen: 5
[INFO] [1672457725.399087700] [listener]: Listen: 6
[INFO] [1672457725.899485600] [listener]: Listen: 7
[INFO] [1672457726.399044900] [listener]: Listen: 8
[INFO] [1672457726.899190300] [listener]: Listen: 9
[INFO] [1672457727.399100400] [listener]: Listen: 10
（以下省略）
```
# launchファイル
* launchファイルを使用することで、複数のノードを同時に立ち上げることができます。
## 実行例
```
$ ros2 launch mypkg talk_listen.launch.py

[listener-2] [INFO] [1672458277.176183500] [listener]: Listen: 0
[listener-2] [INFO] [1672458277.668341800] [listener]: Listen: 1
[listener-2] [INFO] [1672458278.168490200] [listener]: Listen: 2
[listener-2] [INFO] [1672458278.668697500] [listener]: Listen: 3
[listener-2] [INFO] [1672458279.168380900] [listener]: Listen: 4
[listener-2] [INFO] [1672458279.668560400] [listener]: Listen: 5
[listener-2] [INFO] [1672458280.168616400] [listener]: Listen: 6
[listener-2] [INFO] [1672458280.668340000] [listener]: Listen: 7
[listener-2] [INFO] [1672458281.168444400] [listener]: Listen: 8
[listener-2] [INFO] [1672458281.668373500] [listener]: Listen: 9
[listener-2] [INFO] [1672458282.168435900] [listener]: Listen: 10
（以下省略）
```
## 動作確認済み環境
* Ubuntu22.04
* ROS2 humble

## ライセンス
* このソフトウェアパッケージは、3条項BSDライセンスの下、再頒布および使用が許可されます。
* このパッケージのコードは、下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを、本人の許可を得て自身の著作としたものです。
    * [ryuichiueda/my_slides robosys_2022](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)

© 2022 Aoi Ezawa

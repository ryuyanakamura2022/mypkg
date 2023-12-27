![test](https://github.com/ryuyanakamura2022/robosys2023_ROS2_mypkg/actions/workflows/test.yml/badge.svg)

# mypkg
このリポジトリはロボットシステム学の講義課題2用のものです。

## 機能説明
このプログラミングは、ROS2を使用したものである。
* 「talker」「listener」「トピック」「メッセージ」について
  * 「talker」は、パブリッシャである。データを配信するノードになる。
  * 「listener」は、サブスクライバである。「talker」から送られてきたデータを受け取るノードになる。
  * 「トピック」は、「talker」から配信されたデータの伝送経路である。
  * 「メッセージ」は、トピック間を流れるデータのことである。

このプログラムの内容は、talkerとlistenerの2つのノードを使用したものである。
* 「talker」では、数値をカウントするノードである。カウントした数値は、Int16型のメッセージになって、/countupというトピックを通して「listener」に配信する。
* 「listener」では、「talker」から送られて来た数値を受信して表示するノードである。

# 使用方法
## 1.talkerとlistenerを2つの端末で使用する方法
最初に端末はコマンドを入力できるように2つ開いておく。

* talker側の実行コマンド
```
端末1$ ros2 run mypkg talker
```
(実行結果)
```
```
実行結果は何も表示されない。

* listner側の実行コマンド
```
端末2$ ros2 run mypkg listener
```
(実行結果)
```
[INFO] [1703512866.347562333] [listener]: Listen: 0
[INFO] [1703512866.815362721] [listener]: Listen: 1
[INFO] [1703512867.315025427] [listener]: Listen: 2
[INFO] [1703512867.814878339] [listener]: Listen: 3
[INFO] [1703512868.314889485] [listener]: Listen: 4
[INFO] [1703512868.815014449] [listener]: Listen: 5
[INFO] [1703512869.314960658] [listener]: Listen: 6
[INFO] [1703512869.814934289] [listener]: Listen: 7
[INFO] [1703512870.314983628] [listener]: Listen: 8
[INFO] [1703512870.814915978] [listener]: Listen: 9
[INFO] [1703512871.314785919] [listener]: Listen: 10
                ...(以下省略)...
```
表示は無限に続くので[ctrl + c]で強制的に終了させる。

## 2. talkerとlistenerを同じ端末で表示する方法
端末は1つ開いておく。

```
端末$ ros2 launch mypkg talk_listen.launch.py
```
(実行結果)
```
[listener-2] [INFO] [1703513557.621988092] [listener]: Listen: 0
[listener-2] [INFO] [1703513558.102224179] [listener]: Listen: 1
[listener-2] [INFO] [1703513558.602783970] [listener]: Listen: 2
[listener-2] [INFO] [1703513559.102487731] [listener]: Listen: 3
[listener-2] [INFO] [1703513559.602200553] [listener]: Listen: 4
[listener-2] [INFO] [1703513560.102432536] [listener]: Listen: 5
[listener-2] [INFO] [1703513560.602303119] [listener]: Listen: 6
[listener-2] [INFO] [1703513561.102248327] [listener]: Listen: 7
[listener-2] [INFO] [1703513561.602399260] [listener]: Listen: 8
[listener-2] [INFO] [1703513562.102208466] [listener]: Listen: 9
[listener-2] [INFO] [1703513562.602157028] [listener]: Listen: 10
                         ...(以下省略)...
```
こちらも1と同様に終了させたいときは[ctrl + c]を入力する。

## 必要なソフトウェア
* python
* ROS2(foxy,humble)

## テスト環境
* Ubuntu (22.04) 

## ライセンス 
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます。
* このパッケージのコードは，下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです。
  * [ryuichiueda/my_slides robosys_2022](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)
* © 2023 Ryuya Nakamura

![test](https://github.com/ryuyanakamura2022/robosys2023_ROS2_mypkg/actions/workflows/test.yml/badge.svg)

# robosys2023_ROS2_mypkg
このリポジトリはロボットシステム学の講義課題2用のものです。

## 機能説明
このプログラムは、ROSを使用してパブリッシャ側でカウントした数値をサブスクライバで表示するものである。
* パブリッシャ側では、数値をカウントして、それをサブスクライバ間でのトピックを通して送信するノードである。
* サブスクライバ側では、パブリッシャとのトピックで送信されてきたメッセージを表示するノードである。

パブリッシャを「talker」、サブスクライバを「listener」と表示する。メッセージの型は16ビット符号つき整数で送る。
トピックはこの場合だと、「talker」から送信されてきたメッセージを「listener」で受信する通信経路である。

# 使用方法
## 1.talkerとlistenerを2つの端末で使用する方法
最初に端末にコマンドを入力できるように2つ開いておく。

talker側の実行コマンド
```
端末1$ ros2 run mypkg talker
```
listner側の実行コマンド
```
端末2$ ros2 run mypkg listener
```
以上のコマンドをそれぞれの端末に入力して、実行をする。
## 実行結果1
talker側では以下の表示になる。
```
```
表示は何もされない。

listener側では以下の表示になる。
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
端末を1つ開いておく。

```
端末$ ros2 launch mypkg talk_listen.launch.py
```
端末に入力して実行する。

## 実行結果2
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
* ubunte
* python(python 3.8.10)
* ROS2

## テスト環境
* ubuntu 22.04 

## ライセンス 
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます。
* © 2023 Ryuya Nakamura

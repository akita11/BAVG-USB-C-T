# BAVG-USBC-T / BAVG-USBC-T-PD / BAVG-USBC-T-PDdiv

USB TypeｰCケーブル（両側）をツイストペア線と電源線として使用して、RS485等の差動伝送を行うことができます。
複数を直列（デージーチェーン）接続することで、マルチドロップのT型トポロジ接続にできます。

[M5Stack社のRS485 Unit](https://www.switch-science.com/products/6554)や[RS485M Unit](https://github.com/akita11/RS485M_Unit)等に接続して使用できます。
USB Type-Cケーブルの、データ線(D+/D-)をデータ送信用の差動対(A/B)、電源線を給電(V/G)に用います。

<img src="https://github.com/akita11/BAVG-USB-C-T/blob/main/BAVG-USB-C-T_with_HT.jpg" width="240px">


このページでは以下の3種類の情報をまとめています。


## BAVG-USBC-T

<img src="https://github.com/akita11/BAVG-USB-C-T/blob/main/BAVG-USB-C-T.jpg" width="240px">

両側のUSB Type-Cコネクタ間のデータ線(DP/DN)がA/B線と接続されていて、マルチドロップ型のデータ通信を行うことができます。


## BAVG-USBC-T-PD

<img src="https://github.com/akita11/BAVG-USB-C-T/blob/main/BAVG-USB-C-T-PD.jpg" width="240px">

BAVG-USBC-T-PDではUSB PD (Power Derivery)の電圧設定機能があり、給電電圧を20Vまたは12Vに設定できます。
電圧設定が有効の場合はPG (Power Good)LEDが点灯します

また2つのUSBコネクタの通信線は接続されていないため、両側のUSBコネクタでのデータ通信を行うことはできません。
2つのコネクタでデータ通信を行う場合は、PD機能のない「BAVG-USBC-T」、またはPD給電コネクタが別にある「BAVG-USBC-T-PDdiv」を使用してください。

<img src="https://github.com/akita11/BAVG-USB-C-T/blob/main/BAVG-USB-C-T-PD_dir.jpg" width="240px">

**※USB PD電源からのUSB Type-Cケーブルは、必ず右側のUSB Type-Cコネクタ（この写真の赤丸側）へ接続してください。
（反対側に接続すると、RS485ラインのB/A端子がUSBケーブルのDP/DNに接続され、ACアダプタ等によってはQC制御によって供給電圧が変動する場合があり、高電圧の場合は機器が破損する場合があります）
またデータ通信は左側のUSB Type-Cコネクタのみに接続されています。**

通信経路と給電は以下の接続としてください。

<img src="https://github.com/akita11/BAVG-USB-C-T/blob/main/config.png" width="640px">


### USB PD給電の設定

<img src="https://github.com/akita11/BAVG-USB-C-T/blob/main/BAVG-USB-C-T-PD-B.jpg" width="240px">

- JP1: USB PD電圧設定機能の有効無効設定
  - ショート（デフォルト） : 有効
  - オープン : =無効


- JP2でUSB PD給電電圧
  - オープン（デフォルト）: 20V
  - ショート : 12V

※USB PD電圧設定機能を有効にするのは、接続全体で1台のみとしてください。

※JP2の設定は、給電元（ACアダプタ等）へ要求する電圧で、実際に供給される電圧はUSB PD ACアダプタ等の仕様によります。
（例えば給電側の供給可能電圧が9V/15V/20Vの場合でJP2をショートした場合は9Vとなります）


## BAVG-USBC-T-PDdiv

<img src="https://github.com/akita11/BAVG-USB-C-T/blob/main/BAVG-USB-C-T-PDdiv.jpg" width="240px">

USB Type-Cコネクタが3つあり、1つは給電用（データ線の接続なし）、残り2つは「BAVG-USBC-T」と同様にデータ線（DP/DN）が接続されており、マルチドロップ型の通信を行うことができます。

USB PDの電圧設定は「BAVG-USBC-T-PD」と同様です。


## Author

Junichi Akita (@akita11) / akita@ifdl.jp

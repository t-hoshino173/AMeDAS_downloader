# AMeDAS_downloader
気象庁が公開しているAMeDASのデータをスクレイピングするツールです。
AMeDASの公開ページのhtmlファイルを保存するプログラムと、そのデータから表を抜き出してcsvに変換するプログラムと、作成された個々のcsvファイルを結合するプログラムから構成されています。

##動作環境
Python3
Windowsでも、Macでも、UbuntuでもPython3がインストールされていれば動作します。

##著作権
  著作権は開発者である森下功啓に帰属しますが、本ソフトによって生じたいかなる損害・改良・公開については一切関知しません。

##改良時の注意
ファイルのダウンロード間隔をむやみに小さくせず、気象庁のサーバ負荷を高めない範囲でご使用ください。

##ファイルの説明
===
AMEDAS_list.csv
　“AMEDAS_list.csv”は、アメダスの観測所の情報を格納したcsvファイルです。
===
AMEDAS.ini
　AMEDAS.iniは、ダウンロード対象の期間とアメダスの観測所の情報を格納した設定ファイルです。実行の前にご確認下さい。
===
download.py
　download.pyは、アメダスが観測した過去の気象データをダウンロードするスクリプトです。過去の1時間毎の観測データ、過去の10分毎の観測データ、最新の観測データをダウンロードすることが出来ます。
===
html_parser.py
　html_parser.pyは、ダウンロード済みのアメダス観測データをcsv形式に変換するスクリプトです。処理対象期間をAMEDAS.iniで設定します。
===
file_fusion.py
　file_fusion.pyは「Processed HTML」フォルダ下に存在する処理済みcsvファイルの結合に使用するスクリプトです。実行すると、観測局毎に全観測期間のデータを結合したcsvファイルを作成します。

##実行の方法
　ダウンロードしたい地点の名前や期間についてAMEDAS.iniに書き込んでください。準備ができたら、download.pyを実行すると、観測データが自動的にダウンロード＆保存されます。実行には、Windowsであればコマンドプロンプト，Macではターミナルを立ち上げて実行して下さい。なお、htmlファイルができても中身がない場合はソフト側のミスもしくは気象庁側でブロックされたものと考えられます。

以下に、1時間毎のデータをダウンロードする実行コマンドの例を示します。

$ python download.py hourly
又は
$ python3 download.py hourly

引数には、"daily", hourly", "10min", "real-time"の4パターンがあります。
それぞれ、日毎のデータ、1時間毎のデータ、10分毎のデータ、リアルタイムのデータを意味しています。

##スクリプトファイルとAMEDAS.iniの文字コード
  UTF-8

##編集時の注意
  たまに、編集後に文字コードをUTF-8以外に変更するエディタが有ります。文字コードを変えないようにしてください。

##機能追加のリクエストについて
たまに機能追加のリクエストをメールで頂きますが、忙しい時期や面倒なときにはスルーすることがございます。
オープンソースですので、ぜひフォークして機能を追加していただければ幸いです。
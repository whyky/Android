﻿・FCFReaderForPaSoRiについて

USBホスト機能を備えたAndroid 3.2以降のAndroidタブレットとPaSoRiリーダーを組み
合わせた
FCFキャンパスカード用のICカード読取りソフトです。スタンドアロンの出席登録端末と
して
使うことを想定しています。

本アプリはAndroidタブレットとPaSoRiリーダーの組み合わせによるFCFキャンパスカー
ド読取り動作の実証を目的としたもので、
本体内に記録されたデータの機密性・完全性については何ら特別な対処は行っていません。
したがって、実業務への利用を
想定したものではありません。

本ソフト自体の不具合、ならびにタブレット本体の盗難・紛失・破損に伴って本体内に記
録されたデータの機密性・完全性が
失われることに十分留意の上ご利用ください。

・本ソフトの機能

本ソフトには以下の機能があります：

(1)FCFキャンパスカードの読取り機能

	FCFキャンパスフォーマットに対応したICカードをかざすと、学生番号・現在時
刻が
	ログに保存されます。

	注：FCFキャンパスカードでないICカードをかざしても何も起きません

(2)出席受付け時刻設定機能

	出席登録の開始・終了時間を指定することができます。

(3)画面ロック機能

	出席登録受付け中に誤って画面操作をしてしまわないよう、操作画面をロックす
ることができます。
	暗唱番号を入力して画面ロックを解除します。なお、暗唱番号の初期値は「0000」
です。


・動作環境

以下の機器での動作を確認しています。ただし、状況によってはPaSoRiリーダーがAndroid
に
うまく認識されないことがあります。その場合はUSBケーブルの抜き出し、アプリの再起
動などの操作を
行ってください。

(1)Androidタブレット

	GalaxyNoteSC-05D(Android4.0,5.3インチ)
	Nexus 7(Android 4.1, 7インチ)
	ICONIA A500(Android 3.2, 10.1インチ)

(2)PaSoRiリーダー

	RC-S360(スティック型)
	RC-S370(卓上設置型)

・使い方

(1)アプリのインストール

	本アプリ(FCFReaderForPaSoRi)をAndroidタブレットにインストールします。
	Androidタブレットで以下のURIにアクセスし、本アプリのバイナリをダウンロード・インストールしてください:
	
	https://github.com/nagai-takayuki/Android/raw/master/FCFReaderForPasori/bin/FCFReaderForPasori.apk

(2)PaSoRiリーダーの接続

	PaSoRiリーダーをタブレットのUSBポートに接続してください。USB OTG対応タ
ブレットの場合は
	接続にUSB OTGケーブルも必要になります。

(3)FCFReaderForPaSoRiの起動

	本アプリを起動します。

(4)ICカードの読取り

(4-1)画面右上の設定メニューから「設定」を選択します

	カード読取り時のビープON/OFF,暗唱番号変更を行います

	必要な設定を行ったら「Backキー」を押してメイン画面に戻ります

(4-2)出席受付け時刻の設定

	メイン画面上部の「出席設定」をクリックし、出席受付け開始時刻、出席受付け
時間を設定します。

	出席受付時間を「0分」に設定すると、「受付締切なし」の意味になります。

(4-3)出席受付開始

	メイン画面上部の「出席登録」をクリックすると、出席登録画面になります。

	出席登録受付け中の画面操作を禁止したい場合は、画面右上の「画面ロック」を
クリックしてください。

	操作画面のロックを解除するには、画面右上の「画面ロック解除」をクリックし
てください。
	暗唱番号を正しく入力すると画面ロックが解除されます。

(4-4)出席記録閲覧

	メイン画面上部の「出席ログ」をクリックすると、出席記録閲覧画面になります。
	ログの表示項目は「打刻時刻,タイムゾーン,ユーザ区分,学生番号,カード有効期
限」となっています。

(4-5)終了操作

	本アプリを手動で終了される場合は画面右上の設定メニューから「終了」を選択
します。
	主にアプリケーションを多重起動してしまった場合に利用します。

(4-6)出席記録の消去

	画面右上の設定メニューから「設定」を選択します

	「出席ログ消去」の項目をクリックすると出席記録が消去されます。

・出席ログの読み出し方法

	出席ログはAndroidタブレット本体のアプリケーション用領域にFCF.logという
ファイル名で保存されています。
	AndroidタブレットをPCにMTPデバイスとして接続することで出席ログを読み出
すことができます。

	例えば、Nexus7の場合では
/Android/data/jp.ac.kumamoto_u.cc.fcfreaderforpsori/files/FCF.log
	に出席ログが保存されています。

・注意事項

(1)デバッグ出力について

	本ソフトの動作状況確認、並びにICカードに対する不正なアクセスを行っていな
いことを明らかにするため、
	Android標準のログ機能を用いたデバッグ出力を行っています。このデバッグ出
力にはPaSoRiリーダーとやりとりしたデータ、
	画面ロック解除用の暗唱番号等が含まれます。

	デバッグ出力の内容はadb USB protocolに対応したツール(Eclipse上のAndroid
開発環境など)で表示させることができます。

(1)PaSoRiリーダーの認識に失敗した場合の症状

	出席登録画面に「Pasoriリーダーの初期中です」と表示されたままになっている
場合は、
	Pasoriリーダーの認識に失敗しています(本アプリを多重起動した場合によくこ
の症状が出ます)。
	この場合はUSBケーブルを抜き出しする、多重起動されているアプリを終了させ
るなどの操作を
	行ってください。

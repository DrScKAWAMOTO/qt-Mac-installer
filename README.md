# Mac 用ドラッグアンドドロップ型インストーラ作成方法
以下、作業をする Mac ホスト名を mars とし、ユーザー名を kawamoto として説明するので、適宜読み替えること。

## 1) リリース構成で FullereneViewer をビルドする。

## 2) ディスクイメージ作成
　アプリケーションフォルダの中のユーティリティを開き、中のディスクユーティリティ.app を起動する。  
　新規イメージをタップする。  
　一番上の名前を「FullereneViewer-1.4.4.dmg」に、上から３番目の場所を「デスクトップ」に、上から４番目の名前を「FullereneViewer-1.4.4」に、サイズを500MBに、パーティションを「単一パーティション - Apple パーティションマップ」に変更し、「作成」ボタンを押す。

## 3) 背景画像の作成
　デスクトップ上のドライブアイコンをクリックする。  
　FullereneViewer-1.4.4 フォルダの中に Background フォルダを作成する。  
　Background フォルダの中に background.png をコピーする。  
　FullereneViewer-1.4.4 フォルダのタイトルバーをクリックし、Command-J を押す。  
　背景：のピクチャを選択し、Background フォルダにコピーした background.png をドラッグする。  
　ターミナルアプリを起動し、以下を入力する。

    mars:kawamoto> SetFile -a V /Volumes/FullereneViewer-1.4.4/Background

## 4) FullereneViewer アプリとアプリケーションフォルダの作成
　FullereneViewer アプリをデプロイする。  

    mars:kawamoto> cd src/Qt/FullereneViewer/src/build-FullereneViewer-Desktop_Qt_5_4_0_clang_64bit-Release
    mars:build-....> ~/Qt5.4.0/5.4/clang_64/bin/macdeployqt FullereneViewer.app
    ERROR: no file at "/opt/local/lib/libxslt.1.dylib"
    ERROR: no file at "/opt/local/lib/libsqlite3.0.dylib"
    ERROR: no file at "/opt/local/lib/libz.1.dylib"
    ERROR: no file at "/opt/local/lib/libz.1.dylib"
    ERROR: no file at "/opt/local/lib/libz.1.dylib"
    ERROR: no file at "/opt/local/lib/mysql55/mysql/libmysqlclient.18.dylib"
    ERROR: no file at "/opt/local/lib/libz.1.dylib"
    ERROR: no file at "/usr/local/lib/libpq.5.dylib"
    ERROR: no file at "/opt/local/lib/mysql55/lib/libmysqlclient.18.dylib"

　上記エラーが発生するが気にしない。  
　上記でデプロイした FullereneViewer.app をファインダーを使って FullereneViewer-1.4.4 フォルダにドラッグしてコピーする。  
　ファインダーで mars デバイスを開き、Macintosh HD の中のアプリケーションフォルダを選択する。  
　メニューの [ファイル] - [エイリアスを作成] を選択する。  
　できあがった「アプリケーション のエイリアス」をファインダーを使って FullereneViewer-1.4.4 フォルダにドラッグしてコピーする。名前は「アプリケーション」に変更しておく。  
　FullereneViewer-1.4.4 フォルダのタイトルバーをクリックし、Command-J を押す。  
　アイコンサイズを 100x100 に変更する。  
　アイコンの位置やフォルダの大きさを変更して見た目を整える。  

## 5) ディスクイメージの変換
　ディスクユーティリティに戻って、FullereneViewer-1.4.4 を選択する。  
　「マウント解除」ボタンを押す。  
　FullereneViewer-1.4.4.dmg を選択し、「変換」ボタンを押す。  
　「保存」ボタンを押す。  
　「置き換え」ボタンを押す。  
　FullereneViewer-1.4.4 を選択し、「取り出す」ボタンを押す。  
　FullereneViewer-1.4.4.dmg を選択し、右ボタンをクリックしてポップアップメニューの中の「削除」を選択する。

## 6) FullereneViewer-1.4.4.dmg ファイルのアイコン設定
　FullereneViewerInstallerDmg.png をダブルクリックしてプレビューアプリを起動し、メニューの [編集] - [コピー] を選択する。  
　FullereneViewer-1.4.4.dmg を選択し、Command-I を押す。  
　一番上にあるアイコンをクリックし、Command-V を押すと、アイコンが変化する。
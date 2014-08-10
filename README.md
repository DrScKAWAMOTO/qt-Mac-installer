# Mac 用ドラッグアンドドロップ型インストーラ作成方法

## 1) リリース構成で FullereneViewer をビルドする。

## 2) ディスクイメージ作成
　アプリケーションフォルダの中のユーティリティを開き、中のディスクユーティリティ.app を起動する。
　新規イメージをタップする。
一番上の名前を「FullereneViewer-1.2.dmg」に、上から４番目の名前を「FullereneViewer-1.2」に、パーティションを「単一パーティション - Apple パーティションマップ」に変更し、「作成」ボタンを押す。

## 3) 背景画像の作成
　ドライブアイコンをクリックする。
　FullereneViewer-1.2 フォルダの中に Background フォルダを作成する。
　Background フォルダの中に background.png をコピーする。
　FullereneViewer-1.2 フォルダのタイトルバーをクリックし、Command-J を押す。
　背景：のピクチャを選択し、Background フォルダにコピーした background.png をドラッグする。
　ターミナルアプリを起動し、以下を入力する。
    mars:kawamoto> SetFile -a V /Volumes/FullereneViewer-1.2/Background

## 4) FullereneViewer アプリとアプリケーションフォルダの作成
　FullereneViewer アプリをデプロイする。
    mars:kawamoto> cd src/Qt/FullereneViewer/src/build-FullereneViewer-Desktop_Qt_5_3_clang_64bit-Release
    mars:build-....> ~/Qt5.3.1/5.3/clang_64/bin/macdeployqt FullereneViewer.app
    ERROR: no file at "/opt/local/lib/mysql55/lib/libmysqlclient.18.dylib"

　上記エラーが発生するが気にしない。
　上記でデプロイした FullereneViewer.app をファインダーを使って FullereneViewer-1.2 フォルダにドラッグしてコピーする。
　ファインダーで mars デバイスを開き、Macintosh HD の中のアプリケーションを選択する。
　メニューの [ファイル] - [エイリアスを作成] を選択する。
　できあがった「アプリケーション のエイリアス」をファインダーを使って FullereneViewer-1.2 フォルダにドラッグしてコピーする。名前は「アプリケーション」に変更しておく。
　FullereneViewer-1.2 フォルダのタイトルバーをクリックし、Command-J を押す。
　アイコンサイズを 100x100 に変更する。
　アイコンの位置やフォルダの大きさを変更して見た目を整える。
　FullereneViewer-1.2 フォルダを閉じる。

## 5) ディスクイメージの変換
　ディスクユーティリティに戻って、FullereneViewer-1.2 を選択する。
　「マウント解除」ボタンを押す。
　FullereneViewer-1.2.dmg を選択し、「変換」ボタンを押す。
　「保存」ボタンを押す。
　「置き換え」ボタンを押す。

## 6) FullereneViewer.dmg ファイルのアイコン設定
　FullereneViewerInstaller.png をダブルクリックしてプレビューアプリを起動し、メニューの [編集] - [コピー] を選択する。
　FullereneViewer.dmg を選択し、Command-I を押す。
　一番上にあるアイコンをクリックし、Command-V を押すと、アイコンが変化する。
 
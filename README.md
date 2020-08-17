# Windows Terminal をインストールする（Scoop を使って）
Windows Terminal をインストールする。

今回はインストールツールとして Scoop を利用する。Scoop が何か分からない、まだ導入していない場合は、以下のページを参照する。

[Scoop とは（メリットと使い方）](https://github.com/fs5013-furi-sutao/explain.scoop)

## アプリの場所を探す
Scoop でアプリのマニフェスト（対象アプリをインストールする手順書）のリポジトリ（マニフェストが置かれた場所）を探すには、以下のコマンドを実行する。

```console
scoop search windows-terminal
```
実行結果例:
```
Results from other known buckets...
(add them using 'scoop bucket add <name>')

'extras' bucket:
    windows-terminal (1.0.1811.0)
```
上記の場合、実行結果例を見ると、ローカルにマニフェストがなく、他のバケットにありますよ・・・と言っている。その他のバケットはと、`extras` バケットであると。

## バケット一覧を表示する
では、ローカルのバケット一覧を表示してみる。
```console 
scoop bucket list
```
実行結果例:
```
main
```
上記の場合、ローカルには `main` バケットしか無いので別途、`extras` バケットをローカルに追加する必要がある。

## バケットの追加
`extras` バケットを追加するには以下のコマンドを実行する

```console
scoop bucket add extras
```
実行結果:
```
Checking repo... ok
The extras bucket was added successfully.
```
バケットの追加が成功した。

## Windows Terminal のインストール
準備が整ったので、次のコマンドで Java をインストールする。
```console
scoop install windows-terminal
```
実行結果:
```
Updating Scoop...
Updating 'java' bucket...
Updating 'main' bucket...
Scoop was updated successfully!
Installing 'windows-terminal' (1.1.2233.0) [64bit]
Microsoft.WindowsTerminal_1.1.2233.0_8wekyb3d8bbwe.msixbundle (20.5 MB) [=====================================] 100%
Checking hash of Microsoft.WindowsTerminal_1.1.2233.0_8wekyb3d8bbwe.msixbundle ... ok.
Extracting dl.7z ... done.
Running pre-install script...
Running installer script...
Linking ~\scoop\apps\windows-terminal\current => ~\scoop\apps\windows-terminal\1.1.2233.0
Creating shim for 'WindowsTerminal'.
Creating shim for 'wt'.
Creating shortcut for Windows Terminal (WindowsTerminal.exe)
'windows-terminal' (1.1.2233.0) was installed successfully!
```
Windows Terminal のインストールが完了した。

## Java のバージョン確認
Java がインストールできていることを、次のコマンドで確認する。
```console
wt --version
```

バージョンがダイアログで表示される。

実行結果:
```
Windows ターミナル（アンパッケージ）
1.1.200810003-release1.1
```

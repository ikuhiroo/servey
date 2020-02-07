## Language Server Protocol (LSP)
* 消しやすい Vim の構成
* 各プログラミングごとに用意すべきツール類をまとめるのに困難
* vim-lsp-settings というプラグインで便利に導入可能
** https://github.com/mattn/vim-lsp-settings

## 言語ごとに最低限必要な機能 (IDE機能)
* 定義位置ジャンプ (:LspDefinition)
* 入力補完 (ctrl + n / p)
* ソースファイル整形

## LSPの動作
* 扱うプログラミング毎に起動
* gopls: GO言語専用のLanguage Server
* pyls: python-language-server
* 通信相手は通信相手 (エディタ) によらない

## Goの歴史
* gocode は，VScodeのコード補完候補を出していた
* gocode は，コード補完サーバー 兼クライアント
* テキストエディタは GO のソースコードを開くと同時にその拡張やプラグインがバックグラウンドで gocode を起動する
* gocode は Go でのコード補完機能のデファクトスタンダード
* nsf氏について知る必要がある
* go はバイナリとしてパッケージを保持する
* gocode はそのバイナリをパースし，コード補完を高速化することに成功した
* Go 1.10 のビルドキャッシュ（GO コンパイラがビルドした結果をキャッシュし保存する仕組み）
* gocode はキャッシュの位置を知ることができないため，pkg ディレクトリとキャッシュとの間で起きるコードの差異により，正しいコード補完結果を作ることができなくなった
* VS code が Language Server をサポートし始めた
* Go 言語にも go-langserver が誕生したが，それは gocode を用いるので，ビルドキャッシュ問題がのしかかる


# vscode でみんなが幸せになるためのバグレポートと機能リクエストの書き方

Issue の追加がハンパなく、それをさばく中の人も大変だなと思いつつ、自分も Issue にお世話になるので、[Contributing Issues](https://github.com/Microsoft/vscode/blob/master/CONTRIBUTING.md) を翻訳してみた。

初めて書いた Issue は、[Mac OS X Shortcut key: cmd + F1 (Move Focus to Next Window) not usable #5601](https://github.com/Microsoft/vscode/issues/5601) になり、 OS X 限定だけど、途中の build から cmd+F1 でウインドウ切り替えができなくなったのがとても不便だったから報告してみた。根本は Electron 側の bug だったけど、Electron 側で修正され、約半年後の VS code に反映されることになった。

というわけで、macOS で vscode 使いな方、vscode 1.6 は `cmd+F1` でウインドウ切り替えが戻ってくるよー



## ちょっと待って！ 問題を報告する前に

最初にやってみることは、すでに同じ問題の報告や機能のリクエストがないか [Open 状態になっている Issue](https://github.com/Microsoft/vscode/issues) を検索し確認してみることです。

最も人気のある機能要求を検索するには、この[クエリ](https://github.com/Microsoft/vscode/issues?q=is%3Aopen+is%3Aissue+label%3Afeature-request+sort%3Areactions-%2B1-desc)を使用します。

あなたが見つけた問題がすでに報告されていることが確認できた場合は、関連するコメントと[リアクション](https://github.com/blog/2119-add-reactions-to-pull-requests-issues-and-comments)を追加してください。
特にコメントすることがない場合でも、関連するコメントにリアクションを追加することをおすすめします。

👍 - 賛成票 (upvote)

👎 - 反対票 (downvote)

また、VS Code プロジェクトは、複数の Git リポジトリに分散されています。
正しい[関連プロジェクト](https://github.com/Microsoft/vscode/wiki/Related-Projects) のリポジトリに対して、再度、問題を提出してみるのも一つの方法です。

もし、あなたが抱えている問題について質問がある場合は、`vscode` タグを付けて [Stack Overflow](https://stackoverflow.com/questions/tagged/vscode) にも書き込んでみてください。

>**satokaz コメント**: [日本語版スタック・オーバーフロー](http://ja.stackoverflow.com) には `vscode` タグは存在しない

バグや機能追加に関する既存の報告を見つけることができなかった場合は、下記のガイドラインに従い Issue を作成してください。

## みんなが幸せになるためのバグレポートと機能リクエストの書き方

一つの Issue には一つの問題または機能リクエストを書いてください。

* 一つの Issue に複数のバグや機能リクエストを記載しないでください
* 同一の問題でない限り、既存 Issue のコメント欄に、あなたの Issue を追加しないでください。多くの問題は同じように見えるかもしれませんが、原因が異なる可能性があります。

私達を含む誰かが問題を再現してくれたり、修正を見つけてくれる可能性を高めるために、あなたは詳細な情報を報告することができます。
そのために必要となるのは:

* 再現手順、その手順を実行した結果、あなたが期待している動作結果
* 事象についての説明
* アニメーション GIF の利用
* 問題をコードで説明する場合は、ソースだけではなく画像も含んだコー​​ドの抜粋を記載してください
* 問題を確認した VS Code バージョン
* 開発ツール(Dev Tool) のコンソールに出力されるエラー (ヘルプ | 開発ツールの切り替え)
* 拡張機能がインストールされている場合は、`--disable-extensions` コマンドライン引数を使用して VS Code を起動してください。全ての拡張機能が無効になるので、この状態で問題が再現するか確認します

私達が問題を再現できなかったり、あなたにより多くの情報を求めたりすることに気を悪くしないでくださいね！

>**satokaz コメント**: 問題を修正し、修正されたことが何らかの方法で確認できた場合は、Issue の close と共に、`verified` タグをつけてくれる様になりました。修正の挙動を確認できたら報告してあげるだけでも中の人の負担が軽減されますし、これもコントリビューションかと思います

最後に、問題が報告された後、私達の取る作業については、 [issue tracking](https://github.com/Microsoft/vscode/wiki/Issue-Tracking) で説明しています。

## コードベースへの貢献について

VS Code の問題を修正したり、コードベースに直接的に貢献する事に興味を持って頂けたなら、次は、[How to Contribute](https://github.com/Microsoft/vscode/wiki/How-to-Contribute) を参照してください。



# 以下は、独自に追加したメモ。

## ライセンスについて

Visual Studio Code はオープンソースプロダクトとして紹介されるが、バイナリとソースコードに適用されるライセンスが異なることに注意。

- code.visualstudio.com から配布される Visual Studio Code Stable (青いヤツ)は、[MICROSOFT SOFTWARE LICENSE TERMS](https://code.visualstudio.com/license?lang=en) が適用される (日本語訳も用意されている: [マイクロソフト ソフトウェア ライセンス条項](https://code.visualstudio.com/license?lang=ja))
- code.visualstudio.com から配布される Visual Studio Code Insiders (緑のヤツ)は、[MICROSOFT PRE-RELEASE SOFTWARE LICENSE TERMS](https://code.visualstudio.com/license/insiders?lang=en) が適用され、こちらは翻訳されたものは提供しないというスタンス。  
また、Insiders build には、 90 日間のみ使用可能な期間が設定されている (新しい者がリリースされれば更新されるので、現在の daily build では、さほど問題にならないかと思う)

  > **TERM.** The term of this agreement is ninety days.

- エクステンションについては、[MICROSOFT SOFTWARE LICENSE TERMS](https://code.visualstudio.com/license?lang=en) ([マイクロソフト ソフトウェア ライセンス条項](https://code.visualstudio.com/license?lang=ja))及び [MICROSOFT PRE-RELEASE SOFTWARE LICENSE TERMS](https://code.visualstudio.com/license/insiders?lang=en) に次の一文が記載され、エクステンション作成者が独自にライセンスを適用することが可能。
  > `マイクロソフトは、第三者のパッケージについて、頒布、ライセンス許諾、または保証を一切行いません。` 

- https://github.com/microsoft/vscode リポジトリで公開されているソースコードは、[MIT license agreement](https://github.com/Microsoft/vscode/blob/master/LICENSE.txt) が適用される
- 上記のソースコードから作成されたバイナリは、Code - OSS と呼ばれ、ソースコード同様に [MIT license agreement](https://github.com/Microsoft/vscode/blob/master/LICENSE.txt?lang=ja) が適用される

ソースコードからビルドされたものは、Visual Studio Code そのものではなく、Code - OSS と呼ばれる。
バイナリで配布されている Visual Studio Code のフル機能は利用できるわけではないので注意。

毎月の `Code freeze for the endgame` を迎えた後、内部で Visual Studio Code として足りないモノ(オープンソースとして提供できないモノ？)を追加する build が行われ提供される感じ。

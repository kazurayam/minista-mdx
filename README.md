* minista mdx

Zennに投稿した記事 [スタティックサイトジェネレータ minista を試して見た](https://zenn.dev/kazurayam/articles/ae376ca6bff235) の続き。Markdown構文でページを書くことを試して見た。

## やったこと

pluginMdxのドキュメント https://minista.qranoko.jp/docs/plugins/mdx を読んだ

`my-minista-project/minista.config.js` ファイルを追加した

`my-minista-project/src/index.tsx`  を `index.mdx` にファイル名変更して、Markdown構文に書き替えた

`my-minista-project/src/about/index.tsx`  を `index.mdx` にファイル名変更して、Markdown構文に書き替えた

 bun run devしてみた。http://localhost:5173/ が404 Not Foundになった。

 https://github.com/kazurayam/minista-mdx/issues/1 を作った。

minista本家のドキュメントが `minista.config.js` を作れと書いているのを見つけた。これはおそらくministaのv4より前の仕様だ。v4.0.xでは `minista.config.js` を作ってはいけない。

minista本家のGitHubレポジトリのIssuesに https://github.com/qrac/minista/issues/147 を作った。

`vite.config.js` でpluginMdxとpluginImageを使うと宣言した。

`src/pages/about/index.tsx` を `index.mdx` に改名した。`index.mdx` をMarkdown構文に書き替えた。

`index.mdx` が `pluginImage` を使って画像をロードするようにした。

http://localhost:5173/about/ が正常な画面を応答した。

`bun run build` が成功した。

`bun run preview` によって http://localhost:4173/ として正常な静的サイトを閲覧することができた。

![/about/](https://kazurayam.github.io/minista-mdx/images/my-minista-project-09-02-2026_08_40_PM.png)

http://localhost:4173/ をMarkdown構文で書くことに成功した。 

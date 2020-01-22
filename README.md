# akari-level3-vr2.github.io

「ーSERVICEー」タグのレイアウトが崩れる原因について
　修正に至る経緯：


1.直前のコンテンツ：「.headmain-inner」を

display:flex;
flex-direction:column-revers;

にしていることが原因？
→因果関係不明。別の原因を探る。

2.直前の「コーディング上の」要素である「.heading-img」に、固定の幅・高さを設定しているから？

→該当画像に「.img-responsive」適用。
　width:560px;　→　max-width:560px;
   height:448px;　→  height:auto;
に変更。

→変化なし。因果関係無しと思われる。

3.直前のコンテンツ全体を囲っている「.head-main」の<section>タグは、レイアウトのためのコンテナのタグとしてふさわしくない？

（参考）
「http://www.htmq.com/html5/section.shtml

<section>タグを使用する際のポイント
1. レイアウト目的のコンテナ要素として用いるなら、<section>ではなく、<div>を使用してください。
2. その部分の意味を表す見出しを付けることができない場合には、<section>～</section>で囲むのは適切ではないかもしれません。
3. 上記二点をクリアしてセクションであることが明確な場合にも、より具体的な意味を持つ<article>、<aside>、<nav>のほうがふさわしい場合には、これらのタグを使用します。
」

→<section>タグを<div>タグに変更。

→解決には至らなかったが、

★「ーSERVICEー」は本来のコーディング順の直線要素である「.head-main」についてくることを確認。

→「.head-main」の高さを448pxに固定していたので「auto」に変更。

.head-main {
    width: 100%;
    height: auto;
}


→解決！！



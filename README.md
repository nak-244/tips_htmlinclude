## htmlファイルで共通箇所をインクルード
PHPなどのサーバーサイドスクリプトを使わずに、jQueryだけで簡単に外部htmlの内容をインクルードする方法を解説いたします。

例としてサイト共通のヘッダーをhtmlにインクルードする方法について解説いたします。


### header.html（読み込まれる側）

    <ul id="header-inner">
    　<li><a>ナビ1</a></li>
    　<li><a>ナビ2</a></li>
    　<li><a>ナビ3</a></li>
    </ul>

### index.html（読み込む側）

    <div id="header-outer">
    　<!--ここにインクルード-->
    </div>
    <div>
    　<h1>見出し</h1>
    　<p>本文本文本文本文本文本文本文本文本文</p>
    </div>

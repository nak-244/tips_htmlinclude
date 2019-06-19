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


**※htmlの文字コードはUTF-8にしてください。**

読み込む側のhtmlは、表示したい場所に任意のID(#header-outer)をつけたBOX要素を用意してください。  

読み込まれる側には、読み込んでほしい内容を書きます。今回の例ではヘッダーという事でナビゲーションをリスト形式で記述しています。そして読み込んで欲しい要素に任意のID（#header-inner）をつけます。このIDをつけた部分だけが読み込まれる事になりますので、その他に何が書いてあっても特に問題ありません。  

また今回の例では読み込まれる側をhtml形式にしましたが、txt形式でも問題ありません。

### javascriptの記述

<script type="text/javascript">
  $(function() {
    $("#header-outer").load("https://www.olp.co.jp/medical/inc/header.html #header-inner");
    $("#footer-outer").load("https://www.olp.co.jp/medical/inc/footer.html #footer-inner");
  })
</script>

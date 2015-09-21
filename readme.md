##Superblock for iOS9
2chまとめサイトなどの広告をすべて消せます。  
[Superblockをダウンロード](https://itunes.apple.com/us/app/superblock-guang-gaoburokku/id1041786553?l=ja&ls=1&mt=8)  

##使い方
**インストールするだけでは効きません。**設定アプリから  
「Safari」  
↓  
「コンテンツブロッカー」  
↓  
「Superblock」をオン  

にしてください  
  

##ドメイン指定
読み込みをブロックしたいURLのドメインを指定します  
サブドメインは全てマッチします  
例）  
zzz.aaa.jpやxxx.aaa.jpにマッチさせたい場合、aaa.jpだけを指定します  
  
入力する際はドメインごとに改行してください  
  
以下のドメイン指定リストもご利用ください  
1.[Weblock List for Japanese [iOS] [日本語] [domains]](http://cosmonote.blogspot.jp/2014/02/weblock-list-for-japanese-ios-domains.html?m=1)  
2.[アダルト広告ブロック](http://sugokunemui.github.io/superblock/domain.html)  
  

##カスタムフィルターを使う  
現在インポート機能などが無いため、カスタムフィルターを使う場合は注意が必要です  
すでに入力されているカスタムフィルターを全て消して空の状態にしてから、使いたいフィルターリストをペーストしてください  
すでに入っているものの下に追記していくとエラーが出る可能性があります  
  
以下のいずれかをお使いください  
1.[アダルト広告＆ポップアップブロック](http://sugokunemui.github.io/superblock/adult.html)  
  
今後複数のフィルターをインポートし統合する機能を追加します  
  

##カスタムフィルターを作る
この機能は上級者向けです  
WebkitのContent Blockersの仕様に従って記述します  
[Introduction to WebKit Content Blockers](https://www.webkit.org/blog/3476/content-blockers-first-look/)  
  
[テスト用サンドボックス](http://sugokunemui.github.io/superblock/sandbox.html)  

##Content Blockersの仕様について  
コンテンツブロッカーではフィルターをJSONで表します
このJSONはトップレベルに一つの配列があり、その中に複数のフィルターオブジェクトが入ります  
  
    [フィルター1, フィルター2, ...]  
  
よく使うのはURLブロックと要素非表示です  
  

###URLをブロックする  
URLをブロックする基本的なフィルターは  
```{  
	"action":{  
		"type":"block"
	},
	"trigger":{  
		"url-filter":".+/pop\\.js"
	}
}```
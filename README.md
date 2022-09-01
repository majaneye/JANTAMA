# JantamaViewerについて

このツールはじゃんたまの牌譜を解析して、４人麻雀の半荘（東風）のまとめを作成します。

牌譜のダウンロードについてはこちらのページを参照してください。  
https://github.com/majaneye/JANTAMA/wiki/%E7%89%8C%E8%AD%9C%E3%81%AE%E4%B8%80%E6%8B%AC%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89

現在、実装されているのは以下の機能です。
- 各局の結果表示（上がりまたは流局、点棒移動、立直、和了役）
- 点棒状況のグラフ表示
- 局毎の天鳳の牌譜エディタ用テキストへの変換
- 牌譜の再生（牌譜ビューワー）
- 放銃リスト
- スタッツの表示
- リーグ戦（チーム戦）機能
- akochan-reviewerでの解析・結果の表示機能 （ローカルにakochan-reviewerが必要です）  

## 使い方

自身の環境に合わせて、Win または Macのzipファイルをダウンロードしてください。  
解凍した先のPaifuフォルダにじゃんたまの牌譜（**牌譜の入手については後述**）を入れてください。  
牌譜はJantamaViewerを起動後に追加しても構いません。  
牌譜追加後に解析ボタンを押すと、牌譜を解析して半荘（東風）のまとめを作成します。  
各局のまとめをクリックすると、天鳳の牌譜エディタ用テキストをクリップボードにコピーします。  

### まとめに大会戦の名前を表示する
Settings/contest_id.txtにIDと名前を追加することで大会戦の名前を表示します。

### ドロップダウンリストにプレイヤー名を登録する
Settings/player_id.txtにIDと名前を追加することで検索用プレイヤー名を登録します。

### フォルダでフィルタリングを行う
Paifuフォルダ以下にフォルダを作成します。例えば、次のようなフォルダを作ります。  
ドロップダウンリストで”/Paifu/自分"を選択すると、"自分"フォルダ以下の牌譜がフィルタリングされます。  

Paifu/自分  
Paifu/自分/8月  
Paifu/自分/9月  

### リーグ戦、チーム戦のランキング表示

上部の【リーグ戦】タブを選択すると、指定フォルダ以下にある牌譜で、絞り込み条件に一致する牌譜の順位、持ち点からポイントを算出してランキングを表示します。  
ランキング表示は順位、プレイヤー名（チーム名）、ポイント、対局数を見ることができます。  
【pt集形式】のドロップダウンリストは順位と持ち点からのポイントの算出方法を指定します。  
↓のファイルに追加することが可能です。デフォルトは１番上の行です。  
Settings/Leagues/calc_base.txt

【集計対象】のドロップダウンリストは個人成績またはチーム成績としてまとめたものを表示するか切り替えます。  
個人成績の場合は、絞り込まれた牌譜に登場するプレイヤーが全てランキングに表示されます。  
チーム成績の場合は、 Settings/Leagues/team フォルダ以下にある「リーグ戦名」.txtに記述されたチームのメンバーの成績をまとめたものが表示されます。  
※チームとして記載してあると、対局数が0でもランキングに表示されます。  

「リーグ戦名1」.txt,「リーグ戦名2」.txtを作成すると、
ドロップダウンリストには[個人成績］,[リーグ戦名1］,[リーグ戦名2]が表示されます。

#### 「リーグ戦名」.txtの記述例  
じゃんたま愛好会.txt  
#チーム名,メンバー１のアカウントID,メンバー２のアカウントID,...  
チーム一姫推し,000000,0000001  
チーム二階堂推し,000002,0000003  
チームXXX,9999,3333,333333  

チーム数は何個でも大丈夫です。  
メンバー数は同じでなくても構いません。  
０人のチームやチームが一つも登録されていない場合については保証してないのでご注意ください。  

### akochan-reviewerでの解析・結果の表示　　

akochan-reviewerを使用して、解析した結果を牌譜ビューワーで表示できます。  
akochan-reviewerでの解析は１局単位で行いますが、私の環境では大体100秒くらいかかります。（局の長さに比例します）  
MacBook Pro (13-inch, 2016, Two Thunderbolt 3 ports)  
2 GHz デュアルコアIntel Core i5  
8 GB 1867 MHz LPDDR3  
Intel Iris Graphics 540 1536 MB  

akochan-reviewerについてはこちらのページを参照してください。   
https://github.com/Equim-chan/mjai-reviewer  

windowsはこちらの実行ファイルをDLしてJantamaViewerフォルダにおいてください。  
https://github.com/Equim-chan/mjai-reviewer/releases  
[akochan-reviewer-v0.7.1-windows-x86_64.zip](https://github.com/Equim-chan/mjai-reviewer/releases/download/v0.7.1/akochan-reviewer-v0.7.1-windows-x86_64.zip)  

macは実行ファイルが公開されていないので、ビルドが必要です。  
（勝手にアップしていいものか分からないので…）  


## 牌譜について

牌譜の一括ダウンロードの方法についてまとめました。

https://github.com/majaneye/JANTAMA/wiki/%E7%89%8C%E8%AD%9C%E3%81%AE%E4%B8%80%E6%8B%AC%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89  
こちらのページは【雀魂 API 解析にゃ！ Wiki*】様の情報を元に作成しました。  
（作成者様に感謝します。ファイルの解析でもとても参考になりました）

### 牌譜をファイルに保存するにゃ
https://wikiwiki.jp/majsoul-api/%E7%89%8C%E8%AD%9C%E3%82%92%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AB%E4%BF%9D%E5%AD%98%E3%81%99%E3%82%8B%E3%81%AB%E3%82%83

paifu()と入力してウィンドウを表示するより、paifu("雀魂牌譜: https://game.mahjongsoul.com/?paipu=UUID")とする方がちょっと楽でした。

## プレビュー

画像は神域リーグ様の牌譜をお借りして作成しました。

<img width="1069" alt="スクリーンショット 2022-08-08 4 17 10" src="https://user-images.githubusercontent.com/108359839/183307498-c29a527d-c3f7-4fb5-8c3d-0a63064617cd.png">
<img width="1069" alt="スクリーンショット 2022-08-08 4 17 19" src="https://user-images.githubusercontent.com/108359839/183307504-4ef378e9-99d4-4972-ab78-3b23ae669590.png">
<img width="1069" alt="スクリーンショット 2022-08-08 4 17 23" src="https://user-images.githubusercontent.com/108359839/183307509-06e4c607-88f0-4790-88e1-2675f04b2367.png">
<img width="1069" alt="スクリーンショット 2022-08-08 4 21 23" src="https://user-images.githubusercontent.com/108359839/183307544-9d07a023-0db7-41b0-8a4b-308f7306c874.png">
<img width="1067" alt="スクリーンショット 2022-08-24 2 54 25" src="https://user-images.githubusercontent.com/108359839/186340238-827793d1-5ade-444c-aebb-1626058dca75.png">

![JanatamaViewer 001](https://user-images.githubusercontent.com/108359839/187995444-b068b79c-269a-4cf3-8687-42807fb6b316.png)


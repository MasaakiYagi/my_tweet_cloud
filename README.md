# my_tweet_cloud
自分の過去のツイートを取得し、月次でwordcloud画像を生成するコード（いまのところ）

## **1.必要な準備**
### **1-1.TwitterAPIのTOKEN類取得**
下記を参考に、「API Key」、「API secret key」、「Access token」、「Access token secret」を取得する。  
https://wporz.com/twitterapi-apikey-accesstoken/  
その後、ディレクトリ直下に"settings.json"を作成し、下記のように記載する。  
~~~ json
{
    "API_KEY": "取得した値",
    "API_KEY_SECRET": "取得した値",
    "BEARER_TOKEN": "取得した値",
    "ACCESS_TOKEN": "取得した値",
    "ACCESS_TOKEN_SECRET": "取得した値",
    "CHASEN": "後述"
}
~~~

### **1-2.MeCabのダウンロード**
下記を参考にMeCabをインストールする。  
https://self-development.info/mecab%E3%82%92%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%97%E3%81%A6python%E3%81%A7%E4%BD%BF%E3%81%86%E3%80%90windows%E3%80%91/  
また、上述のsettings.jsonの"CHASEN"の値には下記のようにインストールしたMeCab辞書のパスを記載する。  
"[MeCabのインストールフォルダ]\\dic\\ipadic"  

### **1-3.フォントファイルの取得**
https://moji.or.jp/ipafont/ipaex00401/  
よりIPAexゴシックのフォントファイルを取得し、ルートディレクトリ直下に格納する。  
ファイル名称は"ipaexg.ttf"
### **1-4.python環境**
（後ほど記載。コード内でimportしているライブラリが必要）

## **2.使い方**
### **2-1.tweetの取得→csv保存**
get_all_tweet.ipynbを実行すると、/data/フォルダに取得したtweetがcsv形式で保存される。  
※ただし無料のTwitterAPIだと上限3200ツイート。
### **2-2.Wordcloudの生成**
draw_wordcloud.ipynbを実行すると、2-1で取得したcsvファイルをもとにしてWordcloud画像を月ごとに生成し、それらは/img/フォルダに保存される。

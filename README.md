* What's this  
  規則ファイルの設定に従ってファイルを振り分けたりリネームしたりする

* 実行方法  
  file_distributor.exe [ini ファイルのpath]
  * ini ファイルのpath  
  省略時には実行ディレクトリ直下のfile_distributor.ini を探す    　  


* ini ファイルの記述  
  - workpath に処理対象のファイルが保存されているフォルダのpath を記述
    - 振り分けする場合はこのフォルダ直下に振り分け先のフォルダも作成する
  - rulepath に規則ファイルのpath を記述  
    - ファイルで終わってるときはそのファイル名を採用
    - フォルダで終わってるときは実行日付に応じたデフォルトのファイル名を採用  
      - デフォルトのファイル名は、西暦+Q+4半期+".txt"  
      　Ex.) 2014年7月1日～9月30日 に実行したときは2014Q3.txt になる


* 規則ファイル の書式
  - 検索文字列, 置き換え文字列, 振り分けフォルダ名
    - 必須：検索文字列
    - いずれかが必須：置き換え文字列, 振り分けフォルダ名


* 挙動
  - 置き換え文字列のみ  
ヒットした検索文字列部分を置き換え文字列で置換する
  - 振り分けフォルダのみ  
検索文字列をファイル名に含むファイルを振り分けフォルダに移動する
  - 置き換え文字列・振り分けフォルダの両方  
    上記の両方の処理を行う  


* 追加必要なPackage
  * gcfg  
    $ go get code.google.com/p/gcfg
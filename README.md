# MIRROR4D
4DのデータをHTTP越しにミラーリングします。
***
"On Server Startup" を以下のように実装します。( ミラー元&ミラー先共通でOK )  
![mirror4d_onserverstartup](https://user-images.githubusercontent.com/4927926/201840456-a8a2825e-ba99-4746-af95-9976270434dc.png)

"On Web Connection" に以下のように実装します。( ミラー元&ミラー先共通でOK )  
![mirror4d_onwebconnection](https://user-images.githubusercontent.com/4927926/201840484-8fe6ab20-80cf-4c73-888e-a765dd175f3f.png)

# Resources&yen;mirror_setting.txt
起動時に  
"Resources&yen;mirror_setting.txt"  
が生成されるので以下のように修正する。  
※ ミラー元を修正し、さらに修正後のコピーを修正してミラー先に設置する。

## ミラー元
#### "is_mirror" ( 重要 )
必ず false とする。  
#### "interval_sec"
同期インターバル(秒) ( 初期値 "0" )  
#### "interval_min"
同期インターバル(分) ( 初期値 "2" )  
#### "interval_hour"
同期インターバル(時間) ( 初期値 "0" )  
#### "journal_to"
分割ジャーナルの一時保管場所(データフォルダからの相対パス) ( 初期値 "journal_divided&yen;" )  
#### "journal_url_download" ( 重要 )
何でもよいが少なくとも初期値 "http://127.0.0.1/mirror/download" のうち "http://127.0.0.1" の部分は必ずミラー元サーバに該当する値に書き換えること。  
#### "journal_url_complete" ( 重要 )
何でもよいが少なくとも初期値 "http://127.0.0.1/mirror/complete" のうち "http://127.0.0.1" の部分は必ずミラー元サーバに該当する値に書き換えること。  
#### "mirrors" ( 重要 )
ミラー先サーバのIPアドレス配列を設定する。

## ミラー先
#### "is_mirror" ( 重要 )
必ず true とする。  

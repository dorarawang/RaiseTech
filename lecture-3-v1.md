# 課題３提出-V1

**起動できました**
![deploy success](deploy.png)

## 1. AP サーバーについて調べる

> AP サーバーの名前とバージョンを確認してみましょう。

**Ans: Puma, 6.4.2**
![puma version](deploy-2.png)


> AP サーバーを終了させた場合、引き続きアクセスできますか？

**Ans:不可。**

## 2.DB サーバーについて調べる

> サンプルアプリケーションで使った DB サーバー（DB エンジン）の名前と、<br/> 今 Cloud9 で動作しているバージョンはいくつか確認してみましょう。

**Ans: Mysql community server 8.4.3**
![db version](database-5.png)

>  DB サーバーを終了させた場合、引き続きアクセスできますか？

**Ans: 不可。**
![db out](database-3.png)

> Rails の構成管理ツールの名前は何でしたか？

**Ans: Bundler**

## 3. 今回の課題から学んだこと、感じたこと

* 課題がわからない時とりあえず動画をこまめに確認してみること
* Pumaを起動しようとしたときに、puma.rbファイルやpuma.serviceの場所が違うって、うまく起動できなかったことがありました。
  パスを修正しても、rubyの反応時間が長すぎで、切れたこともありました。
もう一度動画を研究したら、cloud9までの起動で、アプリのdeployができていたそうでした。実行したらいけました。 資料の最後にpumaを起動するStepは何のためでしょうかね。
* また、起動の手順をどこかで間違ったら「Pumaが利用したいportがすでに使用されているため、起動できない」の状態になってしまいます。 ChatGPTに聞いて、下記を試しましたが、削除する次第、すぐ自動的にrestartされるようで、解決できなかった。
  > sudo kill -9
  > ps aux | grep puma
  > rm /home/ec2-user/environment/raisetech-live8-sample-app/tmp/pids/server.pid

  こうなったたびインスタンスをストップさせ、接続し直し、やり直したら正常に起動できるようになりました。


* 動画の中にrvm use 3.2.3がうまく動作できない原因を調べたら、こちらのコードが必要だそうです。
　> source ~/.rvm/scripts/rvm
  なんかrvmがインストールできたとしても、使っているshellにも読み込ませないと行けないため、毎回これを実行しないとrvm機能が使えなさそうだ。

* yarnをインストールするため、node.js も必要だった。
  > *because Yarn is a package manager for JavaScript projects, and it heavily relies on Node.js*

*  Githubで提出しないといけないので、課題2の復習にもなった。

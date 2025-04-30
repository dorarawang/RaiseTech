# 課題６
## 1.  CloudTrailからイベント内容の報告
**イベント名：** "UpdateInstanceInformation"\
**"awsRegion":** "ap-northeast-1"\
**"userIdentity":** ユーザーを特定できる諸情報 *(画像参考)*\
**"eventTime":** "2025-04-30T16:30:39Z"

## 2.  CloudWatch Alarmの設定
1. "UnhealthyStateRouting"というmetricをAlarmに追加
1. Amazon SNSを設定（Topicを作成した）
1. サイトは通常通りに動作していることを確認
1. Nginxを停止
1. サイトが動かなくなっている
1. ５分後にAlarmが発火され（無料で利用できる検知頻度は最短５分間隔のため）
1. 通知メールが届いている
1. Nginxを再起動させたらAlarmがOKに戻った

## 3. AWS 利用料の見積作成
今まで作成していた環境のスペックを基づいて作成してみました。\
Amazonの一年間無料サービスがなければ一年間はこのぐらいかかるのは少しびっくりしました。\
RDSの利用について、利用者数が平均１日三人程度で見積もっています。（ChatGbtに相談）。\
使っていたサービスを全部入れるつもりでしたが、正しく見積もっているかどうかが自信がないです。\
[見積もりリンク](https://calculator.aws/#/estimate?id=533fdd5ab5b09d1949dedf923302b3bcf3de120d)

## 4.　先月の利用料金状況
ALBの利用で0.06ドルほど請求されています。\
コストを抑えるためになるべく使わないときにALBを削除したり、EC2をストップさせたりするように意識していました。

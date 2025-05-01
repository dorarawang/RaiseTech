# 課題６
## 1.  CloudTrailからイベント内容の報告
**イベント名：** "UpdateInstanceInformation"\
**"awsRegion":** "ap-northeast-1"\
**"userIdentity":** ユーザーを特定できる諸情報 *(画像参考)*\
**"eventTime":** "2025-04-30T16:30:39Z"

![db out](HW6-cloudtrail-1.png)
![db out](HW6-cloudtrail-2.png)

## 2.  CloudWatch Alarmの設定
1. "UnhealthyStateRouting"というmetricをAlarmに追加
![db out](<HW6-set-up-alarm2.png>)
1. Amazon SNSを設定（Topicを作成した）
![db out](HW6-set-up-sns.png)
1. サイトは通常通りに動作していることを確認
![db out](<HW6-good site.png>)
1. Nginxを停止
![db out](<HW6-stop-nginx.png>)
1. サイトが動かなくなっている
![db out](<HW6-bad site.png>)
1. ５分後にAlarmが発火され（無料で利用できる検知頻度は最短５分間隔のため）
![db out](<HW6-unhealthy-state-routing.png>)
1. 通知メールが届いている
![db out](<HW6-unhealthy-state-routing-mail.png>)
1. Nginxを再起動させたらAlarmがOKに戻った
![db out](<HW6-unhealthy-state-routing-alarm-ok.png>)

## 3. AWS 利用料の見積作成
今まで作成していた環境のスペックを基づいて作成してみました。\
Amazonの一年間無料サービスがなければ一年間はこのぐらいかかるのは少しびっくりしました。\
RDSの利用について、利用者数が平均１日三人程度で見積もっています。（ChatGbtに相談）。\
使っていたサービスを全部入れるつもりです。ただ、あっているかどうか少し不安です\
[見積もりリンク](https://calculator.aws/#/estimate?id=533fdd5ab5b09d1949dedf923302b3bcf3de120d)

## 4.　先月の利用料金状況
0.06ドルほど請求されています。\
利用明細によるとVPCのIP4 public addressの料金だそうです。\
おそらくALBの利用料金だと思っています。
コストを抑えるためになるべく使わないときにALBを削除したり、EC2をストップさせたりするように意識していました。
![db out](<HW6-cost-April.png>)

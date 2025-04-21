# Lecture-4

講義の手順通りにVPとEC2、RDSを作成して、連携させました。
SSH clientでリンクしました。

![db out](L4-screenshot10.png)

## 補足：
作成したリソースのエビデンスを追加いたしました。
* **EC2インスタンスーRaisetech-L4:**
![db out](L4-screenshot3.png)
* **RDS:**
![db out](L4-screenshot4.png)
* **VPC:**
![db out](L4-screenshot5.png)


## 補足20250309
* **作成したVPCのサブネットにEC2が作成されていること:**
![db out](L4-screenshot6.png)

* **作成したVPCのサブネットにRDSが作成されていること:**
![db out](L4-screenshot7.png)

## 20250318修正
* **EC2にアタッチしているsecurity group(rule)の設定:** <br>
1. 重複しているSGを削除しました。
1. inbound rulesを追加しました:SSHで自宅のipアドレスからしかアクセスできないように設定しました。
![db out](L4-screenshot11.png)

* **RDSにアタッチしているsecurity group(rule)の設定:** <br>
1. 重複しているSGを削除しました。
![db out](L4-screenshot12.png)
![db out](L4-screenshot13.png)


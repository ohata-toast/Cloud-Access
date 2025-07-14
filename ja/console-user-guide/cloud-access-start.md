# Cloud Access 開始ガイド

**セキュリティ > Cloud Access > コンソール使用ガイド > Cloud Access開始**

<br>

## コンソール設定

エージェントの準備が完了したら、Cloud Accessサービスを使用するために接続設定とルート設定を行います。

<br>

### 設定情報の保存

接続設定情報を入力して保存します。保存後、Cloud Accessを使用できます。

![setting_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/setting_1.png)

* VPCとサブネットを選択します。
    * VPCやサブネットがない場合は、NHN Cloudコンソールの**VPC**または**Subnet**メニューから作成してください。
* 顧客名を入力します。
    * 日本語、英語、数字、および一部の記号（-、_、.）が使用可能です。
* アルゴリズムを選択します。
    * AES-256とChaCha20をサポートしています。

<br>

## ルート設定

外部エージェントを使用して接続したユーザーが内部インスタンスにアクセスできるよう、ルートを構成します。
例：ユーザーIP割当範囲が10.0.0.0/24、選択したサブネットが172.16.0.0/24、アクセス可能範囲も同じ場合、VPCルートに以下のルールを追加します。

* 宛先CIDR: 10.0.0.0/24
* ゲートウェイ: Virtual_IPタイプのTRAFFIC_SUBNET_INTERFACE_VIP

<br>

!!! danger "注意"
    * 設定情報を保存する前に、選択したVPCがインターネットゲートウェイに接続されているか確認してください。
        * 接続されていない場合、Cloud Accessは使用できません。
    * ユーザーIP割当範囲は以下と重複してはいけません：
        * 接続設定時に選択したサブネット
        * アクセス可能なネットワーク範囲

<br>

## エージェントのダウンロード

Cloud Accessサービスを利用するためのエージェントをダウンロードします。対応OSは以下の通りです。

* Windows 10 1903以上(32bit / 64bit)
* Windows 11(64bit)
* macOS 13.3以上

### [Windows版ダウンロード(64bit)](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_6b5ee6a5d2584600b5ffd3330de1846b/windows/installer/CloudAccess_Setup_x64.exe)

### [Windows版ダウンロード(32bit)](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_6b5ee6a5d2584600b5ffd3330de1846b/windows/installer/CloudAccess_Setup_x86.exe)

### [macOS版ダウンロード](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_6b5ee6a5d2584600b5ffd3330de1846b/macos/CloudAccess%20Installer%20v0.0.1-5309-DEV.dmg)

<br>

## 接続設定

### 接続の追加

NHN Cloudリソースに接続するための項目を追加します。

![conncetion_add_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/connection_add_1.png)

➊ ドメイン、➋ 顧客キー、➌ 秘密キーをNHN Cloudコンソールの権限を持つユーザーから受け取り入力します。

<br>

![conncetion_add_3.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/connection_add_3.png)

➍ 「検証」ボタンをクリックし、検証完了後、➎ 顧客名が表示されます。その後、「追加」をクリックして接続を完了します。

### 接続の削除

接続項目をクリックすると、「削除」ボタンが有効になり、追加した接続を削除できます。

<br>

!!! tip "ポイント"
    * 接続追加に必要な値は、NHN Cloudコンソールの権限を持つユーザーから取得してください。
        * 顧客名は検証後、管理者が設定した名前が自動で表示されます。
    * 複数の接続項目を追加可能ですが、有効なのは1つのみです。

<br>

## 認証によるトンネル接続

接続が必要な項目を選択し、**接続**をクリックして認証を行います。

### 案内表示

* 管理者が設定した案内メッセージを表示します。
    * **設定 > 案内設定**が無効な場合は表示されません。

### 第1段階認証（アカウントとパスワード）

![login_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/login_1.png)

* アカウント名：管理者から発行されたアカウントを入力します。
* パスワード：メールで届いた初期パスワードを入力します。

### 個人情報収集・利用同意
* Cloud Accessサービス運用のため個人情報を収集します。
    * 拒否した場合はサービス利用が制限されます。

### 追加認証

* 第1段階完了後、設定された認証ポリシーに従って追加認証を実施します。 
    * サポートする認証方法：
        * メール
        * 携帯電話 
        * TOTP（ワンタイムパスワード） 
        * 生体情報（パスキー） 

### 初期パスワードの変更

* 初期パスワードを変更します。
    * 管理者が設定したパスワードポリシーに従って変更してください。

<br>

!!! tip "ポイント"
    * アカウント作成後、登録されたメールアドレスに初期パスワードが送信されます。
    * 初回認証時のみ個人情報同意画面が表示され、接続完了で同意されたと見なされます（認証を完了しないと再同意が必要）。
    * 以下のパスワード制約は常に適用されます：
        * 6～30文字以内
        * アカウントIDと同一のパスワードは不可

<br>

## エージェントのトレイ機能

エージェントのトレイアイコンから利用できる機能です。

<br>

### 接続前
 * 開く：接続画面を表示
 * 接続：接続項目を表示
 * アップデート確認：バージョン確認および更新
* バージョン情報：ライセンスとプライバシーポリシーを表示
 * 設定：環境設定と言語設定
      * クラウド設定：パブリック or プライベート選択
      * 言語：韓国語、日本語、英語
 * 終了：エージェントを終了

### 接続後
* 顧客名とアカウント名が表示
* 開く：接続項目表示
* 接続解除：接続解除
* お知らせ：通知内容表示（通知が設定されていない場合もあり）
* バージョン情報：バージョン・ライセンス表示
* 終了：エージェントを終了
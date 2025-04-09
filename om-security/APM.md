# 外形監視を設定してみよう
# 問題
サービスの成長に伴い、お客様から「遅い」、「接続しにくい」といった問い合わせが増えてきました。
インフラ、アプリケーションの内部リソースの監視のみでは、上記のような問い合わせに対して、プロアクティブな対応が難しい状況です。
その対応として、外形監視の設定をあたらに追加し、アプリケーションの障害をお客様からの連絡より前に検知する対策を実施しようと検討しています。
Oracle Cloud Observability and ManagementのAPMの機能を活用し、外形監視を実装してください。

前提条件
- APMドメインは、OCI_Quest_XXを利用してください。

設定要件
- モニター定義
   - 名前： OCI_Quest_XX (XXはチーム番号)
   - タイプ：Browser
   - ベースURL ： https://xxxx.xxxxx
   - レスポンス・コード：200
- 実行設定
  - バンテージ・ポイント：Japan Central(Osaka)
  - 頻度：間隔
  - スケジュール・ポリシー：All
  - 実行間隔 (分) ：10分
  - タイムアウト (分) ：1分
  - 失敗時に再試行：チェック

# 解答
- APM → 可用性モニタリング → リソースを選択
  - 画面起動後、対象チームのAPMドメインを選択 → OCI_Quest_XX (XXはチーム番号)

![モニターの作成](om-security/images/APM-monitor/APM_Monitor1.png "モニターの作成")


!(om-security/images/APM-monitor/APM_Monitor1.png)





# Web Application FirewallのログをLogging Analyticsで分析できるようにしよう (所要時間：20分程度)
# 問題
「Webアプリケーションの脆弱性を狙ったサイバー攻撃の対策をしよう」の課題で、Web Application Firewall(以下 WAF)を構築しました。
構築後、攻撃の可視化と検出、誤検知の調整をするため、WAFのログを参照、分析できる仕組みを準備する必要があります。下記要件を満たすことができるように設定を実施してください。

本問題開始時の前提条件
- Webアプリケーションの脆弱性を狙ったサイバー攻撃の対策の問題が完了していること

実現したい要件
- WAFのログをLogging Analyticsで可視化する仕組みを構築する

設定時の条件について
- コネクタ・ハブはコンパートメントにあるものを使用してください
 
設定後の確認
- 「監視および管理」→ 「ログ・アナリティクス」→「ログ・エクスプローラ」を選択し、WAFのログが収集されていることを確認してください
  

# 解答
- アイデンティティとセキュリティ→ Webアプリケーション・ファイアウォールを選択
  - 画面起動後、作成したWebアプリケーション・ファイアウォールを選択
 
![Wafの設定](images/WAF/WAF_Log01.png "Wafの設定") 

- 「ファイアウォール」を選択

![Wafの設定](images/WAF/WAF_Log02.png "Wafの設定") 

- 「ファイアウォール名」を選択

![Wafの設定](images/WAF/WAF_Log03.png "Wafの設定") 

- 「ログ」を選択

![Wafの設定](images/WAF/WAF_Log04.png "Wafの設定")

- 「ログの有効化」から有効化

![Wafの設定](images/WAF/WAF_Log05.png "Wafの設定")

- 「新規グループの作成」を選択

![Wafの設定](images/WAF/WAF_Log06.png "Wafの設定")

- 「名前」に任意のログ・グループ名を入力し、「作成」を選択

![Wafの設定](images/WAF/WAF_Log07.png "Wafの設定")

- 「ログの有効化」を選択

![Wafの設定](images/WAF/WAF_Log08.png "Wafの設定")

- アクティブな状態になることを確認

![Wafの設定](images/WAF/WAF_Log09.png "Wafの設定")

- 「監視および管理」→ 「ロギング」→「コネクタ」を選択

![Wafの設定](images/WAF/WAF_Log13.png "Wafの設定")

- 作成されているコネクタを選択

![Wafの設定](images/WAF/WAF_Log21.png "Wafの設定")

- 「編集」を選択

![Wafの設定](images/WAF/WAF_Log22.png "Wafの設定")

- 編集画面で「別のログ」を選択

![Wafの設定](images/WAF/WAF_Log23.png "Wafの設定")

- 下記情報を入力
     - コンパートメント名 (チームに割り当てられたコンパートメント)
     - ログ・グループ (本問題で作成したLoggingのログ・グループ)
     - ログ (本問題で有効化したログ名)

![Wafの設定](images/WAF/WAF_Log24.png "Wafの設定")

- デフォルト・ポリシーの「作成」を選択

![Wafの設定](images/WAF/WAF_Log16.png "Wafの設定")

- ポリシーが作成されたことを確認し、「変更の保存」を選択

![Wafの設定](images/WAF/WAF_Log17.png "Wafの設定")

- コネクタがACTIVEになることを確認

![Wafの設定](images/WAF/WAF_Log18.png "Wafの設定")

- 「監視および管理」→ 「ログ・アナリティクス」→「ログ・エクスプローラ」を選択

![Wafの設定](images/WAF/WAF_Log19.png "Wafの設定")

- ログが収集できていることを確認

![Wafの設定](images/WAF/WAF_Log20.png "Wafの設定")






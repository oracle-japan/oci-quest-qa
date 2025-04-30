# Web Application FirewallのログをLogging Analyticsで分析できるようにしよう (所要時間：20分程度)
# 問題
Webアプリケーションの脆弱性を狙ったサイバー攻撃への対策としてWeb Application Firewallを構築しました。
構築後、Web Application Firewallのログを確認し、


実現したい要件
- 下記条件に該当するアクセスがあった場合は、401コードを返却する
   - 日本以外の国からのアクセスがあった場合
   - 1秒以内に同一のIPアドレスから100回以上アクセスがあった場合
   - SQLインジェクションの脅威を受けた場合

設定内容 (基本情報以外は、上記要件を満たすことができるように調査して設定してください)
- 基本情報
  - 名前： OCI_Quest_XX (XXはチーム番号)
  - WAFポリシー・コンパートメント：チームのコンパートメントを選択

- アクセス制御
  - 日本以外の国からのアクセスがあった場合に、401コードを返却する設定を実施

- レート制限
  - 1秒以内に同一のIPアドレスから100回以上アクセスがあった場合に、401コードを返却する設定を実施

 - 保護
   - SQLインジェクションの脅威を受けた場合に、401コードを返却する設定を実施

 - 強制ポイントの選択
   - チームのコンパートメント内にあるロードバランサーを選択


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

- 「監視および管理」→ 「管理」を選択

![Wafの設定](images/WAF/WAF_Log10.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log11.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log12.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log13.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log14.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log15.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log16.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log17.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log18.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log19.png "Wafの設定")


![Wafの設定](images/WAF/WAF_Log20.png "Wafの設定")






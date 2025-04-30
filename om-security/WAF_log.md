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
  - 画面起動後、ポリシーを選択
 
![Wafの設定](images/WAF/WAF_Log01.png "Wafの設定") 

- 「WAFポリシーの作成」を押下し、「基本情報」に関する情報を入力

![Wafの設定](images/WAF/WAF_Log02.png "Wafの設定") 

- 「次」を押下し、「アクセス制御の有効化」にチェックをいれ、「アクセス制御」に関する情報を入力

![Wafの設定](images/WAF/WAF_Log03.png "Wafの設定") 

- 「次」を押下し、「レート制限ルールの構成の有効化」にチェックをいれ、「レート制限」に関する情報を入力

![Wafの設定](images/WAF/WAF_Log04.png "Wafの設定")

- 「次」を押下し、「保護ルールの構成の有効化」にチェックをいれ、「保護」に関する情報を入力

![Wafの設定](images/WAF/WAF_Log05.png "Wafの設定")

![Wafの設定](images/WAF/WAF_Log06.png "Wafの設定")

![Wafの設定](images/WAF/WAF_Log07.png "Wafの設定")

- 「次」を押下し、「強制ポイントの選択」に関する情報を入力

![Wafの設定](images/WAF/WAF_Log08.png "Wafの設定")

- 「次」を押下し、「確認および作成」で設定内容を確認し、「WAFポリシーの作成」を選択

![Wafの設定](images/WAF/WAF_Log09.png "Wafの設定")

- 作成されたポリシーを選択し、正常に作成できていることを確認

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






# Grafana ダッシュボード作成ハンズオン

## ハンズオンのゴール

このGrafanaハンズオンでは、参加者がGrafana Cloudの基本操作を学び、TestDataソースを活用してデータ可視化の基礎を習得します。グラフ、ゲージ、テーブルなど多様なビジュアライゼーションの作成と設定を通じて、効果的なダッシュボードの構築方法を体験します。さらに、変数を用いた動的なダッシュボード作成や、作成したダッシュボードの保存・共有方法も学びます。これにより、参加者は実際の業務や個人プロジェクトでGrafanaを活用するための基礎的なスキルと知識を獲得し、データ駆動の意思決定に貢献できる能力を身につけることができます。

- Grafana Cloudの基本的な操作とナビゲーション
- TestDataソースを使用したデータの可視化
- 複数のタイプのビジュアライゼーション（グラフ、ゲージ、テーブルなど）の作成と設定
- ダッシュボードの構築とカスタマイズ
- 変数を用いた動的なダッシュボードの作成
- ダッシュボードの保存と共有の方法


## 事前準備

今回のハンズオンでは、Grafana環境として[Grafana Cloud](https://grafana.com/ja/products/cloud/)を利用します。ハンズオンの利用範囲では無料での利用が可能です。

### アカウントセットアップ方法

[Sign Up \- Create User](https://grafana.com/auth/sign-up/create-user?pg=login)、アカウントを登録します。

![alt text](../images/createa_account.png)

作成するStack名とリージョン（特にこだわりがなkれば、JapanでOK）を選択し、セットアップを完了します。

![setup stack](../images/setup_stack.png)

既にGrafana Cloudのアカウントをお持ちの方は、そのままサインインしてください。



 





## 1. はじめに

このハンズオンでは、Grafanaを使用してダッシュボードを作成する基本的なスキルを学びます。TestDataソースを使用して、様々なタイプのビジュアライゼーションを作成し、ダッシュボードをカスタマイズする方法を学びます。

所要時間：約100分

## 2. Grafana Cloudへのログイン

1. ブラウザで Grafana Cloud にアクセスします。
2. 提供されたアカウント情報を使用してログインします。

![Grafanaログイン画面](../images/setup/grafana-login.png)

## 3. TestDataソースの設定

1. 左側のメニューから「設定」（歯車アイコン）をクリックします。
2. 「Data Sources」を選択します。
3. 「Add data source」をクリックします。
4. リストから「TestData DB」を選択します。
5. 設定画面の下部にある「Save & Test」をクリックします。

![TestDataソース設定](../images/setup/testdata-config.png)

## 4. 最初のダッシュボードの作成

1. 左側のメニューから「Create」（＋アイコン）をクリックし、「Dashboard」を選択します。
2. 「Add new panel」をクリックします。

![新規ダッシュボード作成](../images/dashboards/create-dashboard.png)

## 5. グラフパネルの作成

1. データソースとして「TestData DB」を選択します。
2. Scenarioで「CSV Metric Values」を選択します。
3. 「Refresh」ボタンをクリックしてプレビューを更新します。
4. パネルのタイトルを「TestData Graph」に変更します。
5. 右上の「Apply」をクリックしてパネルを保存します。

![グラフパネル設定](../images/visualizations/graph-settings.png)

## 6. ゲージパネルの追加

1. ダッシュボード上部の「Add panel」をクリックします。
2. 「Visualization」で「Gauge」を選択します。
3. データソースとして「TestData DB」を選択します。
4. Scenarioで「Random Walk」を選択します。
5. パネルのタイトルを「Random Walk Gauge」に変更します。
6. 「Apply」をクリックして保存します。

![ゲージパネル設定](../images/visualizations/gauge-settings.png)

## 7. テーブルパネルの追加

1. 再度「Add panel」をクリックします。
2. 「Visualization」で「Table」を選択します。
3. データソースとして「TestData DB」を選択します。
4. Scenarioで「CSV Content」を選択します。
5. パネルのタイトルを「CSV Data Table」に変更します。
6. 「Apply」をクリックして保存します。

![テーブルパネル設定](../images/visualizations/table-settings.png)

## 8. ダッシュボードのカスタマイズ

1. ダッシュボード上部の「Dashboard settings」（歯車アイコン）をクリックします。
2. 「General」タブでダッシュボードのタイトルを「My First Grafana Dashboard」に変更します。
3. 「Variables」タブをクリックし、「Add variable」を選択します。
4. 新しい変数を以下のように設定します：
   - Name: `scenario`
   - Type: Query
   - Data source: TestData DB
   - Query: `scenarios()`
5. 「Add」をクリックして変数を追加します。
6. ダッシュボード設定を閉じ、各パネルの設定を開いて、Scenarioの選択に `$scenario` を使用するように変更します。

![ダッシュボード設定](../images/dashboards/dashboard-settings.png)

## 9. ダッシュボードの保存と共有

1. ダッシュボード上部の「Save dashboard」（ディスクアイコン）をクリックします。
2. 保存ダイアログで必要な情報を入力し、「Save」をクリックします。
3. 「Share dashboard」（リンクアイコン）をクリックし、様々な共有オプションを確認します。

![ダッシュボード共有](../images/dashboards/dashboard-share.png)

## 10. まとめ

おめでとうございます！これであなたは以下のスキルを習得しました：

- Grafana Cloudへのログインと基本的なナビゲーション
- TestDataソースの設定
- 異なるタイプのビジュアライゼーションの作成（グラフ、ゲージ、テーブル）
- ダッシュボードのカスタマイズと変数の使用
- ダッシュボードの保存と共有

次のステップとして、他のデータソースの探索や、より高度なダッシュボード機能の学習をお勧めします。

## 追加リソース

- [Grafana公式ドキュメント](https://grafana.com/docs/)
- [Grafana Tutorials](https://grafana.com/tutorials/)
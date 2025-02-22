# 条件判断

プログラミング言語の `if` 文に類似しており、設定された条件の判断結果に基づいて後続のフローを決定します。

## ノードの作成

条件判断には、「‘はい’で続行」と「‘はい’と‘いいえ’でそれぞれ続行」の2つのモードがあります。ノードを作成する際には、これらのモードのいずれかを選択する必要があり、その後ノードの設定では変更できません。

![条件判断_モード選択](https://static-docs.nocobase.com/3de27308c1179523d8606c66bf3a5fb4.png)

「‘はい’で続行」モードでは、条件判断の結果が「はい」の場合、フローは後続のノードを実行し続けます。そうでない場合、フローは終了し、失敗の状態で早期に退出します。

![“はい”で続行モード](https://static-docs.nocobase.com/0f6ae1afe61d501f8eb1f6dedb3d4ad7.png)

このモードは、条件が満たされない場合にフローを続行しないシナリオに適しています。たとえば、「操作前イベント」にバインドされたフォームの送信ボタンが注文を提出する場合、対応する商品の在庫が不足しているときは、注文を生成せずに失敗します。

「‘はい’と‘いいえ’でそれぞれ続行」モードでは、条件ノードの後に2つの分岐フローが生成され、それぞれ条件判断の結果が「はい」と「いいえ」の場合のフローに対応します。この2つの分岐フローはそれぞれ後続のノードを設定でき、どちらかの分岐が完了した後、自動的に条件ノードの上位分岐に合流し、後続のノードの実行を続けます。

![“はい”と“いいえ”でそれぞれ続行モード](https://static-docs.nocobase.com/974a1fcd8603629b64ffce6c55d59282.png)

このモードは、条件が満たされた場合と満たされない場合に、フローが異なる操作を実行するシナリオに適しています。たとえば、特定のデータが存在するかどうかを確認し、存在しない場合は追加し、存在する場合は更新します。

## ノード設定

### 演算エンジン

現在、3つのエンジンをサポートしています：

- **基本**：単純な二項計算と「かつ」、「または」でグループ化し、論理結果を得ます。
- **Math.js**：[Math.js](https://mathjs.org/) エンジンがサポートする式を計算し、論理結果を得ます。
- **Formula.js**：[Formula.js](https://formulajs.info/) エンジンがサポートする式を計算し、論理結果を得ます。

これらの計算においては、プロセスコンテキストの変数を使用して計算のオペランドとすることができます。

## 例

### 「‘はい’で続行」モード

<!-- TODO -->

### 「‘はい’と‘いいえ’でそれぞれ続行」モード

<!-- TODO -->


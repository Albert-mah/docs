# テンプレート印刷

<PluginInfo commercial="true" name="action-template-print"></PluginInfo>
<style>
.markdown h4 {
    font-size: 18px;
    font-weight: 500;
}
</style>

## はじめに

テンプレート印刷プラグインは、Word、Excel、PowerPoint（`.docx`、`.xlsx`、`.pptx`形式をサポート）でテンプレートファイルを編集し、テンプレート内にプレースホルダーと論理構造を設定し、`.docx`、`.xlsx`、`.pptx`、PDFファイルなどの事前フォーマットされたファイルを動的に生成できる強力なツールです。このプラグインは、見積書、請求書、契約書などの様々なビジネス文書の生成に広く使用され、文書生成の効率性と精度を大幅に向上させます。

### 主な機能

- **マルチフォーマットサポート**: Word、Excel、PowerPointテンプレートに対応し、異なる文書生成ニーズに応えます。
- **動的データ入力**: プレースホルダーと論理構造を通じて、文書内容を自動的に入力・生成します。
- **柔軟なテンプレート管理**: テンプレートの追加、編集、削除、分類をサポートし、保守と使用を容易にします。
- **豊富なテンプレート構文**: 基本的な置換、配列アクセス、ループ、条件出力などのテンプレート構文をサポートし、複雑な文書生成ニーズに対応します。
- **フォーマッターサポート**: 条件出力、日付フォーマット、数値フォーマットなどの機能を提供し、文書の可読性と専門性を向上させます。
- **効率的な出力形式**: PDFファイルの直接生成をサポートし、共有と印刷を容易にします。

## インストール

<embed src="./install.md"></embed>

## 設定手順

### テンプレート印刷の有効化
テンプレート印刷は現在、詳細ブロックとテーブルブロックをサポートしています。以下にこれら2つのタイプのブロックの設定方法をご紹介します。

#### 詳細ブロック

1. **詳細ブロックを開く**:
- テンプレート印刷機能を使用する必要があるアプリケーションの詳細ブロックに移動します。

2. **設定操作メニューにアクセス**:
- インターフェースの上部にある「設定操作」メニューをクリックします。

3. **「テンプレート印刷」を選択**:
- ドロップダウンメニューで「テンプレート印刷」オプションをクリックして、プラグインを有効にします。

![テンプレート印刷を有効化](https://static-docs.nocobase.com/20241212150539-2024-12-12-15-05-43.png)

### テンプレートの設定

1. **テンプレート設定ページにアクセス**:
- 「テンプレート印刷」ボタンの設定メニューで、「テンプレート設定」オプションを選択します。

![テンプレート設定オプション](https://static-docs.nocobase.com/20241212151858-2024-12-12-15-19-01.png)

2. **新しいテンプレートを追加**:
- 「テンプレート追加」ボタンをクリックして、テンプレート追加ページに入ります。

![テンプレート追加ボタン](https://static-docs.nocobase.com/20241212151243-2024-12-12-15-12-46.png)

3. **テンプレート情報を入力**:
- テンプレートフォームで、テンプレート名を入力し、テンプレートタイプ（Word、Excel、PowerPoint）を選択します。
- 対応するテンプレートファイルをアップロードします（`.docx`、`.xlsx`、`.pptx`形式をサポート）。

![テンプレート名とファイルの設定](https://static-docs.nocobase.com/20241212151518-2024-12-12-15-15-21.png)

4. **テンプレートの編集と保存**:
- 「フィールドリスト」ページに移動し、フィールドをコピーしてテンプレートに入力します。
  ![フィールドリスト](https://static-docs.nocobase.com/20250107141010.png)
  ![20241212152743-2024-12-12-15-27-45](https://static-docs.nocobase.com/20241212152743-2024-12-12-15-27-45.png)
- 詳細を入力した後、「保存」ボタンをクリックしてテンプレートの追加を完了します。

5. **テンプレート管理**:
- テンプレートリストの右側にある「使用」ボタンをクリックして、テンプレートを有効にします。
- 「編集」ボタンをクリックして、テンプレート名を変更したり、テンプレートファイルを置き換えたりします。
- 「ダウンロード」ボタンをクリックして、設定済みのテンプレートファイルをダウンロードします。
- 「削除」ボタンをクリックして、不要なテンプレートを削除します。システムは誤って削除することを避けるために確認を求めます。
  ![テンプレート管理](https://static-docs.nocobase.com/20250107140436.png)

#### テーブルブロック

テーブルブロックの使用方法は詳細ブロックとほぼ同じですが、以下の違いがあります：

1. **複数レコード印刷のサポート**：印刷するレコードをチェックして選択する必要があります。一度に最大100件のレコードを印刷できます。
   
![20250416215633-2025-04-16-21-56-35](https://static-docs.nocobase.com/20250416215633-2025-04-16-21-56-35.png)

2. **テンプレート分離管理**：テーブルブロックと詳細ブロックのテンプレートは互換性がありません — データ構造が異なるためです（一つはオブジェクト、もう一つは配列）。

## 基本構文

テンプレート印刷プラグインは、テンプレートに動的データと論理構造を柔軟に挿入するための様々な構文を提供します。以下に詳細な構文説明と使用例を示します。

### 基本的な置換

`{d.xxx}`形式のプレースホルダーを使用してデータを置換します。例：

- `{d.title}`: データセットから`title`フィールドを読み取ります。
- `{d.date}`: データセットから`date`フィールドを読み取ります。

**例**:

テンプレート内容:
```
お客様各位

弊社製品をご購入いただき、ありがとうございます: {d.productName}。
注文ID: {d.orderId}
注文日: {d.orderDate}

素晴らしい体験をお祈りしています！
```

データセット:
```json
{
  "productName": "スマートウォッチ",
  "orderId": "A123456789",
  "orderDate": "2025-01-01"
}
```

レンダリング結果:
```
お客様各位

弊社製品をご購入いただき、ありがとうございます: スマートウォッチ。
注文ID: A123456789
注文日: 2025-01-01

素晴らしい体験をお祈りしています！
```

### サブオブジェクトへのアクセス

データセットにサブオブジェクトが含まれている場合、ドット記法を使用してサブオブジェクトのプロパティにアクセスできます。

**構文**: `{d.parent.child}`

**例**:

データセット:
```json
{
  "customer": {
    "name": "田中太郎",
    "contact": {
      "email": "tanaka@example.com",
      "phone": "090-1234-5678"
    }
  }
}
```

テンプレート内容:
```
顧客名: {d.customer.name}
メールアドレス: {d.customer.contact.email}
電話番号: {d.customer.contact.phone}
```

レンダリング結果:
```
顧客名: 田中太郎
メールアドレス: tanaka@example.com
電話番号: 090-1234-5678
```

### 配列へのアクセス

データセットに配列が含まれている場合、予約キーワード`i`を使用して配列内の要素にアクセスできます。

**構文**: `{d.arrayName[i].field}`

**例**:

データセット:
```json
{
  "staffs": [
    { "firstname": "太郎", "lastname": "田中" },
    { "firstname": "花子", "lastname": "佐藤" },
    { "firstname": "次郎", "lastname": "鈴木" }
  ]
}
```

テンプレート内容:
```
最初の従業員の姓は {d.staffs[i=0].lastname} で、名前は {d.staffs[i=0].firstname} です
```

レンダリング結果:
```
最初の従業員の姓は 田中 で、名前は 太郎 です
```



## ループ処理

Loop handling is used to repeatedly render data from arrays or objects by defining start and end markers for the loop. Below, several common scenarios are described.

---

### 配列の反復処理

#### 1. Syntax Description

- Use the tag `{d.array[i].property}` to define the current loop item, and use `{d.array[i+1].property}` to specify the next item to mark the loop area.
- During the loop, the first line (the `[i]` part) is automatically used as the template for repetition; you only need to write the loop example once in the template.

Example syntax format:
```
{d.arrayName[i].property}
{d.arrayName[i+1].property}
```

#### 2. Example: Simple Array Loop

##### Data
```json
{
  "cars": [
    { "brand": "Toyota", "id": 1 },
    { "brand": "Hyundai", "id": 2 },
    { "brand": "BMW",    "id": 3 },
    { "brand": "Peugeot","id": 4 }
  ]
}
```

##### Template
```
Carsid
{d.cars[i].brand}{d.cars[i].id}
{d.cars[i+1].brand}
```

##### Result
```
Carsid
Toyota1
Hyundai2
BMW3
Peugeot4
```

---

#### 3. Example: Nested Array Loop

Suitable for cases where an array contains nested arrays; nesting can be at an infinite level.

##### Data
```json
[
  {
    "brand": "Toyota",
    "models": [
      { "size": "Prius 4", "power": 125 },
      { "size": "Prius 5", "power": 139 }
    ]
  },
  {
    "brand": "Kia",
    "models": [
      { "size": "EV4", "power": 450 },
      { "size": "EV6", "power": 500 }
    ]
  }
]
```

##### Template
```
{d[i].brand}

Models
{d[i].models[i].size} - {d[i].models[i].power}
{d[i].models[i+1].size}

{d[i+1].brand}
```

##### Result
```
Toyota

Models
Prius 4 - 125
Prius 5 - 139

Kia
```

---

#### 4. Example: Bidirectional Loop (Advanced Feature, v4.8.0+)

Bidirectional loops allow iteration over both rows and columns simultaneously, which is suitable for generating comparison tables and other complex layouts (note: currently, some formats are officially supported only in DOCX, HTML, and MD templates).

##### Data
```json
{
  "titles": [
    { "name": "Kia" },
    { "name": "Toyota" },
    { "name": "Hopium" }
  ],
  "cars": [
    { "models": [ "EV3", "Prius 1", "Prototype" ] },
    { "models": [ "EV4", "Prius 2", "" ] },
    { "models": [ "EV6", "Prius 3", "" ] }
  ]
}
```

##### Template
```
{d.titles[i].name}{d.titles[i+1].name}
{d.cars[i].models[i]}{d.cars[i].models[i+1]}
{d.cars[i+1].models[i]}
```

##### Result
```
KiaToyotaHopium
EV3Prius 1Prototype
EV4Prius 2
EV6Prius 3
```

---

#### 5. Example: Accessing Loop Iterator Values (v4.0.0+)

Within a loop, you can directly access the current iteration's index, which helps meet special formatting requirements.

##### Template Example
```
{d[i].cars[i].other.wheels[i].tire.subObject:add(.i):add(..i):add(...i)}
```

> Note: The number of dots indicates the index level (for example, `.i` represents the current level, while `..i` represents the previous level). There is currently an issue with reverse ordering; please refer to the official documentation for details.

---

### オブジェクトの反復処理

#### 1. Syntax Description

- For properties in an object, use `.att` to obtain the property name and `.val` to obtain the property value.
- During iteration, each property item is traversed one by one.

Example syntax format:
```
{d.objectName[i].att}  // property name
{d.objectName[i].val}  // property value
```

#### 2. Example: Object Property Iteration

##### Data
```json
{
  "myObject": {
    "paul": "10",
    "jack": "20",
    "bob":  "30"
  }
}
```

##### Template
```
People namePeople age
{d.myObject[i].att}{d.myObject[i].val}
{d.myObject[i+1].att}{d.myObject[i+1].val}
```

##### Result
```
People namePeople age
paul10
jack20
bob30
```

---

### ソート

Using the sorting feature, you can directly sort array data within the template.

#### 1. Syntax Description: Ascending Order Sorting

- Use an attribute as the sorting criterion in the loop tag. The syntax format is:
  ```
  {d.array[sortingAttribute, i].property}
  {d.array[sortingAttribute+1, i+1].property}
  ```
- For multiple sorting criteria, separate the attributes with commas within the brackets.

#### 2. Example: Sorting by Numeric Attribute

##### Data
```json
{
  "cars": [
    { "brand": "Ferrari", "power": 3 },
    { "brand": "Peugeot", "power": 1 },
    { "brand": "BMW",     "power": 2 },
    { "brand": "Lexus",   "power": 1 }
  ]
}
```

##### Template
```
Cars
{d.cars[power, i].brand}
{d.cars[power+1, i+1].brand}
```

##### Result
```
Cars
Peugeot
Lexus
BMW
Ferrari
```

#### 3. Example: Multi-Attribute Sorting

##### Data
```json
{
  "cars": [
    { "brand": "Ferrari", "power": 3, "sub": { "size": 1 } },
    { "brand": "Aptera",  "power": 1, "sub": { "size": 20 } },
    { "brand": "Peugeot", "power": 1, "sub": { "size": 20 } },
    { "brand": "BMW",     "power": 2, "sub": { "size": 1 } },
    { "brand": "Kia",     "power": 1, "sub": { "size": 10 } }
  ]
}
```

##### Template
```
Cars
{d.cars[power, sub.size, i].brand}
{d.cars[power+1, sub.size+1, i+1].brand}
```

##### Result
```
Cars
Kia
Aptera
Peugeot
BMW
Ferrari
```

---

### フィルタリング

Filtering is used to filter out rows in a loop based on specific conditions.

#### 1. Syntax Description: Numeric Filtering

- Add conditions in the loop tag (for example, `age > 19`). The syntax format is:
  ```
  {d.array[i, condition].property}
  ```

#### 2. Example: Numeric Filtering

##### Data
```json
[
  { "name": "John",   "age": 20 },
  { "name": "Eva",    "age": 18 },
  { "name": "Bob",    "age": 25 },
  { "name": "Charly", "age": 30 }
]
```

##### Template
```
People
{d[i, age > 19, age < 30].name}
{d[i+1, age > 19, age < 30].name}
```

##### Result
```
People
John
Bob
```

---

#### 3. Syntax Description: String Filtering

- Specify string conditions using single quotes. For example:
  ```
  {d.array[i, type='rocket'].name}
  ```

#### 4. Example: String Filtering

##### Data
```json
[
  { "name": "Falcon 9",    "type": "rocket" },
  { "name": "Model S",     "type": "car" },
  { "name": "Model 3",     "type": "car" },
  { "name": "Falcon Heavy","type": "rocket" }
]
```

##### Template
```
People
{d[i, type='rocket'].name}
{d[i+1, type='rocket'].name}
```

##### Result
```
People
Falcon 9
Falcon Heavy
```

---

#### 5. Syntax Description: Filter the First N Items

- You can use the loop index `i` to filter out the first N elements. For example:
  ```
  {d.array[i, i < N].property}
  ```

#### 6. Example: Filtering the First Two Items

##### Data
```json
[
  { "name": "Falcon 9" },
  { "name": "Model S" },
  { "name": "Model 3" },
  { "name": "Falcon Heavy" }
]
```

##### Template
```
People
{d[i, i < 2].name}
{d[i+1, i < 2].name}
```

##### Result
```
People
Falcon 9
Model S
```

---

#### 7. Syntax Description: Exclude the Last N Items

- Use negative indexing `i` to represent items from the end. For example:
  - `{d.array[i=-1].property}` retrieves the last item.
  - `{d.array[i, i!=-1].property}` excludes the last item.

#### 8. Example: Excluding the Last One and Last Two Items

##### Data
```json
[
  { "name": "Falcon 9" },
  { "name": "Model S" },
  { "name": "Model 3" },
  { "name": "Falcon Heavy" }
]
```

##### Template
```
Last item: {d[i=-1].name}

Excluding the last item:
{d[i, i!=-1].name}
{d[i+1, i!=-1].name}

Excluding the last two items:
{d[i, i<-2].name}
{d[i+1, i<-2].name}
```

##### Result
```
Last item: Falcon Heavy

Excluding the last item:
Falcon 9
Model S
Model 3

Excluding the last two items:
Falcon 9
Model S
```

---

#### 9. Syntax Description: Intelligent Filtering

- Using intelligent condition blocks, you can hide an entire row based on complex conditions. For example:
  ```
  {d.array[i].property:ifIN('keyword'):drop(row)}
  ```

#### 10. Example: Intelligent Filtering

##### Data
```json
[
  { "name": "Falcon 9" },
  { "name": "Model S" },
  { "name": "Model 3" },
  { "name": "Falcon Heavy" }
]
```

##### Template
```
People
{d[i].name}
{d[i].name:ifIN('Falcon'):drop(row)}
{d[i+1].name}
```

##### Result
```
People
Model S
Model 3
```

*(Note: Rows containing "Falcon" in the template are removed by the intelligent filtering condition.)*

---

### 重複除去

#### 1. Syntax Description

- Using a custom iterator, you can obtain unique (non-duplicate) items based on a property value. The syntax is similar to a normal loop but automatically ignores duplicate items.

Example format:
```
{d.array[property].property}
{d.array[property+1].property}
```

#### 2. Example: Selecting Unique Data

##### Data
```json
[
  { "type": "car",   "brand": "Hyundai" },
  { "type": "plane", "brand": "Airbus" },
  { "type": "plane", "brand": "Boeing" },
  { "type": "car",   "brand": "Toyota" }
]
```

##### Template
```
Vehicles
{d[type].brand}
{d[type+1].brand}
```

##### Result
```
Vehicles
Hyundai
Airbus
```
---


Below is the English translation of the documentation, with headings and subheadings preserved:

---

## フォーマッター

フォーマッターは、生データを読みやすいテキストに変換するために使用されます。データにコロン（`:`）を使用して適用され、チェーン化することができ、各フォーマッターの出力が次のフォーマッターの入力になります。一部のフォーマッターは定数パラメータまたは動的パラメータをサポートしています。

---

### 概要

#### 1. Syntax Explanation
The basic invocation of a formatter is as follows:
```
{d.property:formatter1:formatter2(...)}
```  
For example, in the case of converting the string `"JOHN"` to `"John"`, the formatter `lowerCase` is used first to convert all letters to lower case, and then `ucFirst` is used to capitalize the first letter.

#### 2. Example

Data:
```json
{
  "name": "JOHN",
  "birthday": "2000-01-31"
}
```

Template:
```
My name is {d.name:lowerCase:ucFirst}. I was born on {d.birthday:formatD(LL)}.
```

#### 3. Result

After rendering, the output is:
```
My name is John. I was born on January 31, 2000.
```

---

### 定数パラメータ

#### 1. Syntax Explanation
Many formatters support one or more constant parameters, which are separated by commas and enclosed in parentheses to modify the output. For example, `:prepend(myPrefix)` will add "myPrefix" in front of the text.  
**Note:** If the parameter contains commas or spaces, it must be enclosed in single quotes, for example: `prepend('my prefix')`.

#### 2. Example

Template example (see the specific formatter usage for details).

#### 3. Result

The output will have the specified prefix added in front of the text.

---

### 動的パラメータ

#### 1. Syntax Explanation
Formatters also support dynamic parameters. These parameters start with a dot (`.`) and are not enclosed in quotes.  
There are two methods to specify dynamic parameters:
- **Absolute JSON Path:** Begins with `d.` or `c.` (referring to root data or supplemental data).
- **Relative JSON Path:** Begins with a single dot (`.`), indicating that the property is looked up from the current parent object.

For example:
```
{d.subObject.qtyB:add(d.subObject.qtyC)}
```
It can also be written as a relative path:
```
{d.subObject.qtyB:add(.qtyC)}
```
If you need to access data from a higher level (parent or above), you can use multiple dots:
```
{d.subObject.qtyB:add(..qtyA):add(.qtyC)}
```

#### 2. Example

Data:
```json
{
  "id": 10,
  "qtyA": 20,
  "subObject": {
    "qtyB": 5,
    "qtyC": 3
  },
  "subArray": [{
    "id": 1000,
    "qtyE": 3
  }]
}
```

Usage in Template:
```
{d.subObject.qtyB:add(d.subObject.qtyC)}      // Result: 8 (5 + 3)
{d.subObject.qtyB:add(.qtyC)}                   // Result: 8
{d.subObject.qtyB:add(..qtyA):add(.qtyC)}        // Result: 28 (5 + 20 + 3)
{d.subArray[0].qtyE:add(..subObject.qtyC)}       // Result: 6 (3 + 3)
```

#### 3. Result

The examples yield 8, 8, 28, and 6 respectively.

> **Note:** Using custom iterators or array filters as dynamic parameters is not allowed, for example:
> ```
> {d.subObject.qtyB:add(..subArray[i].qtyE)}
> {d.subObject.qtyB:add(d.subArray[i].qtyE)}
> ```

---

### テキストフォーマット

This section provides various formatters for text data. The following subsections introduce each formatter's syntax, examples, and results.

#### 1. :lowerCase

##### Syntax Explanation
Converts all letters to lower case.

##### Example
```
'My Car':lowerCase()   // Outputs "my car"
'my car':lowerCase()   // Outputs "my car"
null:lowerCase()       // Outputs null
1203:lowerCase()       // Outputs 1203
```

##### Result
Each example outputs as indicated in the comments.

---

#### 2. :upperCase

##### Syntax Explanation
Converts all letters to upper case.

##### Example
```
'My Car':upperCase()   // Outputs "MY CAR"
'my car':upperCase()   // Outputs "MY CAR"
null:upperCase()       // Outputs null
1203:upperCase()       // Outputs 1203
```

##### Result
Each example outputs as indicated in the comments.

---

#### 3. :ucFirst

##### Syntax Explanation
Capitalizes only the first letter of the string while leaving the rest unchanged.

##### Example
```
'My Car':ucFirst()     // Outputs "My Car"
'my car':ucFirst()     // Outputs "My car"
null:ucFirst()         // Outputs null
undefined:ucFirst()    // Outputs undefined
1203:ucFirst()         // Outputs 1203
```

##### Result
The output is as described in the comments.

---

#### 4. :ucWords

##### Syntax Explanation
Capitalizes the first letter of each word in the string.

##### Example
```
'my car':ucWords()     // Outputs "My Car"
'My cAR':ucWords()     // Outputs "My CAR"
null:ucWords()         // Outputs null
undefined:ucWords()    // Outputs undefined
1203:ucWords()         // Outputs 1203
```

##### Result
The output is as shown in the examples.

---

#### 5. :print(message)

##### Syntax Explanation
Always returns the specified message regardless of the original data, making it useful as a fallback formatter.  
Parameter:
- **message:** The text to print.

##### Example
```
'My Car':print('hello!')   // Outputs "hello!"
'my car':print('hello!')   // Outputs "hello!"
null:print('hello!')       // Outputs "hello!"
1203:print('hello!')       // Outputs "hello!"
```

##### Result
Returns the specified string "hello!" in all cases.

---

#### 6. :printJSON

##### Syntax Explanation
Converts an object or array into a JSON-formatted string.

##### Example
```
[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:printJSON()
// Outputs "[
  {"id": 2, "name": "homer"},
  {"id": 3, "name": "bart"}
]"
'my car':printJSON()   // Outputs ""my car""
```

##### Result
The output is the JSON-formatted string of the given data.

---

#### 7. :unaccent

##### Syntax Explanation
Removes diacritical marks from text, converting it to an unaccented format.

##### Example
```
'crÃ¨me brulÃ©e':unaccent()   // Outputs "creme brulee"
'CRÃME BRULÃE':unaccent()   // Outputs "CREME BRULEE"
'Ãªtre':unaccent()           // Outputs "etre"
'Ã©Ã¹Ã¯ÃªÃ¨Ã ':unaccent()       // Outputs "euieea"
```

##### Result
All examples output the text with accents removed.

---

#### 8. :convCRLF

##### Syntax Explanation
Converts carriage return and newline characters (`
` or `
`) into document-specific line break tags. This is useful for formats such as DOCX, PPTX, ODT, ODP, and ODS.  
**Note:** When using `:html` before `:convCRLF`, the `
` will be converted to a `<br>` tag.

##### Example
```
// For ODT format:
'my blue 
 car':convCRLF()    // Outputs "my blue <text:line-break/> car"
'my blue 
 car':convCRLF()    // Outputs "my blue <text:line-break/> car"

// For DOCX format:
'my blue 
 car':convCRLF()    // Outputs "my blue </w:t><w:br/><w:t> car"
'my blue 
 car':convCRLF()    // Outputs "my blue </w:t><w:br/><w:t> car"
```

##### Result
The output shows the line break markers appropriate for the target document format.

---

#### 9. :substr(begin, end, wordMode)

##### Syntax Explanation
Performs substring operations on a string, starting at index `begin` (0-based) and ending just before index `end`.  
An optional parameter `wordMode` (boolean or `last`) controls whether to avoid breaking a word in the middle.

##### Example
```
'foobar':substr(0, 3)            // Outputs "foo"
'foobar':substr(1)               // Outputs "oobar"
'foobar':substr(-2)              // Outputs "ar"
'foobar':substr(2, -1)           // Outputs "oba"
'abcd efg hijklm':substr(0, 11, true)  // Outputs "abcd efg "
'abcd efg hijklm':substr(1, 11, true)  // Outputs "abcd efg "
```

##### Result
The output is the substring extracted according to the parameters.

---

#### 10. :split(delimiter)

##### Syntax Explanation
Splits a string into an array using the specified delimiter.  
Parameter:
- **delimiter:** The delimiter string.

##### Example
```
'abcdefc12':split('c')    // Outputs ["ab", "def", "12"]
1222.1:split('.')         // Outputs ["1222", "1"]
'ab/cd/ef':split('/')      // Outputs ["ab", "cd", "ef"]
```

##### Result
The example results in an array split by the given delimiter.

---

#### 11. :padl(targetLength, padString)

##### Syntax Explanation
Pads the left side of a string with a specified character until the final string reaches `targetLength`.  
If the target length is less than the original string length, the original string is returned.  
Parameters:
- **targetLength:** The desired total length.
- **padString:** The string used for padding (default is a space).

##### Example
```
'abc':padl(10)              // Outputs "       abc"
'abc':padl(10, 'foo')       // Outputs "foofoofabc"
'abc':padl(6, '123465')     // Outputs "123abc"
'abc':padl(8, '0')          // Outputs "00000abc"
'abc':padl(1)               // Outputs "abc"
```

##### Result
Each example outputs the string padded on the left accordingly.

---

#### 12. :padr(targetLength, padString)

##### Syntax Explanation
Pads the right side of a string with a specified character until the final string reaches `targetLength`.  
Parameters are the same as for `:padl`.

##### Example
```
'abc':padr(10)              // Outputs "abc       "
'abc':padr(10, 'foo')       // Outputs "abcfoofoof"
'abc':padr(6, '123465')     // Outputs "abc123"
'abc':padr(8, '0')          // Outputs "abc00000"
'abc':padr(1)               // Outputs "abc"
```

##### Result
The output shows the string padded on the right.

---

#### 13. :ellipsis(maximum)

##### Syntax Explanation
If the text exceeds the specified number of characters, appends an ellipsis ("...") at the end.  
Parameter:
- **maximum:** The maximum allowed number of characters.

##### Example
```
'abcdef':ellipsis(3)      // Outputs "abc..."
'abcdef':ellipsis(6)      // Outputs "abcdef"
'abcdef':ellipsis(10)     // Outputs "abcdef"
```

##### Result
The examples show text truncated and appended with an ellipsis if needed.

---

#### 14. :prepend(textToPrepend)

##### Syntax Explanation
Prepends the specified text to the beginning of the string.  
Parameter:
- **textToPrepend:** The prefix text.

##### Example
```
'abcdef':prepend('123')     // Outputs "123abcdef"
```

##### Result
The output shows the text with the specified prefix added.

---

#### 15. :append(textToAppend)

##### Syntax Explanation
Appends the specified text to the end of the string.  
Parameter:
- **textToAppend:** The suffix text.

##### Example
```
'abcdef':append('123')      // Outputs "abcdef123"
```

##### Result
The output shows the text with the specified suffix added.

---

#### 16. :replace(oldText, newText)

##### Syntax Explanation
Replaces all occurrences of `oldText` in the text with `newText`.  
Parameters:
- **oldText:** The text to be replaced.
- **newText:** The new text to replace with.  
  **Note:** If `newText` is null, it indicates that the matching text should be removed.

##### Example
```
'abcdef abcde':replace('cd', 'OK')    // Outputs "abOKef abOKe"
'abcdef abcde':replace('cd')          // Outputs "abef abe"
'abcdef abcde':replace('cd', null)      // Outputs "abef abe"
'abcdef abcde':replace('cd', 1000)      // Outputs "ab1000ef ab1000e"
```

##### Result
The output is the text after replacing the specified segments.

---

#### 17. :len

##### Syntax Explanation
Returns the length of a string or an array.

##### Example
```
'Hello World':len()     // Outputs 11
'':len()                // Outputs 0
[1,2,3,4,5]:len()       // Outputs 5
[1,'Hello']:len()       // Outputs 2
```

##### Result
Outputs the corresponding length as a number.

---

#### 18. :t

##### Syntax Explanation
Translates the text using a translation dictionary.  
Examples and results depend on the actual translation dictionary configuration.

---

#### 19. :preserveCharRef

##### Syntax Explanation
By default, Template removes certain illegal characters from XML (such as `&`, `>`, `<`, etc.). This formatter preserves character references (for example, `&#xa7;` remains unchanged) and is suitable for specific XML generation scenarios.  
Examples and results depend on the specific use case.

---

### 数値フォーマット

#### 1. :formatN(precision)

##### Syntax Explanation
Formats a number according to localization settings.  
Parameter:
- **precision:** The number of decimal places.  
  For ODS/XLSX formats, the number of displayed decimals is determined by the text editor; for other formats, this parameter is used.

##### Example
```
// Example environment: API options { "lang": "en-us" }
'10':formatN()         // Outputs "10.000"
'1000.456':formatN()   // Outputs "1,000.456"
```

##### Result
The number is output according to the specified precision and localization format.

---

#### 2. :round(precision)

##### Syntax Explanation
Rounds the number to the specified number of decimal places.

##### Example
```
10.05123:round(2)      // Outputs 10.05
1.05:round(1)          // Outputs 1.1
```

##### Result
The output is the number rounded to the given precision.

---

#### 3. :add(value)

##### Syntax Explanation
Adds the specified value to the current number.  
Parameter:
- **value:** The number to add.

##### Example
```
1000.4:add(2)         // Outputs 1002.4
'1000.4':add('2')      // Outputs 1002.4
```

##### Result
The output is the sum of the current number and the specified value.

---

#### 4. :sub(value)

##### Syntax Explanation
Subtracts the specified value from the current number.  
Parameter:
- **value:** The number to subtract.

##### Example
```
1000.4:sub(2)         // Outputs 998.4
'1000.4':sub('2')      // Outputs 998.4
```

##### Result
The output is the current number minus the specified value.

---

#### 5. :mul(value)

##### Syntax Explanation
Multiplies the current number by the specified value.  
Parameter:
- **value:** The multiplier.

##### Example
```
1000.4:mul(2)         // Outputs 2000.8
'1000.4':mul('2')      // Outputs 2000.8
```

##### Result
The output is the product of the current number and the specified value.

---

#### 6. :div(value)

##### Syntax Explanation
Divides the current number by the specified value.  
Parameter:
- **value:** The divisor.

##### Example
```
1000.4:div(2)         // Outputs 500.2
'1000.4':div('2')      // Outputs 500.2
```

##### Result
The output is the result of the division.

---

#### 7. :mod(value)

##### Syntax Explanation
Computes the modulus (remainder) of the current number divided by the specified value.  
Parameter:
- **value:** The modulus divisor.

##### Example
```
4:mod(2)              // Outputs 0
3:mod(2)              // Outputs 1
```

##### Result
The output is the remainder from the modulus operation.

---

#### 8. :abs

##### Syntax Explanation
Returns the absolute value of the number.

##### Example
```
-10:abs()             // Outputs 10
-10.54:abs()          // Outputs 10.54
10.54:abs()           // Outputs 10.54
'-200':abs()          // Outputs 200
```

##### Result
The output is the absolute value of the input number.

---

#### 9. :ceil

##### Syntax Explanation
Rounds the number upward to the smallest integer that is greater than or equal to the current number.

##### Example
```
10.05123:ceil()       // Outputs 11
1.05:ceil()           // Outputs 2
-1.05:ceil()          // Outputs -1
```

##### Result
The output is the number rounded upward to the nearest integer.

---

#### 10. :floor

##### Syntax Explanation
Rounds the number downward to the largest integer that is less than or equal to the current number.

##### Example
```
10.05123:floor()      // Outputs 10
1.05:floor()          // Outputs 1
-1.05:floor()         // Outputs -2
```

##### Result
The output is the number rounded downward to the nearest integer.

---

#### 11. :int

##### Syntax Explanation
Converts the number to an integer (not recommended for use).

##### Example and Result
Depends on the specific conversion case.

---

#### 12. :toEN

##### Syntax Explanation
Converts the number to English format (using `.` as the decimal point). Not recommended for use.

##### Example and Result
Depends on the specific conversion case.

---

#### 13. :toFixed

##### Syntax Explanation
Converts the number to a string while keeping only the specified number of decimal places. Not recommended for use.

##### Example and Result
Depends on the specific conversion case.

---

#### 14. :toFR

##### Syntax Explanation
Converts the number to French format (using `,` as the decimal separator). Not recommended for use.

##### Example and Result
Depends on the specific conversion case.

---

### 通貨フォーマット

#### 1. :formatC(precisionOrFormat, targetCurrency)

##### Syntax Explanation
Formats a currency number and allows specifying the number of decimals or a particular output format.  
Parameters:
- **precisionOrFormat:** An optional parameter that can either be a number (specifying the number of decimals) or a format specifier:
  - An integer: changes the default decimal precision.
  - `'M'`: outputs only the main currency name.
  - `'L'`: outputs the number along with the currency symbol (default).
  - `'LL'`: outputs the number along with the main currency name.
- **targetCurrency:** Optional; the target currency code (in uppercase, e.g., USD, EUR) that overrides the global settings.

##### Example
```
// Example environment: API options { "lang": "en-us", "currency": { "source": "EUR", "target": "USD", "rates": { "EUR": 1, "USD": 2 } } }
'1000.456':formatC()      // Outputs "$2,000.91"
'1000.456':formatC('M')    // Outputs "dollars"
'1':formatC('M')           // Outputs "dollar"
'1000':formatC('L')        // Outputs "$2,000.00"
'1000':formatC('LL')       // Outputs "2,000.00 dollars"

// French example (when environment settings differ):
'1000.456':formatC()      // Outputs "2 000,91 ..."  
'1000.456':formatC()      // When the source and target currencies are the same, outputs "1 000,46 €"
```

##### Result
The output depends on the API options and exchange rate settings.

---

#### 2. :convCurr(target, source)

##### Syntax Explanation
Converts a number from one currency to another. The exchange rate can be passed via API options or set globally.  
If no parameters are specified, the conversion is automatically performed from `options.currencySource` to `options.currencyTarget`.  
Parameters:
- **target:** Optional; the target currency code (defaults to `options.currencyTarget`).
- **source:** Optional; the source currency code (defaults to `options.currencySource`).

##### Example
```
// Example environment: API options { "currency": { "source": "EUR", "target": "USD", "rates": { "EUR": 1, "USD": 2 } } }
10:convCurr()              // Outputs 20
1000:convCurr()            // Outputs 2000
1000:convCurr('EUR')        // Outputs 1000
1000:convCurr('USD')        // Outputs 2000
1000:convCurr('USD', 'USD') // Outputs 1000
```

##### Result
The output is the converted currency value.

---

### Date Formatting

#### 1. :formatD(patternOut, patternIn)

##### Syntax Explanation
Formats a date by accepting an output format `patternOut` and an optional input format `patternIn` (defaults to ISO 8601).  
Timezone and language adjustments can be made via `options.timezone` and `options.lang`.

##### Example
```
// Example environment: API options { "lang": "en-us", "timezone": "Europe/Paris" }
'20160131':formatD('L')      // Outputs "01/31/2016"
'20160131':formatD('LL')     // Outputs "January 31, 2016"
'20160131':formatD('LLLL')   // Outputs "Sunday, January 31, 2016 12:00 AM"
'20160131':formatD('dddd')   // Outputs "Sunday"

// French example:
'2017-05-10T15:57:23.769561+03:00':formatD('LLLL')  // Outputs "mercredi 10 mai 2017 14:57"
'20160131':formatD('LLLL')   // Outputs "dimanche 31 janvier 2016 00:00"
1410715640:formatD('LLLL', 'X') // Outputs "dimanche 14 septembre 2014 19:27"
```

##### Result
The output is the date formatted as specified.

---

#### 2. :addD(amount, unit, patternIn)

##### Syntax Explanation
Adds a specified amount of time to a date. Supported units include: day, week, month, quarter, year, hour, minute, second, millisecond.  
Parameters:
- **amount:** The quantity to add.
- **unit:** The time unit (case-insensitive).
- **patternIn:** Optional, the input format (defaults to ISO8601).

##### Example
```
// Example environment: API options { "lang": "fr", "timezone": "Europe/Paris" }
'2017-05-10T15:57:23.769561+03:00':addD('3', 'day')    // Outputs "2017-05-13T12:57:23.769Z"
'2017-05-10 15:57:23.769561+03:00':addD('3', 'month')      // Outputs "2017-08-10T12:57:23.769Z"
'20160131':addD('3', 'day')       // Outputs "2016-02-03T00:00:00.000Z"
'20160131':addD('3', 'month')     // Outputs "2016-04-30T00:00:00.000Z"
'31-2016-01':addD('3', 'month', 'DD-YYYY-MM')  // Outputs "2016-04-30T00:00:00.000Z"
```

##### Result
The output is the new date after the specified time has been added.

---

#### 3. :subD(amount, unit, patternIn)

##### Syntax Explanation
Subtracts a specified amount of time from a date. The parameters are the same as in `addD`.

##### Example
```
// Example environment: API options { "lang": "fr", "timezone": "Europe/Paris" }
'2017-05-10T15:57:23.769561+03:00':subD('3', 'day')    // Outputs "2017-05-07T12:57:23.769Z"
'2017-05-10 15:57:23.769561+03:00':subD('3', 'month')      // Outputs "2017-02-10T12:57:23.769Z"
'20160131':subD('3', 'day')       // Outputs "2016-01-28T00:00:00.000Z"
'20160131':subD('3', 'month')     // Outputs "2015-10-31T00:00:00.000Z"
'31-2016-01':subD('3', 'month', 'DD-YYYY-MM')  // Outputs "2015-10-31T00:00:00.000Z"
```

##### Result
The output is the new date after the specified time has been subtracted.

---

#### 4. :startOfD(unit, patternIn)

##### Syntax Explanation
Sets the date to the start of the specified time unit.  
Parameters:
- **unit:** The time unit.
- **patternIn:** Optional, the input format.

##### Example
```
// Example environment: API options { "lang": "fr", "timezone": "Europe/Paris" }
'2017-05-10T15:57:23.769561+03:00':startOfD('day')    // Outputs "2017-05-10T00:00:00.000Z"
'2017-05-10 15:57:23.769561+03:00':startOfD('month')      // Outputs "2017-05-01T00:00:00.000Z"
'20160131':startOfD('day')       // Outputs "2016-01-31T00:00:00.000Z"
'20160131':startOfD('month')     // Outputs "2016-01-01T00:00:00.000Z"
'31-2016-01':startOfD('month', 'DD-YYYY-MM')  // Outputs "2016-01-01T00:00:00.000Z"
```

##### Result
The output is the date set to the start of the specified unit.

---

#### 5. :endOfD(unit, patternIn)

##### Syntax Explanation
Sets the date to the end of the specified time unit.  
Parameters are the same as for `startOfD`.

##### Example
```
// Example environment: API options { "lang": "fr", "timezone": "Europe/Paris" }
'2017-05-10T15:57:23.769561+03:00':endOfD('day')    // Outputs "2017-05-10T23:59:59.999Z"
'2017-05-10 15:57:23.769561+03:00':endOfD('month')      // Outputs "2017-05-31T23:59:59.999Z"
'20160131':endOfD('day')       // Outputs "2016-01-31T23:59:59.999Z"
'20160131':endOfD('month')     // Outputs "2016-01-31T23:59:59.999Z"
'31-2016-01':endOfD('month', 'DD-YYYY-MM')  // Outputs "2016-01-31T23:59:59.999Z"
```

##### Result
The output is the date set to the end of the specified unit.

---

#### 6. :diffD(toDate, unit, patternFromDate, patternToDate)

##### Syntax Explanation
Calculates the difference between two dates and outputs it in the specified unit. Supported units include:
- `day(s)` or `d`
- `week(s)` or `w`
- `quarter(s)` or `Q`
- `month(s)` or `M`
- `year(s)` or `y`
- `hour(s)` or `h`
- `minute(s)` or `m`
- `second(s)` or `s`
- `millisecond(s)` or `ms` (default unit)

Parameters:
- **toDate:** The target date.
- **unit:** The unit for output.
- **patternFromDate:** Optional, the format of the starting date.
- **patternToDate:** Optional, the format of the target date.

##### Example
```
'20101001':diffD('20101201')              // Outputs 5270400000
'20101001':diffD('20101201', 'second')      // Outputs 5270400
'20101001':diffD('20101201', 's')           // Outputs 5270400
'20101001':diffD('20101201', 'm')           // Outputs 87840
'20101001':diffD('20101201', 'h')           // Outputs 1464
'20101001':diffD('20101201', 'weeks')       // Outputs 8
'20101001':diffD('20101201', 'days')        // Outputs 61
'2010+10+01':diffD('2010=12=01', 'ms', 'YYYY+MM+DD', 'YYYY=MM=DD')  // Outputs 5270400000
```

##### Result
The output is the time difference between the two dates, converted into the specified unit.

---

#### 7. :convDate(patternIn, patternOut)

##### Syntax Explanation
Converts a date from one format to another (not recommended for use).  
Parameters:
- **patternIn:** The input date format.
- **patternOut:** The output date format.

##### Example
```
// Example environment: API options { "lang": "en", "timezone": "Europe/Paris" }
'20160131':convDate('YYYYMMDD', 'L')      // Outputs "01/31/2016"
'20160131':convDate('YYYYMMDD', 'LL')     // Outputs "January 31, 2016"
'20160131':convDate('YYYYMMDD', 'LLLL')   // Outputs "Sunday, January 31, 2016 12:00 AM"
'20160131':convDate('YYYYMMDD', 'dddd')   // Outputs "Sunday"
1410715640:convDate('X', 'LLLL')          // Outputs "Sunday, September 14, 2014 7:27 PM"
// French example:
'20160131':convDate('YYYYMMDD', 'LLLL')   // Outputs "dimanche 31 janvier 2016 00:00"
'20160131':convDate('YYYYMMDD', 'dddd')   // Outputs "dimanche"
```

##### Result
The output is the date converted to the specified format.

---

#### 8. Date Format Patterns

Common date format symbols (refer to the DayJS documentation):
- `X`: Unix timestamp (in seconds), e.g., 1360013296
- `x`: Unix timestamp in milliseconds, e.g., 1360013296123
- `YY`: Two-digit year, e.g., 18
- `YYYY`: Four-digit year, e.g., 2018
- `M`, `MM`, `MMM`, `MMMM`: Month (number, two-digit, abbreviated, full name)
- `D`, `DD`: Day (number, two-digit)
- `d`, `dd`, `ddd`, `dddd`: Day of the week (number, minimal, abbreviated, full name)
- `H`, `HH`, `h`, `hh`: Hour (24-hour or 12-hour clock)
- `m`, `mm`: Minute
- `s`, `ss`: Second
- `SSS`: Millisecond (3 digits)
- `Z`, `ZZ`: UTC offset, e.g., +05:00 or +0500
- `A`, `a`: AM/PM
- `Q`: Quarter (1-4)
- `Do`: Day of month with ordinal, e.g., 1st, 2nd, …
- For other formats, refer to the full documentation.  
  Additionally, there are localized formats based on language such as `LT`, `LTS`, `L`, `LL`, `LLL`, `LLLL`, etc.

---

### Interval Formatting

#### 1. :formatI(patternOut, patternIn)

##### Syntax Explanation
Formats a duration or interval. The supported output formats include:
- `human+` or `human` (suitable for human-friendly display)
- Units such as `millisecond(s)`, `second(s)`, `minute(s)`, `hour(s)`, `year(s)`, `month(s)`, `week(s)`, `day(s)` (or their abbreviations).

Parameters:
- **patternOut:** The output format (for example, `'second'` or `'human+'`).
- **patternIn:** Optional, the input unit (for example, `'milliseconds'` or `'s'`).

##### Example
```
// Example environment: API options { "lang": "en", "timezone": "Europe/Paris" }
2000:formatI('second')       // Outputs 2
2000:formatI('seconds')      // Outputs 2
2000:formatI('s')            // Outputs 2
3600000:formatI('minute')    // Outputs 60
3600000:formatI('hour')      // Outputs 1
2419200000:formatI('days')   // Outputs 28

// French example:
2000:formatI('human')        // Outputs "quelques secondes"
2000:formatI('human+')       // Outputs "dans quelques secondes"
-2000:formatI('human+')      // Outputs "il y a quelques secondes"

// English example:
2000:formatI('human')        // Outputs "a few seconds"
2000:formatI('human+')       // Outputs "in a few seconds"
-2000:formatI('human+')      // Outputs "a few seconds ago"

// Unit conversion example:
60:formatI('ms', 'minute')   // Outputs 3600000
4:formatI('ms', 'weeks')      // Outputs 2419200000
'P1M':formatI('ms')          // Outputs 2628000000
'P1Y2M3DT4H5M6S':formatI('hour')  // Outputs 10296.085
```

##### Result
The output is the duration or interval displayed in the specified unit or format.

---

### Array Formatting

#### 1. :arrayJoin(separator, index, count)

##### Syntax Explanation
Joins an array of strings or numbers into a single string.  
Parameters:
- **separator:** The delimiter (default is a comma `,`).
- **index:** Optional; the starting index from which to join.
- **count:** Optional; the number of items to join starting from `index` (can be negative to count from the end).

##### Example
```
['homer','bart','lisa']:arrayJoin()              // Outputs "homer, bart, lisa"
['homer','bart','lisa']:arrayJoin(' | ')          // Outputs "homer | bart | lisa"
['homer','bart','lisa']:arrayJoin('')              // Outputs "homerbartlisa"
[10,50]:arrayJoin()                               // Outputs "10, 50"
[]:arrayJoin()                                    // Outputs ""
null:arrayJoin()                                  // Outputs null
{}:arrayJoin()                                    // Outputs {}
20:arrayJoin()                                    // Outputs 20
undefined:arrayJoin()                             // Outputs undefined
['homer','bart','lisa']:arrayJoin('', 1)          // Outputs "bartlisa"
['homer','bart','lisa']:arrayJoin('', 1, 1)       // Outputs "bart"
['homer','bart','lisa']:arrayJoin('', 1, 2)       // Outputs "bartlisa"
['homer','bart','lisa']:arrayJoin('', 0, -1)      // Outputs "homerbart"
```

##### Result
The output is a string created by joining the array elements according to the specified parameters.

---

#### 2. :arrayMap(objSeparator, attSeparator, attributes)

##### Syntax Explanation
Transforms an array of objects into a string. It does not process nested objects or arrays.  
Parameters:
- **objSeparator:** The separator between objects (default is `, `).
- **attSeparator:** The separator between object attributes (default is `:`).
- **attributes:** Optional; a list of object attributes to output.

##### Example
```
[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap()
// Outputs "2:homer, 3:bart"

[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap(' - ')
// Outputs "2:homer - 3:homer"

[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap(' ; ', '|')
// Outputs "2|homer ; 3|bart"

[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap(' ; ', '|', 'id')
// Outputs "2 ; 3"

[{'id':2,'name':'homer','obj':{'id':20},'arr':[12,23]}]:arrayMap()
// Outputs "2:homer"

['homer','bart','lisa']:arrayMap()    // Outputs "homer, bart, lisa"
[10,50]:arrayMap()                    // Outputs "10, 50"
[]:arrayMap()                         // Outputs ""
null:arrayMap()                       // Outputs null
{}:arrayMap()                         // Outputs {}
20:arrayMap()                         // Outputs 20
undefined:arrayMap()                  // Outputs undefined
```

##### Result
The output is a string generated by mapping and joining the array elements, ignoring nested object content.

---

#### 3. :count(start)

##### Syntax Explanation
Counts the row number in an array and outputs the current row number.  
For example:
```
{d[i].id:count()}
```  
Regardless of the value of `id`, it outputs the current row count.  
Starting from v4.0.0, this formatter has been replaced internally by `:cumCount`.

Parameter:
- **start:** Optional; the starting value for the count.

##### Example and Result
In use, the output will display the row number according to the sequence of the array elements.

---


Below is the translated text back into English with the same structure using secondary (##) and tertiary (###) headings:

## 条件文

Conditional statements allow you to dynamically control the display or hiding of content in the document based on data values. Template provides three main ways to write conditions:

- **Inline conditions**: Directly output text (or replace it with other text).
- **Conditional blocks**: Display or hide a section of the document, suitable for multiple Template tags, paragraphs, tables, etc.

All conditions begin with a logical evaluation formatter (e.g., ifEQ, ifGT, etc.), followed by action formatters (such as show, elseShow, drop, keep, etc.).

---

### Overview

The logical operators and action formatters supported in conditional statements include:

- **Logical Operators**
  - **ifEQ(value)**: Checks if the data is equal to the specified value.
  - **ifNE(value)**: Checks if the data is not equal to the specified value.
  - **ifGT(value)**: Checks if the data is greater than the specified value.
  - **ifGTE(value)**: Checks if the data is greater than or equal to the specified value.
  - **ifLT(value)**: Checks if the data is less than the specified value.
  - **ifLTE(value)**: Checks if the data is less than or equal to the specified value.
  - **ifIN(value)**: Checks if the data is contained in an array or string.
  - **ifNIN(value)**: Checks if the data is not contained in an array or string.
  - **ifEM()**: Checks if the data is empty (e.g., null, undefined, an empty string, an empty array, or an empty object).
  - **ifNEM()**: Checks if the data is non-empty.
  - **ifTE(type)**: Checks if the data type is equal to the specified type (for example, "string", "number", "boolean", etc.).
  - **and(value)**: Logical "and", used to connect multiple conditions.
  - **or(value)**: Logical "or", used to connect multiple conditions.

- **Action Formatters**
  - **:show(text) / :elseShow(text)**: Used in inline conditions to directly output the specified text.
  - **:hideBegin / :hideEnd** and **:showBegin / :showEnd**: Used in conditional blocks to hide or show sections of the document.

The following sections introduce the detailed syntax, examples, and results for each usage.

---

### Inline Conditions

#### 1. :show(text) / :elseShow(text)

##### Syntax
```
{data:condition:show(text)}
{data:condition:show(text):elseShow(alternative text)}
```

##### Example
Assume the data is:
```json
{
  "val2": 2,
  "val5": 5
}
```
The template is as follows:
```
val2 = {d.val2:ifGT(3):show('high')}
val2 = {d.val2:ifGT(3):show('high'):elseShow('low')}
val5 = {d.val5:ifGT(3):show('high')}
```

##### Result
```
val2 = 2
val2 = low
val5 = high
```

---

#### 2. Switch Case (Multiple Conditionals)

##### Syntax
Use consecutive condition formatters to build a structure similar to a switch-case:
```
{data:ifEQ(value1):show(result1):ifEQ(value2):show(result2):elseShow(default result)}
```
Or achieve the same with the or operator:
```
{data:ifEQ(value1):show(result1):or(data):ifEQ(value2):show(result2):elseShow(default result)}
```

##### Example
Data:
```json
{
  "val1": 1,
  "val2": 2,
  "val3": 3
}
```
Template:
```
val1 = {d.val1:ifEQ(1):show(A):ifEQ(2):show(B):elseShow(C)}
val2 = {d.val2:ifEQ(1):show(A):ifEQ(2):show(B):elseShow(C)}
val3 = {d.val3:ifEQ(1):show(A):ifEQ(2):show(B):elseShow(C)}
```

##### Result
```
val1 = A
val2 = B
val3 = C
```

---

#### 3. Multi-variable Conditionals

##### Syntax
Use the logical operators and/or to test multiple variables:
```
{data1:ifEQ(condition1):and(.data2):ifEQ(condition2):show(result):elseShow(alternative result)}
{data1:ifEQ(condition1):or(.data2):ifEQ(condition2):show(result):elseShow(alternative result)}
```

##### Example
Data:
```json
{
  "val2": 2,
  "val5": 5
}
```
Template:
```
and = {d.val2:ifEQ(1):and(.val5):ifEQ(5):show(OK):elseShow(KO)}
or = {d.val2:ifEQ(1):or(.val5):ifEQ(5):show(OK):elseShow(KO)}
```

##### Result
```
and = KO
or = OK
```

---

### Logical Operators and Formatters

In the following sections, the described formatters use the inline condition syntax with the following format:
```
{data:formatter(parameter):show(text):elseShow(alternative text)}
```

#### 1. :and(value)

##### Syntax
```
{data:ifEQ(value):and(new data or condition):ifGT(another value):show(text):elseShow(alternative text)}
```

##### Example
```
{d.car:ifEQ('delorean'):and(.speed):ifGT(80):show('TravelInTime'):elseShow('StayHere')}
```

##### Result
If `d.car` equals `'delorean'` and `d.speed` is greater than 80, the output is `TravelInTime`; otherwise, the output is `StayHere`.

---

#### 2. :or(value)

##### Syntax
```
{data:ifEQ(value):or(new data or condition):ifGT(another value):show(text):elseShow(alternative text)}
```

##### Example
```
{d.car:ifEQ('delorean'):or(.speed):ifGT(80):show('TravelInTime'):elseShow('StayHere')}
```

##### Result
If `d.car` equals `'delorean'` or `d.speed` is greater than 80, the output is `TravelInTime`; otherwise, the output is `StayHere`.

---

#### 3. :ifEM()

##### Syntax
```
{data:ifEM():show(text):elseShow(alternative text)}
```

##### Example
```
null:ifEM():show('Result true'):elseShow('Result false')
[]:ifEM():show('Result true'):elseShow('Result false')
```

##### Result
For `null` or an empty array, the output is `Result true`; otherwise, it is `Result false`.

---

#### 4. :ifNEM()

##### Syntax
```
{data:ifNEM():show(text):elseShow(alternative text)}
```

##### Example
```
0:ifNEM():show('Result true'):elseShow('Result false')
'homer':ifNEM():show('Result true'):elseShow('Result false')
```

##### Result
For non-empty data (such as the number 0 or the string 'homer'), the output is `Result true`; for empty data, the output is `Result false`.

---

#### 5. :ifEQ(value)

##### Syntax
```
{data:ifEQ(value):show(text):elseShow(alternative text)}
```

##### Example
```
100:ifEQ(100):show('Result true'):elseShow('Result false')
'homer':ifEQ('homer'):show('Result true'):elseShow('Result false')
```

##### Result
If the data equals the specified value, the output is `Result true`; otherwise, it is `Result false`.

---

#### 6. :ifNE(value)

##### Syntax
```
{data:ifNE(value):show(text):elseShow(alternative text)}
```

##### Example
```
100:ifNE(100):show('Result true'):elseShow('Result false')
100:ifNE(101):show('Result true'):elseShow('Result false')
```

##### Result
The first example outputs `Result false`, while the second example outputs `Result true`.

---

#### 7. :ifGT(value)

##### Syntax
```
{data:ifGT(value):show(text):elseShow(alternative text)}
```

##### Example
```
1234:ifGT(1):show('Result true'):elseShow('Result false')
-23:ifGT(19):show('Result true'):elseShow('Result false')
```

##### Result
The first example outputs `Result true`, and the second outputs `Result false`.

---

#### 8. :ifGTE(value)

##### Syntax
```
{data:ifGTE(value):show(text):elseShow(alternative text)}
```

##### Example
```
50:ifGTE(-29):show('Result true'):elseShow('Result false')
1:ifGTE(768):show('Result true'):elseShow('Result false')
```

##### Result
The first example outputs `Result true`, while the second outputs `Result false`.

---

#### 9. :ifLT(value)

##### Syntax
```
{data:ifLT(value):show(text):elseShow(alternative text)}
```

##### Example
```
-23:ifLT(19):show('Result true'):elseShow('Result false')
1290:ifLT(768):show('Result true'):elseShow('Result false')
```

##### Result
The first example outputs `Result true`, and the second outputs `Result false`.

---

#### 10. :ifLTE(value)

##### Syntax
```
{data:ifLTE(value):show(text):elseShow(alternative text)}
```

##### Example
```
5:ifLTE(5):show('Result true'):elseShow('Result false')
1290:ifLTE(768):show('Result true'):elseShow('Result false')
```

##### Result
The first example outputs `Result true`, and the second outputs `Result false`.

---

#### 11. :ifIN(value)

##### Syntax
```
{data:ifIN(value):show(text):elseShow(alternative text)}
```

##### Example
```
'car is broken':ifIN('is'):show('Result true'):elseShow('Result false')
[1,2,'toto']:ifIN(2):show('Result true'):elseShow('Result false')
```

##### Result
Both examples output `Result true` (because the string contains 'is', and the array contains 2).

---

#### 12. :ifNIN(value)

##### Syntax
```
{data:ifNIN(value):show(text):elseShow(alternative text)}
```

##### Example
```
'car is broken':ifNIN('is'):show('Result true'):elseShow('Result false')
[1,2,'toto']:ifNIN(2):show('Result true'):elseShow('Result false')
```

##### Result
The first example outputs `Result false` (because the string contains 'is'), and the second example outputs `Result false` (because the array contains 2).

---

#### 13. :ifTE(type)

##### Syntax
```
{data:ifTE('type'):show(text):elseShow(alternative text)}
```

##### Example
```
'homer':ifTE('string'):show('Result true'):elseShow('Result false')
10.5:ifTE('number'):show('Result true'):elseShow('Result false')
```

##### Result
The first example outputs `Result true` (since 'homer' is a string), and the second outputs `Result true` (since 10.5 is a number).

---

### Conditional Blocks

Conditional blocks are used to display or hide a section of the document, typically to enclose multiple tags or an entire block of text.

#### 1. :showBegin / :showEnd

##### Syntax
```
{data:ifEQ(condition):showBegin}
Document block content
{data:showEnd}
```

##### Example
Data:
```json
{
  "toBuy": true
}
```
Template:
```
Banana{d.toBuy:ifEQ(true):showBegin}
Apple
Pineapple
{d.toBuy:showEnd}Grapes
```

##### Result
When the condition is met, the content in between is displayed:
```
Banana
Apple
Pineapple
Grapes
```

---

#### 2. :hideBegin / :hideEnd

##### Syntax
```
{data:ifEQ(condition):hideBegin}
Document block content
{data:hideEnd}
```

##### Example
Data:
```json
{
  "toBuy": true
}
```
Template:
```
Banana{d.toBuy:ifEQ(true):hideBegin}
Apple
Pineapple
{d.toBuy:hideEnd}Grapes
```

##### Result
When the condition is met, the content in between is hidden, resulting in:
```
Banana
Grapes
```

## 計算

## 高度な機能

### Pagination

#### 1. Page Number Update

##### Syntax
Simply insert it in your Office software.

##### Example
In Microsoft Word:
- Use the "Insert → Page Number" function

In LibreOffice:
- Use the "Insert → Field → Page Number" function

##### Result
In the generated report, the page numbers will update automatically.

---

#### 2. Table of Contents Generation

##### Syntax
Simply insert it in your Office software.

##### Example
In Microsoft Word:
- Use the "Insert → Index and Table → Table of Contents" function

In LibreOffice:
- Use the "Insert → Table of Contents and Index → Table, Index or Bibliography" function

##### Result
The report's table of contents will update automatically based on the document content.

---

#### 3. Repeating Table Headers

##### Syntax
Simply insert it in your Office software.

##### Example
In Microsoft Word:
- Right-click the table header → Table Properties → Check "Repeat as header row at the top of each page"

In LibreOffice:
- Right-click the table header → Table Properties → Text Flow tab → Check "Repeat heading"

##### Result
When a table spans multiple pages, the header will automatically repeat at the top of each page.

---

### Internationalization (i18n)

#### 1. Static Text Translation

##### Syntax
Use the `{t(text)}` tag for internationalizing static text:
```
{t(meeting)}
```

##### Example
In the template:
```
{t(meeting)} {t(apples)}
```
JSON Data or an external localization dictionary (e.g., for "fr-fr") provides corresponding translations (for example, "meeting" → "rendez-vous" and "apples" → "Pommes").

##### Result
When generating the report, the text will be replaced with the corresponding translation based on the target language.

---

#### 2. Dynamic Text Translation

##### Syntax
For data content, use the `:t` formatter, for example:
```
{d.id:ifEQ(2):show({t(monday)}):elseShow({t(tuesday)})}
```

##### Example
In the template:
```
{d.id:ifEQ(2):show({t(monday)}):elseShow({t(tuesday)})}
```
JSON Data and the localization dictionary provide the appropriate translations.

##### Result
Based on the condition, the output will be either "lundi" or "mardi" (using the target language as an example).

---

### Key-Value Mapping

#### 1. Enum Conversion (:convEnum)

##### Syntax
```
{data:convEnum(enumName)}
```
For example:
```
0:convEnum('ORDER_STATUS')
```

##### Example
In an API options example, the following is provided:
```json
{
  "enum": {
    "ORDER_STATUS": ["pending", "sent", "delivered"]
  }
}
```
In the template:
```
0:convEnum('ORDER_STATUS')
```

##### Result
Outputs "pending"; if the index exceeds the enumeration range, the original value is output.

---

### ダイナミック画像
:::info
現在、XLSXおよびDOCXファイル形式をサポートしています
:::

ドキュメントテンプレートに「ダイナミック画像」を挿入することができます。これは、テンプレート内のプレースホルダー画像がレンダリング時にデータに基づいて自動的に実際の画像に置き換えられることを意味します。このプロセスは非常にシンプルで、以下の手順のみ必要です：

1. プレースホルダーとして一時的な画像を挿入する

2. その画像の「代替テキスト」を編集してフィールドラベルを設定する

3. ドキュメントをレンダリングすると、システムが自動的に実際の画像に置き換えます

以下、具体例を通してDOCXとXLSXの操作方法をそれぞれ説明します。

#### DOCXファイルでのダイナミック画像挿入

##### 単一画像の置換

1. DOCXテンプレートを開き、一時的な画像を挿入します（任意のプレースホルダー画像、例えば[青一色の画像](https://static-docs.nocobase.com/solid-color-image-2025-04-14-11-00-26.png)など）

:::info
**画像形式の説明**

- 現在、プレースホルダー画像はPNG形式のみサポートしています。提供している例の[青一色の画像](https://static-docs.nocobase.com/solid-color-image-2025-04-14-11-00-26.png)の使用を推奨します
- ターゲットレンダリング画像はPNG、JPG、JPEG形式のみサポートしています。他の画像形式はレンダリングに失敗する可能性があります。

**画像サイズの説明**

DOCXでもXLSXでも、最終レンダリング時の画像サイズは、テンプレート内の一時画像の寸法に従います。つまり、実際に置き換えられる画像は、挿入したプレースホルダー画像と同じサイズに自動的にスケールされます。レンダリング後の画像サイズを150×150にしたい場合は、テンプレートで一時画像を使用し、そのサイズに調整してください。
:::

2. この画像を右クリックし、「代替テキスト」を編集して、挿入したい画像フィールドラベルを入力します（例：`{d.imageUrl}`）：

![20250414211130-2025-04-14-21-11-31](https://static-docs.nocobase.com/20250414211130-2025-04-14-21-11-31.png)

3. レンダリングに以下のサンプルデータを使用します：
```json
{
  "name": "リンゴ",
  "imageUrl": "https://images.pexels.com/photos/206959/pexels-photo-206959.jpeg"
}
```

4. レンダリング結果では、一時画像が実際の画像に置き換えられます：

![20250414203444-2025-04-14-20-34-46](https://static-docs.nocobase.com/20250414203444-2025-04-14-20-34-46.png)

##### 複数画像のループ置換

テンプレートに商品リストのような画像グループを挿入したい場合は、ループ方式で実装することもできます。具体的な手順は以下の通りです：

1. データが以下のようになっているとします：
```json
{
  "products": [
    {
      "name": "リンゴ",
      "imageUrl": "https://images.pexels.com/photos/206959/pexels-photo-206959.jpeg"
    },
    {
      "name": "バナナ",
      "imageUrl": "https://images.pexels.com/photos/61127/pexels-photo-61127.jpeg"
    }
  ]
}
```

2. DOCXテンプレートでループエリアを設定し、各ループアイテムに一時画像を挿入して、代替テキストを`{d.products[i].imageUrl}`に設定します：

![20250414205418-2025-04-14-20-54-19](https://static-docs.nocobase.com/20250414205418-2025-04-14-20-54-19.png)

3. レンダリング後、すべての一時画像がそれぞれのデータ画像に置き換えられます：

![20250414205503-2025-04-14-20-55-05](https://static-docs.nocobase.com/20250414205503-2025-04-14-20-55-05.png)

#### XLSXファイルでのダイナミック画像挿入

Excelテンプレート（XLSX）での操作方法は基本的に同じですが、以下の点にご注意ください：

1. 画像を挿入した後、画像がセルの上に浮いているのではなく、「セル内の画像」を選択していることを確認してください。

![20250414211643-2025-04-14-21-16-45](https://static-docs.nocobase.com/20250414211643-2025-04-14-21-16-45.png)

2. セルを選択後、「代替テキスト」を表示をクリックして、フィールドラベル（例：`{d.imageUrl}`）を入力します。

### バーコード
:::info
現在、XLSXおよびDOCXファイル形式をサポートしています
:::

#### バーコード生成（QRコードなど）

バーコード生成は[ダイナミック画像](/handbook/action-template-print#ダイナミック画像)と同じ方法で動作し、3つのステップのみ必要です：

1. テンプレートにバーコードの位置をマークするために一時画像を挿入する

2. 画像の「代替テキスト」を編集し、バーコード形式フィールドラベルを書き込みます（例：`{d.code:barcode(qrcode)}`。ここで`qrcode`はバーコードのタイプです（下記の[サポートリスト](/handbook/action-template-print#サポートされているバーコードタイプ)を参照））

![20250414214626-2025-04-14-21-46-28](https://static-docs.nocobase.com/20250414214626-2025-04-14-21-46-28.png)

3. レンダリング後、プレースホルダー画像が対応するバーコード画像に自動的に置き換えられます：

![20250414214925-2025-04-14-21-49-26](https://static-docs.nocobase.com/20250414214925-2025-04-14-21-49-26.png)

#### サポートされているバーコードタイプ

| バーコード名 | タイプ |
| ------------ | ------ |
| QRコード     | qrcode |

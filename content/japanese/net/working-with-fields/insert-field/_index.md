---
title: フィールドを挿入
linktitle: フィールドを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にフィールドを挿入する方法を学びます。動的フィールドを使用して文書をカスタマイズします。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-field/
---

ここでは、Aspose.Words for .NET の「フィールドの挿入」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントと DocumentBuilder の作成

まず、新しいドキュメントを作成し、DocumentBuilder を初期化します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: フィールドの挿入

私たちは`InsertField()`DocumentBuilder のメソッドを使用して、ドキュメントにフィールドを挿入します。この例では、フィールド名が「MyFieldName」で、マージ形式が指定されたマージ フィールド (MERGEFIELD) を挿入します。

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Aspose.Words for .NET でフィールドを挿入するためのソース コードの例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントと DocumentBuilder を作成します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//フィールドを挿入します。
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

この例では、新しいドキュメントを作成し、DocumentBuilder を初期化し、フィールド名「MyFieldName」とマージ形式のマージ フィールドを挿入しました。その後、ドキュメントは指定されたファイル名で保存されます。

これで、Aspose.Words for .NET の「フィールドの挿入」機能の使用に関するガイドは終了です。

### よくある質問

#### Q: Word のフィールドとは何ですか?

A: Word のフィールドは、ドキュメントに動的なデータを挿入したり操作したりできる要素です。日付、ページ番号、表、数式などの可変情報を表示するために使用できます。

#### Q: Word 文書にフィールドを挿入するにはどうすればいいですか?

A: Word 文書にフィールドを挿入するには、次の手順に従います。

1. フィールドを挿入する場所にカーソルを置きます。
2. リボンの「挿入」タブに移動します。
3. 「テキスト」グループの「フィールド」ボタンをクリックして、フィールド ダイアログ ボックスを開きます。
4. ドロップダウン リストから挿入するフィールドの種類を選択します。
5. 必要に応じてフィールド オプションを構成します。
6. 「OK」ボタンをクリックして、フィールドをドキュメントに挿入します。

#### Q: Word でよく使用されるフィールドの種類は何ですか?

A: Word には、文書で使用できるさまざまなフィールド タイプが用意されています。よく使用されるフィールド タイプをいくつか紹介します。

- 日付と時刻: 現在の日付と時刻を表示します。
- ページ番号: 現在のページ番号を表示します。
- 目次: タイトルのスタイルに基づいて目次を自動的に生成します。
- 計算: 数式を使用して数学的な計算を実行します。
- フィラーテキスト: ドキュメントを埋めるためのランダムなテキストを生成します。

#### Q: Word でフィールドの外観をカスタマイズできますか?

A: はい、Word の利用可能な書式設定オプションを使用して、フィールドの外観をカスタマイズできます。たとえば、フィールド内のテキストのフォント、サイズ、色、スタイルを変更できます。太字、斜体、下線などの書式設定効果を適用することもできます。
  
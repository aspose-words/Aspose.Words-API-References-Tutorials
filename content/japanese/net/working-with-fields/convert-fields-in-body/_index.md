---
title: 本文内のフィールドを変換する
linktitle: 本文内のフィールドを変換する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ページ フィールドを Word 文書本文のテキストに変換する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/convert-fields-in-body/
---

このステップバイステップのチュートリアルでは、提供されている C# ソース コードを使用して、Aspose.Words for .NET の ConvertFieldsInBody 機能を使用する方法を説明します。この機能を使用すると、文書本文の特定のフィールドをプレーン テキストに変換できるため、文書の処理が容易になります。この機能を効果的に使用するには、次の手順に従ってください。

## ステップ 1: 前提条件

始める前に、Aspose.Words for .NET がインストールされていて、ドキュメントを処理できる状態になっていることを確認してください。また、ドキュメントへのディレクトリ パスがあることも確認してください。

## ステップ 2: ドキュメントをロードする

まず、ドキュメント ディレクトリへのパスの変数を宣言し、その変数を使用して、指定されたドキュメントから Document オブジェクトを初期化します。この例では、ドキュメントの名前は「Linked field.docx」です。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします
Document doc = new Document(dataDir + "Linked fields.docx");
```

## ステップ 3: ページフィールドをプレーンテキストに変換する

ドキュメントがロードされたので、変換手順に進むことができます。最初のセクションの本文でページフィールドをプレーンテキストに変換するには、`Range.Fields`指定された範囲内のすべてのフィールドを取得し、次のタイプのフィールドをフィルターで除外するメソッド`FieldType.FieldPage`。その後、使用できます`ForEach`各フィールドをループして呼び出します。`Unlink()`プレーンテキストに変換するメソッドです。

```csharp
//適切なパラメータを渡して、最初のセクションの本文でページ フィールドをプレーン テキストに変換します。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## ステップ 4: 変更したドキュメントを保存する

ページフィールドをプレーンテキストに変換したら、次のコマンドを使用して変更したドキュメントを保存できます。`Save()`メソッドを指定し、出力ファイルのパスと名前を指定します。この例では、「WorkingWithFields.ConvertFieldsInBody.docx」として保存します。

```csharp
//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Aspose.Words for .NET を使用して本文内のフィールドを変換するためのソース コードの例

Aspose.Words for .NET を使用してフィールドを本文に変換する完全なソース コードの例を次に示します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします
Document doc = new Document(dataDir + "Linked fields.docx");

//適切なパラメータを渡して、最初のセクションの本文でページ フィールドをプレーン テキストに変換します。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### よくある質問

#### Q: Aspose.Words は Microsoft Word のさまざまなバージョンと互換性がありますか?

A: はい、Aspose.Words は、Word 2003、Word 2007、Word 2010、Word 2013、Word 2016、Word 2019 など、さまざまなバージョンの Microsoft Word と互換性があります。

#### Q: Aspose.Words は複雑なフィールド構造を処理できますか?

A: もちろんです！ Aspose.Words は、ネストされたフィールド、計算、条件式などの複雑なフィールド構造を広範にサポートします。強力な API を活用して、あらゆる種類のフィールド構造を操作できます。

#### Q: Aspose.Words はフィールド更新操作をサポートしていますか?

A: はい、Aspose.Words を使用すると、フィールドをプログラムで更新できます。 API を使用すると、フィールド値の更新、計算の更新、その他のフィールド関連の操作を簡単に実行できます。

#### Q: Aspose.Words を使用してフィールドをプレーン テキストに変換できますか?

A：確かに！ Aspose.Words は、フィールドをプレーン テキストに変換するメソッドを提供します。これは、フィールド関連の書式設定や機能を使用せずにコンテンツを抽出する必要がある場合に役立ちます。

#### Q: Aspose.Words を使用して、動的フィールドを含む Word ドキュメントを生成することはできますか?

A: もちろんです！ Aspose.Words は、動的フィールドを含む Word ドキュメントを生成するための堅牢な機能を提供します。事前定義されたフィールドを含むテンプレートを作成し、それらにデータを動的に入力することで、柔軟で効率的なドキュメント生成ソリューションを提供できます。
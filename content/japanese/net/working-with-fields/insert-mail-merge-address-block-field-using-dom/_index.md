---
title: DOM を使用して差し込み印刷アドレス ブロック フィールドを挿入
linktitle: DOM を使用して差し込み印刷アドレス ブロック フィールドを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に差し込み印刷アドレス ブロック フィールドを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

ここでは、Aspose.Words for .NET の「差し込み印刷アドレス ブロック フィールドの挿入」機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。 「YOUR DOCUMENT DIRECTORY」という値を、ドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントと DocumentBuilder の作成

まず、新しいドキュメントを作成し、DocumentBuilder を初期化します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: カーソルを段落に移動する

DocumentBuilder を使用します。`MoveTo()`メソッドを使用して、差し込み印刷のアドレス ブロック フィールドを挿入する段落にカーソルを移動します。

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## ステップ 4: 差し込み印刷アドレス ブロック フィールドの挿入

DocumentBuilder を使用します。`InsertField()`差し込み印刷アドレス ブロック フィールドを段落に挿入するメソッド。

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

次に、国/地域名を含める、国/地域に応じた住所の書式設定、国/地域名の除外、名前と住所の形式、言語識別子などの適切なオプションを指定して、アドレス ブロック フィールドのプロパティを構成します。

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
field. Update();
```

### Aspose.Words for .NET を使用して差し込み印刷アドレス ブロック フィールドを挿入するためのサンプル ソース コード

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

//次のような差し込み印刷アドレス ブロックを挿入したいとします。
// { アドレスブロック \\c 1 \\d \\e テスト 2 \\f テスト 3 \\l \"テスト 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { アドレスブロック \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { アドレスブロック \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { アドレスブロック \\c 1 \\d \\e テスト 2 }
field.ExcludedCountryOrRegionName = "Test2";

// { アドレスブロック \\c 1 \\d \\e テスト 2 \\f テスト 3 }
field.NameAndAddressFormat = "Test3";

// { アドレスブロック \\c 1 \\d \\e テスト 2 \\f テスト 3 \\l \"テスト 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書内のメールアドレスの形式をカスタマイズするにはどうすればよいですか?

 A: Aspose.Words for .NET のプロパティを使用して、Word 文書内のメールアドレスの形式をカスタマイズできます。`FieldAddressBlock`物体。住所スタイル、区切り文字、オプション項目などの書式オプションを設定して、目的の書式を取得できます。

#### Q: Aspose.Words for .NET のメールアドレスフィールドのソースデータを指定するにはどうすればよいですか?

 A: Aspose.Words for .NET のメールアドレスフィールドのソースデータを指定するには、`FieldAddressBlock.StartAddress`そして`FieldAddressBlock.EndAddress`プロパティ。これらのプロパティは、CSV ファイル、データベースなどの外部データ ソースのアドレス範囲を定義するために使用されます。

#### Q: Aspose.Words for .NET のメールアドレスフィールドにオプションの要素を含めることはできますか?

 A: はい、Aspose.Words for .NET を使用すると、メールアドレスフィールドにオプションの要素を含めることができます。オプションの要素を定義するには、`FieldAddressBlock.OmitOptional`受信者名、会社名などのオプションの要素を含めるか除外するかを指定するメソッド。

#### Q: DOM を使用してメールアドレスフィールドを挿入すると、Aspose.Words for .NET の Word ドキュメント構造に影響しますか?

A: DOM を使用してメールアドレスフィールドを挿入しても、Word 文書の構造には直接影響しません。ただし、ドキュメントのコンテンツに新しいフィールド要素が追加されます。必要に応じて既存の要素を追加、削除、または変更することで、ドキュメントの構造を操作できます。
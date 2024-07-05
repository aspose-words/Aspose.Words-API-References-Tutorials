---
title: DOM を使用して差し込み印刷アドレスブロックフィールドを挿入する
linktitle: DOM を使用して差し込み印刷アドレスブロックフィールドを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書に差し込み印刷アドレス ブロック フィールドを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

ここでは、Aspose.Words for .NET の「差し込み印刷アドレス ブロック フィールドの挿入」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

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

## ステップ3: カーソルを段落に移動する

DocumentBuilderの`MoveTo()`メソッドを使用して、差し込み印刷アドレス ブロック フィールドを挿入する段落にカーソルを移動します。

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## ステップ4: 差し込み印刷アドレスブロックフィールドの挿入

DocumentBuilderの`InsertField()`段落に差し込み印刷アドレス ブロック フィールドを挿入する方法。

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

次に、国/地域名を含める、国/地域に応じて住所をフォーマットする、国/地域名を除外する、名前と住所の形式、言語識別子などの適切なオプションを指定して、住所ブロック フィールドのプロパティを構成します。

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

//次のような差し込み印刷アドレス ブロックを挿入します。
// { アドレスブロック \\c 1 \\d \\e テスト2 \\f テスト3 \\l \"テスト 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { アドレスブロック \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { アドレスブロック \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { アドレスブロック \\c 1 \\d \\e テスト2 }
field.ExcludedCountryOrRegionName = "Test2";

// { アドレスブロック \\c 1 \\d \\e テスト2 \\f テスト3 }
field.NameAndAddressFormat = "Test3";

// { アドレスブロック \\c 1 \\d \\e テスト2 \\f テスト3 \\l \"テスト 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書内の郵送先住所の形式をカスタマイズするにはどうすればよいですか?

 A: Aspose.Words for .NETでは、Word文書内の郵送先住所の形式を、`FieldAddressBlock`オブジェクト。アドレス スタイル、区切り文字、オプション項目などの書式設定オプションを設定して、必要な形式を取得できます。

#### Q: Aspose.Words for .NET の郵送先住所フィールドのソース データを指定するにはどうすればよいですか?

 A: Aspose.Words for .NETの郵送先住所フィールドのソースデータを指定するには、`FieldAddressBlock.StartAddress`そして`FieldAddressBlock.EndAddress`プロパティ。これらのプロパティは、CSV ファイル、データベースなどの外部データ ソース内のアドレス範囲を定義するために使用されます。

#### Q: Aspose.Words for .NET を使用して郵送先住所フィールドにオプションの要素を含めることができますか?

 A: はい、Aspose.Words for .NETでは郵送先住所フィールドにオプション要素を含めることができます。オプション要素を定義するには、`FieldAddressBlock.OmitOptional`受信者名、会社名などのオプション要素を含めるか除外するかを指定する方法。

#### Q: DOM を使用して郵送先住所フィールドを挿入すると、Aspose.Words for .NET の Word 文書構造に影響しますか?

A: DOM を使用して郵送先住所フィールドを挿入しても、Word 文書の構造に直接影響はありません。ただし、新しいフィールド要素が文書コンテンツに追加されます。必要に応じて既存の要素を追加、削除、または変更することで、文書構造を操作できます。
---
title: フィールドの変更 カルチャーソースの更新
linktitle: フィールドの変更 カルチャーソースの更新
second_title: Aspose.Words ドキュメント処理 API
description: フィールド更新カルチャ ソースの変更、Aspose.Words for .NET でカルチャ ソースを変更するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fields/change-field-update-culture-source/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフィールド更新カルチャ ソースを変更する手順を説明します。カルチャ ソースを変更することで、フィールド更新および差し込み印刷操作中に日付の書式を制御できます。これを実現するために必要な C# ソース コードと手順を説明します。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ1: ドキュメントとDocumentBuilderを作成する
まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: 特定のロケールのコンテンツを挿入する
次に、ロケールをドイツ語に設定し、日付形式のフィールドを挿入します。

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

上記のコードでは、フォント ロケールをドイツ語 (ロケール ID 1031) に設定し、特定の日付形式を持つ 2 つのフィールドを挿入します。

## ステップ 3: フィールドの変更、カルチャー ソースの更新
フィールド更新カルチャ ソースを変更するには、FieldOptions クラスを使用します。

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

この例では、フィールドの更新時に使用されるカルチャを、フィールドで使用されるカルチャから選択するように設定します。

## ステップ4: 差し込み印刷を実行する
差し込み印刷操作を実行し、「Date2」フィールドに日付の値を指定します。

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

このコード スニペットでは、差し込み印刷操作を実行し、「Date2」フィールドに DateTime 値を指定します。

## ステップ5: ドキュメントを保存する
Document クラスの Save メソッドを使用して、変更したドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Aspose.Words for .NET を使用してフィールド更新カルチャ ソースを変更するためのサンプル ソース コード
以下は、Aspose.Words for .NET を使用して Word 文書内のフィールド更新カルチャ ソースを変更するための完全なソース コードです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## 結論
おめでとうございます! Aspose.Words for .NET を使用して Word 文書のフィールド更新カルチャ ソースを変更する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを利用することで、フィールド更新および差し込み印刷操作中に日付の書式設定に使用されるカルチャを制御できるようになりました。正確で一貫性のある日付を確保するために、要件に応じてカルチャ ソースをカスタマイズします。

### よくある質問

#### Q: Aspose.Words for .NET でフィールド更新カルチャ ソースを変更するにはどうすればよいですか?

 A: Aspose.Words for .NETでフィールド更新カルチャソースを変更するには、`Document.FieldOptions.CultureSource`プロパティを設定し、その値を`FieldCultureSource.FieldCode`または`FieldCultureSource.CurrentThread`たとえば、`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode`フィールド コードで定義されたカルチャを使用します。

#### Q: Aspose.Words for .NET でフィールドを更新するために特定のカルチャを指定するにはどうすればよいですか?

 A: Aspose.Words for .NETでフィールドを更新するための特定のカルチャを指定するには、`Document.FieldOptions.FieldUpdateCultureInfo`プロパティを設定し、`CultureInfo`目的の文化に対応するオブジェクト。たとえば、`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")`フランス語 (フランス) の文化を指定します。

#### Q: Aspose.Words for .NET で自動フィールド更新を無効にすることは可能ですか?

 A: はい、Aspose.Words for .NETではフィールドの自動更新を無効にすることができます。`Document.FieldOptions.UpdateFields`プロパティを設定し、`false`フィールドの自動更新を防止します。これにより、必要に応じてフィールドの更新を手動で制御できます。

#### Q: Aspose.Words for .NET でドキュメント フィールドを手動で更新するにはどうすればよいですか?

 A: Aspose.Words for .NETでドキュメント内のフィールドを手動で更新するには、`Field.Update`各フィールドごとにメソッドを個別に使用できます。たとえば、`field.Update()`特定のフィールドを更新します。
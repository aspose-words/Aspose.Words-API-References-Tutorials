---
title: フィールドアップデート文化
linktitle: フィールドアップデート文化
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のフィールド カルチャを更新する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/field-update-culture/
---

ここでは、Aspose.Words for .NET の「フィールド カルチャ更新」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントとドキュメントジェネレーターの作成

まず、新しいドキュメントとドキュメント ジェネレーターを作成します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: 時間フィールドの挿入

私たちは`InsertField()`ドキュメントに時間フィールドを挿入する方法。

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

これにより、ドキュメントに時間フィールドが挿入されます。

## ステップ4: フィールド更新カルチャの構成

フィールド オプションを構成して、フィールド更新カルチャがフィールド コードに基づくように指定します。

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

これらのオプションは、フィールドの更新に使用されるカルチャを決定します。

### Aspose.Words for .NET でフィールド カルチャを更新するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントとドキュメント ジェネレーターを作成します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//時間フィールドを挿入します。
builder. InsertField(FieldType.FieldTime, true);

//フィールド更新カルチャを構成します。
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

//ドキュメントを保存します。
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

この例では、新しいドキュメントを作成し、時間フィールドを挿入し、フィールド更新カルチャを構成しました。次に、指定したファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET の「フィールド カルチャの更新」機能の使用に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words のフィールド更新カルチャとは何ですか?

A: Aspose.Words のフィールド更新カルチャとは、Word 文書内のフィールド値の書式設定と更新に使用されるカルチャを指します。カルチャによって、数値、日付、その他のデータが更新されたときにフィールドに表示される方法が決まります。

#### Q: Aspose.Words を使用して Word 文書内のフィールドの更新カルチャを設定する方法を教えてください。

A: Aspose.Words を使用して Word 文書内のフィールドの更新カルチャを設定するには、次の手順に従います。

1. Aspose.Words 名前空間から Document クラスをインポートします。
2. 既存のドキュメントを読み込んで Document のインスタンスを作成します。
3. Document.UpdateFieldsCultureInfo プロパティを使用して、フィールドの更新カルチャを設定します。

#### Q: Aspose.Words でフィールドを更新するためにサポートされているカルチャは何ですか?

A: Aspose.Words は、フィールドを更新するためにさまざまなカルチャをサポートしています。オペレーティング システムでサポートされている任意のカルチャを指定できます。たとえば、アメリカ英語の場合は「en-US」、フランス語の場合は「fr-FR」、ドイツ語の場合は「de-DE」などです。

#### Q: ドキュメント全体ではなく、個々のフィールドに特定のカルチャを設定することは可能ですか?

A: はい、ドキュメント全体ではなく、個々のフィールドに特定のカルチャを設定することができます。Aspose.Words では、各フィールドに Format プロパティがあり、これを使用してそのフィールドに固有の書式設定カルチャを設定できます。これにより、ドキュメント内の他のフィールドとは独立して、このフィールドの表示方法と更新方法を制御できます。

#### Q: Word 文書で現在定義されているフィールド更新カルチャを確認するにはどうすればよいですか?

A: Word 文書で現在定義されているフィールド更新カルチャを確認するには、Document.UpdateFieldsCultureInfo プロパティを使用します。このプロパティは、フィールド更新の設定に現在使用されているカルチャを表す CultureInfo オブジェクトを返します。
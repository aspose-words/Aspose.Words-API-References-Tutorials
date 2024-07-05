---
title: ロケールの変更
linktitle: ロケールの変更
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の日付と数値の書式設定のロケールを変更する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/change-locale/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のロケールを変更する手順を説明します。ロケールを変更することで、差し込み印刷操作中に日付と数字の書式を制御できます。これを実現するために必要な C# ソース コードと手順を説明します。

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

## ステップ2: フィールドを挿入する
次に、InsertField メソッドを使用して、ドキュメントにマージ フィールドを挿入します。

```csharp
builder.InsertField("MERGEFIELD Date");
```

上記のコードでは、「Date」という名前のマージ フィールドをドキュメントに挿入します。

## ステップ3: ロケールを変更する
日付と数値の書式設定のロケールを変更するには、スレッドの現在のカルチャを変更します。 この例では、ロケールをドイツ語 ("de-DE") に設定します。

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

上記のコードでは、現在のカルチャを保存し、現在のスレッドのカルチャをドイツ語に設定します。

## ステップ4: 差し込み印刷を実行する
差し込み印刷操作を実行し、「日付」フィールドに日付の値を入力します。

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

このコード スニペットでは、差し込み印刷操作を実行し、現在の日付を「日付」フィールドの値として提供します。

## ステップ5: 元のロケールを復元する
差し込み印刷が完了したら、スレッドの元のカルチャを復元します。

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

上記のコードでは、スレッドの元のカルチャを復元します。

## ステップ6: ドキュメントを保存する
Document クラスの Save メソッドを使用して、変更したドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Aspose.Words for .NET を使用してロケールを変更するためのサンプル ソース コード
以下は、Aspose.Words for .NET を使用して Word 文書のロケールを変更するための完全なソース コードです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## 結論
おめでとうございます。Aspose.Words for .NET を使用して Word 文書のロケールを変更する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを利用することで、差し込み印刷操作中に日付と数値の書式を制御できるようになりました。要件に応じてロケールをカスタマイズし、文書の書式が正確で一貫性のあるものになるようにします。

### よくある質問

#### Q: Aspose.Words はさまざまなバージョンの Microsoft Word と互換性がありますか?

A: はい、Aspose.Words は、Word 2003、Word 2007、Word 2010、Word 2013、Word 2016、Word 2019 など、さまざまなバージョンの Microsoft Word と互換性があります。

#### Q: Aspose.Words は複雑なフィールド構造をサポートしていますか?

A: もちろんです! Aspose.Words は、ネストされたフィールド、計算、条件式などの複雑なフィールド構造を幅広くサポートしています。この強力な API を使用して、あらゆる種類のフィールド構造を操作できます。

#### Q: Aspose.Words はフィールド更新操作をサポートしていますか?

A: はい、Aspose.Words ではスケジュールに従ってフィールドを更新できます。API を使用すると、フィールド値の更新、計算の更新、その他のフィールド関連の操作を簡単に実行できます。

#### Q: Aspose.Words を使用してフィールドをプレーン テキストに変換することは可能ですか?

A: もちろんです! Aspose.Words には、フィールドをプレーン テキストに変換するメソッドが用意されています。これは、書式設定やフィールド関連の機能なしでコンテンツを抽出する必要がある場合に役立ちます。

#### Q: Aspose.Words を使用して動的フィールドを含む Word 文書を生成することは可能ですか?

A: もちろんです! Aspose.Words は、動的なフィールドを持つ Word ドキュメントを生成するための強力な機能を提供します。定義済みのフィールドを持つテンプレートを作成し、動的にデータを入力することで、ドキュメント生成のための柔軟で効率的なソリューションを提供できます。
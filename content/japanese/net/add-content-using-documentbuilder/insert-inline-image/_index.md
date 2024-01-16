---
title: Word文書にインライン画像を挿入
linktitle: Word文書にインライン画像を挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にインライン画像を挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/insert-inline-image/
---
この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にインライン画像を挿入する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、ドキュメントのテキストに画像を直接追加できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: 新しいドキュメントと DocumentBuilder を作成する
まず、Document クラスを使用して新しいドキュメントを作成し、DocumentBuilder オブジェクトを初期化します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: インライン画像を挿入する
次に、DocumentBuilder クラスの InsertImage メソッドを使用して、インライン イメージをドキュメントに挿入します。画像ファイルのパスをパラメータとして指定します。

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## ステップ 3: ドキュメントを保存する
インライン イメージを挿入した後、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Aspose.Words for .NET を使用したインライン イメージの挿入のソース コード例
Aspose.Words for .NET を使用してインライン イメージを挿入するための完全なソース コードを次に示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## 結論
おめでとう！ Aspose.Words for .NET を使用して Word 文書にインライン画像を挿入する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、ドキュメントのテキスト内に画像をシームレスに追加できるようになります。

インライン画像は、イラスト、ロゴ、その他の視覚要素をドキュメントのフローに直接追加するなど、さまざまなシナリオで役立ちます。

### Word 文書へのインライン画像の挿入に関する FAQ

#### Q: Word 文書内のインライン画像のサイズを変更できますか?

A: はい、Aspose.Words for .NET を使用してインライン イメージのサイズを変更できます。画像を挿入した後、画像を表す Shape オブジェクトの幅と高さのプロパティを調整することで、そのサイズを操作できます。

#### Q: アクセシビリティを目的としてインライン画像に代替テキストを追加することはできますか?

A: はい、インライン画像に代替テキストを追加してアクセシビリティを高めることができます。 Aspose.Words for .NET は、画像への代替テキストの追加をサポートしており、スクリーン リーダーやその他の支援テクノロジで視覚障害のあるユーザーに画像コンテンツを説明できるようになります。

#### Q: インライン画像に書式設定やスタイルを適用できますか?

A: もちろんです！ Aspose.Words for .NET は、インライン イメージ用の広範な書式設定オプションを提供します。ドキュメントの視覚的なデザインに合わせて、さまざまなスタイル、枠線、効果、その他の書式設定属性を画像に適用できます。

#### Q: Aspose.Words for .NET は、ストリームまたはバイト配列からの画像の挿入をサポートしていますか?

A: はい、Aspose.Words for .NET を使用して、ストリームまたはバイト配列からインライン イメージを挿入できます。これにより、外部ソースからロードされた画像や動的に生成された画像を操作できるようになります。

#### Q: テキストコンテンツ内の特定の位置に画像を挿入できますか?

A: はい、Aspose.Words for .NET の DocumentBuilder クラスは、インライン イメージの挿入位置を正確に制御します。画像を挿入するテキスト内の正確な位置を指定できます。
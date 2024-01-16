---
title: Word文書にフローティング画像を挿入する
linktitle: Word文書にフローティング画像を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にフローティング イメージを挿入する方法を学びます。ステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/insert-floating-image/
---
この包括的な例では、Aspose.Words for .NET を使用して Word 文書にフローティング イメージを挿入する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、カスタマイズ可能な位置と折り返しのオプションを備えた画像をドキュメントに追加できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: 新しいドキュメントと DocumentBuilder を作成する
まず、Document クラスを使用して新しいドキュメントを作成し、DocumentBuilder オブジェクトを初期化します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: フローティング画像を挿入する
次に、DocumentBuilder クラスの InsertImage メソッドを使用して、フローティング イメージを挿入します。画像ファイルのパス、相対的な水平および垂直位置、幅、高さ、および折り返しオプションをパラメータとして指定します。

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## ステップ 3: ドキュメントを保存する
フローティング イメージを挿入した後、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Aspose.Words for .NET を使用したフローティング イメージの挿入のソース コード例
Aspose.Words for .NET を使用してフローティング イメージを挿入するための完全なソース コードを次に示します。
フローティング イメージは、ドキュメントのテキストから独立して配置できるロゴ、イラスト、装飾要素の追加など、さまざまなシナリオに役立ちます。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

画像ファイルのパス、必要な位置および折り返しのオプションなど、特定の要件に応じてコードを必ず調整してください。

## 結論
おめでとう！ Aspose.Words for .NET を使用して、Word 文書にフローティング イメージを挿入する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、視覚的に魅力的でカスタマイズ可能なフローティング イメージでドキュメントを強化できるようになります。

### Word 文書にフローティング画像を挿入する場合の FAQ

#### Q: 1 つのドキュメントに複数のフローティング画像を挿入できますか?

A：確かに！ Aspose.Words for .NET を使用して、Word 文書に必要なだけフローティング イメージを挿入できます。挿入プロセスを繰り返すだけで、複数の視覚的に魅力的な画像を追加できます。

#### Q: フローティング画像にはどのようなラッピング オプションが利用できますか?

A: Aspose.Words for .NET には、スクエア、タイト、スルー、トップボトム、なしなど、フローティング イメージのさまざまなラッピング オプションが用意されています。これらのオプションは、テキストがフローティング画像とどのように相互作用するかを決定します。

#### Q: フローティング画像のサイズを調整できますか?

A: もちろんです！ InsertImage メソッドのそれぞれのパラメータを使用して、フローティング イメージの幅と高さを指定できます。これにより、デザインの好みに応じて画像のサイズを制御できます。

#### Q: ドキュメント内の特定の要素を基準にしてフローティング イメージを配置できますか?

A: はい、Aspose.Words for .NET を使用すると、マージン、ページ、段落、表などの特定の要素を基準にしてフローティング イメージを配置できます。適切な相対的な水平および垂直位置パラメータを選択して、目的の配置を実現できます。

#### Q: Aspose.Words for .NET はデスクトップ アプリケーションと Web アプリケーションの両方に適していますか?

A: はい、Aspose.Words for .NET は、デスクトップ アプリケーションと Web アプリケーションの両方に適した多用途ライブラリです。 Windows アプリケーションを構築している場合でも、Web ベースのシステムを構築している場合でも、ライブラリを簡単に統合できます。

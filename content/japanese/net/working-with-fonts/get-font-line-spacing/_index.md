---
title: フォントの行間隔を取得する
linktitle: フォントの行間隔を取得する
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント行間隔を取得する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/get-font-line-spacing/
---
このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して Word 文書内のフォント行間隔を取得する方法を説明します。フォントの行間隔は、テキストの行間の垂直方向のスペースを定義します。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ 1: 新しいドキュメントとドキュメント ジェネレーターを作成する
まず、インスタンス化して新しいドキュメントを作成します。`Document`クラスとドキュメントビルダーをインスタンス化して、`DocumentBuilder`クラス。

```csharp
//新しいドキュメントを作成する
Document doc = new Document();

//ドキュメントジェネレーターを作成する
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: フォントを構成する
次に、フォントを設定してフォントを設定します。`Name`ドキュメントジェネレーターのプロパティ。

```csharp
//フォントを設定する
builder.Font.Name = "Calibri";
```

## ステップ 3: ドキュメントにテキストを追加する
次に、ドキュメント ジェネレーターを使用して、書式設定されたテキストをドキュメントに追加します。

```csharp
//ドキュメントにテキストを追加する
builder. Writen("qText");
```

## ステップ 4: フォントの行間隔を取得する
次に、次の場所にアクセスします。`Font`ドキュメントの最初の段落のオブジェクトを取得し、その値を取得します。`LineSpacing`財産。

```csharp
//フォントの行間を取得する
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Aspose.Words for .NET を使用してフォント行間隔を取得するためのサンプル ソース コード 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント行間隔を取得する方法を説明しました。フォントの行間隔は、テキストの行間の垂直方向の間隔を制御するために重要です。この機能を自由に使用して、ドキュメント内のテキストの外観をカスタマイズしてください。

### よくある質問

#### Q: Word 文書内の特定のテキストの行間隔を変更するにはどうすればよいですか?

A: Aspose.Words を使用すると、Word 文書内の特定のテキストの行間隔を簡単に変更できます。 API を使用して目的のテキストを選択し、適切な値を指定して行間の間隔を調整します。

#### Q: Word 文書の行間に正確な間隔を適用することはできますか?

A: はい、Aspose.Words を使用すると、Word 文書の行間に正確な間隔を適用できます。 API を使用して、行間隔の正確な値を指定できます。

#### Q: Word 文書全体の行間を調整するにはどうすればよいですか?

A: Aspose.Words を使用すると、Word 文書全体の行間隔を簡単に調整できます。 API が提供するメソッドを使用して、ドキュメント全体の行間隔を指定します。

#### Q: Aspose.Words は複数の行間隔をサポートしていますか?

A: はい、Aspose.Words は Word 文書内の複数の行間隔をサポートしています。テキストの行には、通常の 1.5 倍や 2 倍など、複数の間隔を設定できます。

#### Q: 行間隔を調整するときに行が重なる問題を回避するにはどうすればよいですか?

A: 行間の間隔を調整するときに行が重なり合う問題を回避するには、必ず適切な間隔の値を選択してください。また、ドキュメントの最終的なレンダリングをテストして、テキストが読みやすく適切な形式のままであることを確認します。
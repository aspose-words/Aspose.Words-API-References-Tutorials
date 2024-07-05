---
title: フォントの行間隔を取得
linktitle: フォントの行間隔を取得
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント行間隔を取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/get-font-line-spacing/
---
このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して、Word 文書のフォント行間隔を取得する方法について説明します。フォント行間隔は、テキストの行間の垂直スペースを定義します。.NET プロジェクトでコードを理解して実装できるように、手順を追って説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ1: 新しいドキュメントとドキュメントジェネレーターを作成する
まず、インスタンス化して新しいドキュメントを作成します。`Document`クラスとドキュメントビルダーをインスタンス化することで`DocumentBuilder`クラス。

```csharp
//新しいドキュメントを作成する
Document doc = new Document();

//ドキュメントジェネレータを作成する
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: フォントを設定する
次に、フォントを設定します。`Name`ドキュメントジェネレーターのプロパティ。

```csharp
//フォントを設定する
builder.Font.Name = "Calibri";
```

## ステップ3: 文書にテキストを追加する
ここで、ドキュメント ジェネレーターを使用して、フォーマットされたテキストをドキュメントに追加します。

```csharp
//文書にテキストを追加する
builder. Writen("qText");
```

## ステップ4: フォントの行間隔を取得する
では、`Font`文書の最初の段落のオブジェクトを取得し、その値を取得します。`LineSpacing`財産。

```csharp
//フォントの行間隔を取得する
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Aspose.Words for .NET を使用してフォントの行間を取得するためのサンプル ソース コード 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント行間隔を取得する方法を説明しました。フォント行間隔は、テキストの行間の垂直間隔を制御するために重要です。この機能を使用して、文書内のテキストの外観を自由にカスタマイズしてください。

### よくある質問

#### Q: Word 文書内の特定のテキストの行間隔を変更するにはどうすればよいですか?

A: Aspose.Words を使用すると、Word 文書内の特定のテキストの行間隔を簡単に変更できます。API を使用して目的のテキストを選択し、適切な値を指定して行間隔を調整します。

#### Q: Word 文書の行間に正確な間隔を適用することは可能ですか?

A: はい、Aspose.Words を使用すると、Word 文書内の行間に正確な間隔を適用できます。API を使用して行間隔の正確な値を指定できます。

#### Q: Word 文書全体の行間隔を調整するにはどうすればよいですか?

A: Aspose.Words を使用すると、Word 文書全体の行間隔を簡単に調整できます。API が提供するメソッドを使用して、文書全体の希望する行間隔を指定します。

#### Q: Aspose.Words は複数の行間隔をサポートしていますか?

A: はい、Aspose.Words は Word 文書で複数の行間隔をサポートしています。テキストの行に、通常の行間隔の 1.5 倍や 2 倍など、複数の行間隔を設定できます。

#### Q: 行間隔を調整するときに行が重なる問題を回避するにはどうすればよいですか?

A: 行間の間隔を調整するときに行が重なり合う問題を回避するには、適切な間隔の値を選択してください。また、ドキュメントの最終的なレンダリングをテストして、テキストが読みやすく、適切にフォーマットされていることを確認してください。
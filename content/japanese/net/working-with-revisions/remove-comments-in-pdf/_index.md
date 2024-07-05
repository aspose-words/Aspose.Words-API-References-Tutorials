---
title: PDF ファイル内のコメントを削除する
linktitle: PDF ファイル内のコメントを削除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ファイル内のコメントを削除します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/remove-comments-in-pdf/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して PDF ファイル内のコメントを削除する方法について説明します。完全なソース コードを提供し、マークダウン出力のフォーマット方法を説明します。

## ステップ1: ドキュメントの読み込み

最初のステップは、コメントを含むドキュメントを読み込むことです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ2: PDF内のコメントを非表示にする

PDF を生成するときにコメントを非表示にするようにレイアウト オプションを設定します。

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## ステップ3: ドキュメントをPDFとして保存する

最後に、コメントを削除してドキュメントを PDF 形式で保存します。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown出力形式

読みやすさを向上させるために、出力をマークダウン形式でフォーマットすることができます。例:

```markdown
- Comments are hidden in the generated PDF.
```

### Aspose.Words for .NET を使用して PDF 内のコメントを削除するためのサンプル ソース コード

Aspose.Words for .NET を使用して PDF ファイル内のコメントを削除するための完全なソース コードは次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// PDF 内のコメントを非表示にします。
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ファイルからコメントを削除する方法を学習しました。適切なレイアウト オプションを使用することで、PDF を生成するときにコメントを非表示にできました。Aspose.Words for .NET は、Word ファイルを操作し、PDF を含むさまざまな形式に変換する優れた柔軟性を提供します。この知識を適用して、Aspose.Words for .NET を使用して独自の PDF ファイルからコメントを削除できるようになりました。

### PDF ファイル内のコメントを削除する方法に関する FAQ

#### Q: Aspose.Words for .NET でドキュメントをアップロードするにはどうすればよいですか?

 A:`Document`ファイルからドキュメントを読み込むための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET で生成された PDF 内のコメントを非表示にするにはどうすればよいですか?

 A:`CommentDisplayMode`の財産`LayoutOptions` PDFを生成する際にコメントをどのように表示するかを設定するオブジェクト。コメントを非表示にするには、このプロパティを`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Q: Aspose.Words for .NET を使用してドキュメントを PDF として保存するにはどうすればよいですか?

 A:`Save`方法の`Document`ドキュメントを PDF 形式で保存するためのオブジェクト。PDF ファイルのフルパスを指定します。

```csharp
doc.Save("path/to/the/file.pdf");
```
---
title: PDF ファイル内のコメントを削除する
linktitle: PDF ファイル内のコメントを削除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ファイル内のコメントを削除します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/remove-comments-in-pdf/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して PDF ファイル内のコメントを削除する方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントをロードする

最初のステップは、コメントを含むドキュメントをロードすることです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ 2: PDF 内のコメントを非表示にする

PDF を生成するときにコメントを非表示にするようにレイアウト オプションを設定します。

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## ステップ 3: ドキュメントを PDF として保存する

最後にコメントを削除してPDF形式で保存します。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## マークダウン出力形式

読みやすさを向上させるために、出力をマークダウンでフォーマットすることができます。例えば ：

```markdown
- Comments are hidden in the generated PDF.
```

### Aspose.Words for .NET を使用して PDF 内のコメントを削除するためのソース コードの例

Aspose.Words for .NET を使用して PDF ファイル内のコメントを削除する完全なソース コードを次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// PDF 内のコメントを非表示にします。
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ファイルからコメントを削除する方法を学びました。適切なレイアウト オプションを使用することで、PDF の生成時にコメントを非表示にすることができました。 Aspose.Words for .NET は、Word ファイルを操作し、PDF を含むさまざまな形式に変換するための優れた柔軟性を提供します。この知識を応用して、Aspose.Words for .NET を使用して独自の PDF ファイル内のコメントを削除できるようになりました。

### PDF ファイル内のコメントを削除するための FAQ

#### Q: Aspose.Words for .NET にドキュメントをアップロードするにはどうすればよいですか?

 A: を使用してください。`Document`ファイルからドキュメントをロードするための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET で生成された PDF 内のコメントを非表示にするにはどうすればよいですか?

 A: を使用してください。`CommentDisplayMode`の財産`LayoutOptions` PDF 生成時にコメントを表示する方法を設定するオブジェクト。コメントを非表示にするには、このプロパティを次のように設定します。`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Q: Aspose.Words for .NET を使用してドキュメントを PDF として保存するにはどうすればよいですか?

 A: を使用してください。`Save`の方法`Document`オブジェクトを使用してドキュメントを PDF 形式で保存します。 PDFファイルのフルパスを指定します。

```csharp
doc.Save("path/to/the/file.pdf");
```
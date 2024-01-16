---
title: 単語のリビジョンの種類を取得する
linktitle: 単語のリビジョンの種類を取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の単語のリビジョン タイプを取得します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/get-revision-types/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内の単語のリビジョンの種類を取得する方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントをロードする

最初のステップは、リビジョンを含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ 2: 段落を段階的に進めていく

次に、文書の段落を調べて、各段落に関連付けられている単語の改訂の種類を確認します。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Aspose.Words for .NET を使用したリビジョン タイプの取得のソース コード例

Aspose.Words for .NET を使用してドキュメント内のリビジョン タイプを取得するための完全なソース コードを次に示します。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の単語のリビジョンの種類を取得する方法を学びました。文書をロードし、段落を調べ、各段落に関連付けられた単語レビューの種類を確認する手順に従いました。この知識を応用して、Aspose.Words for .NET を使用して独自の Word 文書内の単語レビューを分析できるようになりました。

### リビジョンタイプの単語の取得に関する FAQ

#### Q: Aspose.Words for .NET にドキュメントをアップロードするにはどうすればよいですか?

 A: を使用してください。`Document`ファイルからドキュメントをロードするための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でドキュメント内の段落をループするにはどうすればよいですか?

 A: を使用してください。`Paragraphs`ドキュメントセクションのプロパティを使用して段落のコレクションを取得します。その後、ループを使用して各段落をループすることができます。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     //ここで各段落を処理します
}
```

#### Q: Aspose.Words for .NET で段落が移動 (削除) されたかどうかを確認するにはどうすればよいですか?

 A: 段落の`IsMoveFromRevision`プロパティを参照して、移動（削除）されたかどうかを確認します。

```csharp
if (paragraph. IsMove

FromRevision)
{
     //段落が移動（削除）されました
}
```

#### Q: Aspose.Words for .NET で段落が移動 (挿入) されたかどうかを確認するにはどうすればよいですか?

 A: 段落の`IsMoveToRevision`プロパティを使用して、移動 (挿入) されたかどうかを確認します。

```csharp
if (paragraph.IsMoveToRevision)
{
     //段落が移動（挿入）されました
}
```
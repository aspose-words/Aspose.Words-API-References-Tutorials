---
title: 単語の修正タイプを取得する
linktitle: 単語の修正タイプを取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の単語の修正タイプを取得します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/get-revision-types/
---

このステップ バイ ステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内の単語のリビジョンの種類を取得する方法について説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を説明します。

## ステップ1: ドキュメントの読み込み

最初のステップは、修正を含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ2: 段落を順に確認する

次に、ドキュメントの段落を確認して、各段落に関連付けられている単語の修正の種類を確認します。

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

### Aspose.Words for .NET を使用してリビジョン タイプを取得するためのサンプル ソース コード

Aspose.Words for .NET を使用してドキュメント内のリビジョン タイプを取得するための完全なソース コードは次のとおりです。

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

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の単語の修正の種類を取得する方法を学習しました。ドキュメントを読み込み、段落を調べ、各段落に関連付けられた単語の修正の種類を確認する手順を実行しました。これで、この知識を適用して、Aspose.Words for .NET を使用して独自の Word 文書内の単語の修正を分析できます。

### 単語の修正タイプを取得するためのFAQ

#### Q: Aspose.Words for .NET でドキュメントをアップロードするにはどうすればよいですか?

 A:`Document`ファイルからドキュメントを読み込むための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でドキュメント内の段落をループするにはどうすればよいですか?

 A:`Paragraphs`ドキュメント セクションのプロパティを使用して段落のコレクションを取得します。その後、ループを使用して各段落をループできます。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     //ここで各段落を処理します
}
```

#### Q: Aspose.Words for .NET で段落が移動 (削除) されたかどうかを確認するにはどうすればよいですか?

 A: 段落の`IsMoveFromRevision`プロパティが移動 (削除) されたかどうかを確認します。

```csharp
if (paragraph. IsMove

FromRevision)
{
     //段落は移動されました（削除されました）
}
```

#### Q: Aspose.Words for .NET で段落が移動 (挿入) されたかどうかを確認するにはどうすればよいですか?

 A: 段落の`IsMoveToRevision`移動 (挿入) されたかどうかを確認するプロパティ。

```csharp
if (paragraph.IsMoveToRevision)
{
     //段落が移動（挿入）されました
}
```
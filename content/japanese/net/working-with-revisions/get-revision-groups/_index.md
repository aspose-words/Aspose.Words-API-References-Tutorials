---
title: リビジョングループの取得
linktitle: リビジョングループの取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のリビジョン グループを取得します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/get-revision-groups/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内のリビジョン グループを取得する方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントをロードする

最初のステップは、リビジョンを含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ 2: リビジョン グループを参照する

次に、文書内に存在する改訂グループをループして、作成者、改訂タイプ、改訂テキストなどの詳細を表示します。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Aspose.Words for .NET を使用したリビジョン グループの取得のソース コード例

Aspose.Words for .NET を使用してドキュメント内のリビジョン グループを取得するための完全なソース コードを次に示します。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のリビジョン グループを取得する方法を学びました。手順に従ってドキュメントをロードし、レビュー グループを参照して、作成者やレビュー タイプなどの詳細を表示します。この知識を応用して、Aspose.Words for .NET を使用して独自の Word 文書のリビジョンを分析できるようになりました。

### よくある質問

#### Q: Aspose.Words for .NET にドキュメントをアップロードするにはどうすればよいですか?

 A: を使用してください。`Document`ファイルからドキュメントをロードするための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でドキュメント内のリビジョン グループを参照するにはどうすればよいですか?

 A: を使用してください。`Groups`ドキュメントのプロパティ`Revisions`リビジョン グループのコレクションを取得するオブジェクト。その後、ループを使用して各レビュー グループをループすることができます。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     //ここで各レビューグループを処理します
}
```

#### Q: Aspose.Words for .NET でレビュー グループの作成者を取得するにはどうすればよいですか?

 A: を使用してください。`Author`の財産`RevisionGroup`リビジョン グループの作成者を取得するオブジェクト。

```csharp
string author = group.Author;
```

#### Q: Aspose.Words for .NET でリビジョン グループのリビジョン タイプを取得するにはどうすればよいですか?

 A: を使用してください。`RevisionType`の財産`RevisionGroup`オブジェクトを使用してグループのリビジョン タイプを取得します。

```csharp
string revisionType = group.RevisionType;
```
---
title: リビジョングループを取得
linktitle: リビジョングループを取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のリビジョン グループを取得します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/get-revision-groups/
---

このステップ バイ ステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内のリビジョン グループを取得する方法について説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を説明します。

## ステップ1: ドキュメントの読み込み

最初のステップは、修正を含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ2: リビジョングループを参照する

次に、ドキュメント内に存在するリビジョン グループをループし、作成者、リビジョン タイプ、リビジョン テキストなどの詳細を表示します。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Aspose.Words for .NET を使用してリビジョン グループを取得するためのサンプル ソース コード

Aspose.Words for .NET を使用してドキュメント内のリビジョン グループを取得するための完全なソース コードは次のとおりです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のリビジョン グループを取得する方法を学習しました。手順に従って文書を読み込み、レビュー グループを参照し、作成者やレビュー タイプなどの詳細を表示しました。この知識を適用して、Aspose.Words for .NET を使用して独自の Word 文書のリビジョンを分析できるようになりました。

### よくある質問

#### Q: Aspose.Words for .NET でドキュメントをアップロードするにはどうすればよいですか?

 A:`Document`ファイルからドキュメントを読み込むための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でドキュメント内のリビジョン グループを参照するにはどうすればよいですか?

 A:`Groups`文書のプロパティ`Revisions`オブジェクトを使用して、リビジョン グループのコレクションを取得します。次に、ループを使用して各レビュー グループをループできます。

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     //各レビューグループをここで処理します
}
```

#### Q: Aspose.Words for .NET でレビュー グループの作成者を取得するにはどうすればよいですか?

 A:`Author`の財産`RevisionGroup`リビジョン グループの作成者を取得するためのオブジェクト。

```csharp
string author = group.Author;
```

#### Q: Aspose.Words for .NET でリビジョン グループのリビジョン タイプを取得するにはどうすればよいですか?

 A:`RevisionType`の財産`RevisionGroup`グループのリビジョン タイプを取得するためのオブジェクト。

```csharp
string revisionType = group.RevisionType;
```
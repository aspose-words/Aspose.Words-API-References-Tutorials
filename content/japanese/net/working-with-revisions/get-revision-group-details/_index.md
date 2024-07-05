---
title: リビジョングループの詳細を取得
linktitle: リビジョングループの詳細を取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のリビジョン グループの詳細を取得します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/get-revision-group-details/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内の一連の変更の詳細を取得する方法を説明します。完全なソース コードを提供し、マークダウン出力の書式設定方法を説明します。

## ステップ1: ドキュメントの読み込み

最初のステップは、修正を含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ2: リビジョンを参照する

次に、ドキュメント内に存在するリビジョンをループし、タイプ、作成者、日付、および改訂されたテキストなどの詳細を表示します。

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Aspose.Words for .NET を使用してリビジョン グループの詳細を取得するためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用してドキュメント内の一連の変更の詳細を取得するための完全なソース コードです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のリビジョン グループの詳細を取得する方法を学習しました。ループと適切なプロパティを使用することで、リビジョンの種類、作成者、日付、および変更されたテキストなどの詳細を表示できました。Aspose.Words for .NET には、リビジョン管理など、Word 文書を操作するための強力な機能が多数用意されています。この知識を活用して、Aspose.Words for .NET を使用して独自の Word 文書にリビジョン グループの詳細を取得できるようになりました。

### よくある質問

#### Q: 修正を加えたドキュメントを Aspose.Words for .NET に読み込むにはどうすればよいですか?

 A:`Document` Aspose.Words for .NET のクラスを使用して、リビジョンを含むファイルからドキュメントを読み込みます。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でリビジョン グループの詳細を取得するにはどうすればよいですか?

A: ループを使用してドキュメントのリビジョンを調べ、各リビジョンのプロパティにアクセスして必要な詳細を取得します。`RevisionType`, `Author`, `DateTime`そして`ParentNode`プロパティを使用して、それぞれリビジョンの種類、作成者、日付、および改訂されたテキストを取得します。

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Q: Aspose.Words for .NET でリビジョンがグループに属しているかどうかを確認する方法を教えてください。

 A:`Group`の財産`Revision`オブジェクトを使用して、リビジョンがグループに属しているかどうかを確認します。`Group`財産は`null`これは、リビジョンがどのグループにも属していないことを意味します。

```csharp
if (revision.Group != null)
{
      //このリビジョンはグループに属しています
}
else
{
      //このリビジョンはどのグループにも属していません
}
```
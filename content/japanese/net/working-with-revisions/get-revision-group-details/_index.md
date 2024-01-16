---
title: リビジョングループの詳細の取得
linktitle: リビジョングループの詳細の取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のリビジョン グループの詳細を取得します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/get-revision-group-details/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内のリビジョンのグループの詳細を取得する方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントをロードする

最初のステップは、リビジョンを含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ 2: リビジョンを参照する

次に、ドキュメント内に存在する改訂をループして、種類、作成者、日付、改訂されたテキストなどの詳細を表示します。

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


### Aspose.Words for .NET を使用したリビジョン グループの詳細の取得のソース コード例

Aspose.Words for .NET を使用してドキュメント内のリビジョンのグループの詳細を取得する完全なソース コードを次に示します。

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

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のリビジョンのグループの詳細を取得する方法を学びました。ループと適切なプロパティを使用することで、改訂タイプ、作成者、日付、改訂テキストなどの詳細を表示できました。 Aspose.Words for .NET は、リビジョン管理など、Word ドキュメントを操作するための強力な機能を多数提供します。この知識を利用して、Aspose.Words for .NET を使用してリビジョン グループの詳細を独自の Word 文書に取り込むことができるようになりました。

### よくある質問

#### Q: リビジョンを含むドキュメントを Aspose.Words for .NET にロードするにはどうすればよいですか?

 A: を使用してください。`Document`Aspose.Words for .NET のクラスを使用して、リビジョンを含むファイルからドキュメントをロードします。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でリビジョン グループの詳細を取得するにはどうすればよいですか?

 A: ループを使用してドキュメントのリビジョンを調べ、各リビジョンのプロパティにアクセスして、必要な詳細を取得します。使用できます`RevisionType`, `Author`, `DateTime`そして`ParentNode`プロパティを使用して、リビジョン タイプ、作成者、日付、および改訂されたテキストをそれぞれ取得します。

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

#### Q: リビジョンが Aspose.Words for .NET のグループに属しているかどうかを確認するにはどうすればよいですか?

 A: を使用してください。`Group`の財産`Revision`オブジェクトを使用して、リビジョンがグループに属しているかどうかを確認します。もし`Group`財産は`null`、これは、リビジョンがどのグループにも属していないことを意味します。

```csharp
if (revision.Group != null)
{
      //リビジョンはグループに属しています
}
else
{
      //リビジョンはどのグループにも属していません
}
```
---
title: Word 文書内で等しいかどうかを比較する
linktitle: Word 文書内で等しいかどうかを比較する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントに等しいものを比較する機能の C# ソース コードを説明するステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/compare-documents/compare-for-equal/
---
このチュートリアルでは、Aspose.Words for .NET を使用して Word ドキュメントに等しいかどうかを比較する機能を使用する方法を説明します。以下の手順に従ってソース コードを理解し、変更を適用します。

## ステップ 1: 文書の比較

まず、比較する 2 つのドキュメントをロードします。この例では、`Clone()`元のドキュメントのコピーを作成するメソッド。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## ステップ 2: 文書の比較

これから使用するのは、`Compare()` 2 つの文書を比較する方法。このメソッドは、元のドキュメント内の変更をマークします。その方法は次のとおりです。

```csharp
//書類を比較する
docA.Compare(docB, "user", DateTime.Now);

//書類が等しいかどうかを確認する
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Aspose.Words for .NET を使用した Compare For Equal のソース コード例

Aspose.Words for .NET を使用した比較機能の完全なソース コードは次のとおりです。

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA には変更がリビジョンとして含まれるようになりました。
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

このコードを使用すると、Aspose.Words for .NET を使用して 2 つのドキュメントを比較し、それらが同じかどうかを判断できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET の同等比較機能を使用してドキュメントの同等性を比較する方法を検討しました。 2 つの文書を比較し、リビジョンを分析することで、文書の内容が同じかどうか、または文書間に相違点があるかどうかを判断できます。 Aspose.Words for .NET は強力なドキュメント比較機能を提供し、ドキュメントの類似点と相違点を識別するプロセスを自動化できます。

### よくある質問

#### Q: Aspose.Words for .NET でドキュメントの同等性を比較する目的は何ですか?

A: Aspose.Words for .NET でドキュメントの同等性を比較すると、2 つのドキュメントの内容が同じかどうかを識別できます。ドキュメントを比較することで、それらが同一であるかどうか、またはドキュメント間に相違点があるかどうかを判断できます。

#### Q: Aspose.Words for .NET を使用して 2 つのドキュメントが等しいかどうかを比較するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して 2 つのドキュメントが等しいかどうかを比較するには、次の手順に従います。
1. 比較する 2 つのドキュメントを別々の Document オブジェクトにロードします。
2. 使用`Compare()`一方のドキュメントでメソッドを使用し、もう一方のドキュメントをパラメータとして指定します。この方法では、ドキュメントを比較し、元のドキュメントの変更をマークします。
3. チェックしてください`Revisions`元のドキュメントのプロパティ。カウントがゼロの場合は、ドキュメントが同一であることを意味します。

#### Q: 比較プロセスをカスタマイズしたり、特定の比較オプションを提供したりできますか?

A: はい、Aspose.Words for .NET には、比較プロセスをカスタマイズするためのさまざまなオプションが用意されています。ドキュメントの比較方法を制御したり、比較方法や書式変更などの比較オプションを指定したり、特定の要素を無視したりできます。比較プロセスのカスタマイズの詳細については、Aspose.Words for .NET のドキュメントを参照してください。

#### Q: ドキュメント間の具体的な違いを特定するために、より詳細な比較を実行できますか?

 A: はい、次の手順を繰り返すことで、より詳細な比較を実行してドキュメント間の具体的な違いを特定できます。`Revisions`原本資料のコレクション。各リビジョンは、ドキュメント間の変更または相違を表します。変更の種類（挿入、削除、書式変更）やドキュメントの影響範囲など、各リビジョンの詳細にアクセスできます。
---
title: Word 文書のオプションを比較する
linktitle: Word 文書のオプションを比較する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用した Word ドキュメント機能のオプション比較の C# ソース コードを説明するステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/compare-documents/compare-options/
---
このチュートリアルでは、Aspose.Words for .NET で Word 文書のオプションを比較機能を使用する方法を説明します。以下の手順に従ってソース コードを理解し、変更を適用します。

## ステップ 1: ドキュメントをカスタム オプションと比較する

まず、比較する 2 つのドキュメントをロードします。この例では、`Clone()`元のドキュメントのコピーを作成するメソッド。その方法は次のとおりです。

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## ステップ 2: 比較オプションの構成

次に、比較オプションを作成して、比較オプションを構成します。`CompareOptions`オブジェクトを作成し、必要に応じてさまざまなプロパティを設定します。その方法は次のとおりです。

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## ステップ 3: ドキュメントをカスタム オプションと比較する

これから使用するのは、`Compare()` つのドキュメントを比較するためのカスタム オプションを渡すメソッド。このメソッドは、元のドキュメント内の変更をマークします。その方法は次のとおりです。

```csharp
//カスタム オプションを使用してドキュメントを比較する
docA.Compare(docB, "user", DateTime.Now, options);

//書類が等しいかどうかを確認する
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Aspose.Words for .NET を使用した比較オプションのソース コード例

Aspose.Words for .NET を使用したオプション比較機能の完全なソース コードは次のとおりです。

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

このコードを使用すると、Aspose.Words for .NET と比較するときに特定の要素を無視するカスタム オプションを使用して 2 つのドキュメントを比較できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET の比較オプションを使用して、2 つのドキュメントを比較する際の比較プロセスをカスタマイズする方法を学びました。別のオプションを指定すると、特定の要素を無視して、比較プロセスをより柔軟にすることができます。この機能により、比較プロセスをより詳細に制御し、特定の要件に合わせて調整することができます。 Aspose.Words for .NET は強力なドキュメント比較機能を提供し、必要に応じて特定の要素を無視しながらドキュメント間の相違点を簡単に特定できるようにします。

### よくある質問

#### Q: Aspose.Words for .NET で比較オプションを使用する目的は何ですか?

A: Aspose.Words for .NET の比較オプションを使用すると、2 つのドキュメントを比較する際の比較プロセスをカスタマイズできます。これらのオプションを使用すると、書式変更、ヘッダーとフッター、テーブル、フィールド、コメント、テキストボックス、脚注など、比較中に無視する要素を指定できます。

#### Q: Aspose.Words for .NET で比較オプションを使用するにはどうすればよいですか?

A: Aspose.Words for .NET で比較オプションを使用するには、次の手順に従います。
1. 比較する 2 つのドキュメントを別々の Document オブジェクトにロードします。
2. 使用`Clone()`元のドキュメントのコピーを作成するメソッド。
3. を作成します`CompareOptions`オブジェクトを作成し、そのプロパティを設定して比較プロセスをカスタマイズします。比較中に無視する要素を指定できます。
4. 使用`Compare()`一方のドキュメントでメソッドを実行し、もう一方のドキュメントと`CompareOptions`オブジェクトをパラメータとして指定します。このメソッドは、指定されたオプションに基づいてドキュメントを比較し、元のドキュメントの変更をマークします。
5. チェックしてください`Revisions`元のドキュメントのプロパティ。カウントがゼロの場合は、指定されたオプションを考慮すると、ドキュメントが同一であることを意味します。

#### Q: CompareOptions で使用できる一般的なオプションは何ですか?

A: CompareOptions で使用できる一般的なオプションには次のものがあります。
- `IgnoreFormatting`: 書式設定の変更を無視します。
- `IgnoreHeadersAndFooters`: ヘッダーとフッターの変更を無視します。
- `IgnoreCaseChanges`: 大文字と小文字の変更を無視します。
- `IgnoreTables`: テーブルの変更を無視します。
- `IgnoreFields`: フィールドの変更を無視します。
- `IgnoreComments`: コメントの変更を無視します。
- `IgnoreTextboxes`テキストボックス内の変更を無視します。
- `IgnoreFootnotes`: 脚注の変更を無視します。

#### Q: ドキュメントの比較中に特定の要素に対してカスタム オプションを使用できますか?

 A: はい、ドキュメントの比較中に特定の要素に対してカスタム オプションを使用できます。のプロパティを設定することで、`CompareOptions`それに応じて、比較中にどの要素を無視し、どの要素を考慮するかを選択できます。
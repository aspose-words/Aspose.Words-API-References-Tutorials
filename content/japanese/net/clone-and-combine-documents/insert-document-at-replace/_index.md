---
title: 置換時にドキュメントを挿入
linktitle: 置換時にドキュメントを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して置換時にドキュメントを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/clone-and-combine-documents/insert-document-at-replace/
---
このチュートリアルでは、Aspose.Words for .NET の [置換時にドキュメントを挿入] 機能を使用して、置換時にドキュメントを別のドキュメントに挿入する方法を説明します。以下の手順に従ってソース コードを理解し、ドキュメントの挿入を実行します。

## ステップ 1: メインドキュメントをロードする

まず、ドキュメントのディレクトリを指定し、メインドキュメントを Document オブジェクトにロードします。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## ステップ 2: 検索および置換のオプションを構成する

次に、検索方向と、ドキュメントを別のドキュメントに挿入するための置換コールバックを指定して、検索と置換のオプションを構成します。その方法は次のとおりです。

```csharp
//検索および置換のオプションを構成します。
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## ステップ 3: 置換メソッドの呼び出し

次に、replace メソッドを呼び出して、構成されたオプションを使用して、指定されたテキストを検索し、空の文字列に置き換えます。その方法は次のとおりです。

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Aspose.Words for .NET を使用した「置換時にドキュメントを挿入」のソース コード例

Aspose.Words for .NET を置き換える場合のドキュメントの挿入機能の完全なソース コードは次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

//検索と置換のオプションを設定します。
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// replace メソッドを呼び出します。
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET の置換時にドキュメントを挿入機能を使用して、置換中にドキュメントを別のドキュメントに挿入する方法を検討しました。検索と置換のオプションを構成し、必要なデータを提供すると、特定のプレースホルダーを他のドキュメント テンプレートまたはセクションの内容に置き換えてドキュメントを動的に組み立てることができます。 Aspose.Words for .NET は、複雑なドキュメント操作タスクを管理するための強力かつ柔軟な方法を提供し、ドキュメント作成とコンテンツ挿入シナリオを自動化するための貴重なツールとなります。

### よくある質問

#### Q: 置換中にドキュメントを別のドキュメントに挿入する目的は何ですか?

A: 置換中にドキュメントを別のドキュメントに挿入すると、特定のプレースホルダーを別のドキュメントのコンテンツに動的に置き換えることができます。この機能は、さまざまな事前定義されたドキュメント テンプレートまたはセクションを特定のプレースホルダーに結合して、より大きなドキュメントを組み立てる場合に特に便利です。

#### Q: Aspose.Words for .NET を使用して置換中にドキュメントを別のドキュメントに挿入するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して置換中にドキュメントを別のドキュメントに挿入するには、次の手順に従います。
1. プレースホルダーを含むメインドキュメントを Document オブジェクトに読み込みます。
2. ドキュメントの挿入を処理するための検索方向と置換コールバックを含む、検索と置換のオプションを構成します。
3. 構成されたオプションを使用して、適切な検索パターンで replace メソッドを呼び出し、プレースホルダーを空の文字列に置き換えます。

#### Q: 置換時の挿入動作をカスタマイズできますか?

A: はい、カスタム ReplacingCallback を実装することで、置換中の挿入動作をカスタマイズできます。 IReplacingCallback インターフェイスから継承することにより、プレースホルダーを置換するときに、特定の要件に基づいてドキュメントを挿入および結合する方法を制御できます。

#### Q: 複数のプレースホルダーを異なるドキュメントに置き換えることはできますか?

A: はい、各プレースホルダーに適切な検索パターンを指定し、挿入する対応するドキュメントを指定することで、複数のプレースホルダーを異なるドキュメントで置き換えることができます。
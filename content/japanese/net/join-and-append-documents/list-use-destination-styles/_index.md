---
title: 宛先スタイルの使用リスト
linktitle: 宛先スタイルの使用リスト
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、宛先ドキュメントのリスト スタイルを保持しながら Word ドキュメントを結合および追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/list-use-destination-styles/
---

このチュートリアルでは、Aspose.Words for .NET のリスト使用宛先スタイル機能を使用する手順について説明します。この機能を使用すると、宛先ドキュメントのリスト スタイルを使用しながら、Word ドキュメントを結合および追加できます。

## 前提条件

始める前に、次のものがあることを確認してください。

1. Aspose.Words for .NET がインストールされています。Aspose Web サイトからダウンロードするか、NuGet 経由でインストールできます。
2. Visual Studio またはその他の C# 開発環境。

## ステップ1: ドキュメントディレクトリを初期化する

まず、ドキュメントディレクトリへのパスを設定する必要があります。`dataDir`ドキュメントが保存されているパスへの変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ソースドキュメントと宛先ドキュメントを読み込む

次に、Aspose.Wordsを使用してソースドキュメントと宛先ドキュメントをロードする必要があります。`Document`クラス。`Document`ドキュメント名に応じてコンストラクターを作成します。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ステップ3: ソース文書を宛先文書の後に継続するように設定する

ソース文書のコンテンツが宛先文書の終了後も継続されるようにするには、`SectionStart`ソース文書の最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ4: リストの書式設定を処理する

リストの書式設定を処理するには、ソース ドキュメント内の各段落を反復処理し、それがリスト項目であるかどうかを確認します。リスト項目である場合は、リスト ID を宛先ドキュメント内の既存のリストと比較します。同じ ID のリストが存在する場合は、ソース ドキュメントにリストのコピーを作成し、コピーしたリストを使用するように段落のリスト書式を更新します。

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## ステップ5: ソースドキュメントを宛先ドキュメントに追加する

これで、ソース文書を宛先文書に追加することができます。`AppendDocument`方法の`Document`クラス。`ImportFormatMode.UseDestinationStyles`パラメータにより、追加操作中に宛先ドキュメントのリスト スタイルが使用されるようになります。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## ステップ6: 最終文書を保存する

最後に、リスト使用宛先スタイル機能を有効にして、結合された文書を保存します。`Save`方法の`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Aspose.Words for .NET を使用したリスト使用宛先スタイルのサンプル ソース コード 

以下は、Aspose.Words for .NET を使用した C# の「List Use Destination Styles」機能の完全なソース コードです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//ソース ドキュメントを、宛先ドキュメントの終了後すぐに継続するように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//作成されたリストを追跡します。
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			//宛先ドキュメントにこのIDのリストがすでに含まれていないか確認してください。含まれている場合は、
			// 2 つのリストが一緒に実行される原因になります。代わりに、ソース ドキュメントにリストのコピーを作成します。
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				//このIDに対して新しくコピーされたリストが既に存在する場合は、保存されたリストを取得します。
				//現在の段落で使用します。
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					//このリストのコピーをドキュメントに追加し、後で参照できるように保存します。
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				//この段落のリストをコピーしたリストに設定します。
				para.ListFormat.List = currentList;
			}
		}
	}
	//ソース ドキュメントを宛先ドキュメントの末尾に追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

これで完了です。Aspose.Words for .NET を使用して、リストの宛先スタイルの使用機能を正常に実装しました。最終的なドキュメントには、宛先ドキュメントのリスト スタイルが結合されたコンテンツが含まれます。
---
title: リスト使用宛先スタイル
linktitle: リスト使用宛先スタイル
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、宛先ドキュメントのリスト スタイルを維持しながら Word ドキュメントを結合および追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/list-use-destination-styles/
---

このチュートリアルでは、Aspose.Words for .NET の宛先スタイルのリスト表示機能を使用するプロセスを説明します。この機能を使用すると、宛先ドキュメントのリスト スタイルを使用しながら、Word ドキュメントを結合および追加できます。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. Aspose.Words for .NET がインストールされています。 Aspose Web サイトからダウンロードするか、NuGet 経由でインストールできます。
2. Visual Studio またはその他の C# 開発環境。

## ステップ 1: ドキュメント ディレクトリを初期化する

まず、ドキュメント ディレクトリへのパスを設定する必要があります。の値を変更します。`dataDir`変数をドキュメントが配置されているパスに設定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ソースドキュメントと宛先ドキュメントをロードする

次に、Aspose.Words を使用してソース ドキュメントと宛先ドキュメントをロードする必要があります。`Document`クラス。ファイル名を更新します。`Document`ドキュメント名に従ってコンストラクターを作成します。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ステップ 3: ソースドキュメントを宛先ドキュメントの後に継続するように設定する

ソース文書のコンテンツが宛先文書の終了後も継続されるようにするには、`SectionStart`ソースドキュメントの最初のセクションのプロパティを`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ 4: リストのフォーマットを処理する

リストの書式設定を処理するには、ソース文書の各段落を繰り返し処理し、それがリスト項目であるかどうかを確認します。存在する場合は、リスト ID を宛先ドキュメント内の既存のリストと比較します。同じ ID のリストが存在する場合は、ソース文書内にリストのコピーを作成し、コピーされたリストを使用するように段落のリスト形式を更新します。

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

## ステップ 5: ソースドキュメントを宛先ドキュメントに追加する

これで、`AppendDocument`の方法`Document`クラス。の`ImportFormatMode.UseDestinationStyles`パラメータを指定すると、追加操作中に宛先ドキュメントのリスト スタイルが使用されるようになります。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## ステップ 6: 最終ドキュメントを保存する

最後に、「宛先スタイルのリスト使用」機能を有効にして、結合されたドキュメントを保存します。`Save`の方法`Document`クラス。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Aspose.Words for .NET を使用したリスト使用宛先スタイルのソース コード例 

Aspose.Words for .NET を使用した C# の "List Use Destination Styles" 機能の完全なソース コードは次のとおりです。


```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//ソース文書が宛先文書の終了直後に継続するように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//作成されたリストを追跡します。
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			//宛先ドキュメントにこの ID を持つリストが既に含まれているかどうかを確認してください。そうなった場合、これは可能性があります
			// つのリストを一緒に実行します。代わりに、ソース文書内にリストのコピーを作成します。
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				//この ID には新しくコピーされたリストがすでに存在します。保存されているリストを取得します。
				//そしてそれを現在の段落で使用します。
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
	//ソース文書を宛先文書の末尾に追加します。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、宛先スタイルのリスト使用機能を正常に実装しました。最終的なドキュメントには、宛先ドキュメントのリスト スタイルとマージされたコンテンツが含まれます。
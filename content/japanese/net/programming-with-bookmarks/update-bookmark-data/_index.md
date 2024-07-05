---
title: Word 文書のブックマーク データを更新する
linktitle: ブックマークデータの更新
second_title: Aspose.Words ドキュメント処理 API
description: .NET の Word 文書機能における Aspose.Words ブックマーク データ更新の C# ソース コードを説明するステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/update-bookmark-data/
---

このチュートリアルでは、Aspose.Words for .NET の Word 文書内のブックマーク データの更新機能を理解して実装するためのステップ バイ ステップ ガイドを紹介します。この機能を使用すると、C# ソース コードを使用して Word 文書内のブックマークのコンテンツとプロパティを更新できます。

## 要件

チュートリアルを進める前に、次の要件が満たされていることを確認してください。

- Aspose.Words for .NET ライブラリがインストールされている
- C#プログラミング言語の基礎知識
- Visual Studio またはその他の互換性のある IDE

## ステップ1: ドキュメントを読み込む

この手順では、更新するブックマークを含む Word 文書を読み込みます。文書が特定のディレクトリに保存されていると仮定すると、次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されている実際のディレクトリ パスを入力します。

## ステップ2: ブックマークにアクセスする

ブックマーク データを更新するには、まずドキュメント内の特定のブックマークにアクセスする必要があります。各ブックマークには、一意の名前が関連付けられています。次のコードを使用して、「MyBookmark1」という名前のブックマークにアクセスします。

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

ブックマーク名がドキュメント内のものと一致していることを確認してください。必要に応じて変更できます。

## ステップ3: ブックマークのプロパティとコンテンツを更新する

ブックマークにアクセスしたら、そのプロパティとコンテンツを更新できます。次のコード スニペットでは、ブックマークの名前とテキストを更新します。

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

ブックマーク名と新しいテキストは、必要に応じてカスタマイズできます。上記のコードは、ブックマークの名前を「RenamedBookmark」に変更し、テキスト コンテンツを更新します。

## ステップ4: 更新したドキュメントを保存する

ブックマークデータを更新したら、変更したドキュメントを保存する必要があります。ドキュメントを保存するには、次のコードを使用します。

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

このコードは、変更されたドキュメントを「UpdatedDocument.docx」という名前で元のドキュメントと同じディレクトリに保存します。

### Aspose.Words for .NET を使用してブックマーク データを更新するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されている実際のディレクトリ パスを入力します。

## 結論

おめでとうございます。Aspose.Words for .NET を使用してブックマーク データを更新する方法を学習しました。このチュートリアルで説明されているステップ バイ ステップ ガイドに従うことで、この機能を C# アプリケーションに組み込み、Word ドキュメント内のブックマークをプログラムで操作できるようになります。

### Word 文書のブックマーク データの更新に関する FAQ

#### Q: ブックマーク データの更新機能は、Word 文書内のブックマークでのみ機能しますか?

A: はい、ブックマーク データの更新機能は、Word 文書内のブックマーク専用に設計されています。この機能を使用すると、Word 文書内のブックマークのコンテンツとプロパティを更新できます。

#### Q: テキスト以外のブックマークのプロパティを更新できますか?

 A: はい、テキストに加えて、ブックマーク名、ブックマーク範囲などの他のブックマークプロパティも更新できます。`Bookmark`必要なプロパティを更新するオブジェクト。

#### Q: 同じドキュメント内の複数のブックマークを更新できますか?

A: はい、各ブックマークに対してアクセスと更新の手順を繰り返すことで、同じドキュメント内の複数のブックマークを更新できます。更新するブックマークごとに、必ず一意のブックマーク名を使用してください。

#### Q: ブックマークデータの更新機能は元のドキュメントを変更しますか?

A: はい、ブックマーク データ更新機能は、ブックマークのプロパティとコンテンツを更新して元のドキュメントを変更します。この機能を適用する前に、必ず元のドキュメントのコピーを保存してください。
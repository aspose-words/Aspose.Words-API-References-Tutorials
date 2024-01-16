---
title: ドキュメントページの設定
linktitle: ドキュメントページの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント レイアウトを設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/document-page-setup/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント レイアウトを構成するための C# ソース コードを説明します。この機能を使用すると、レイアウト モード、1 行あたりの文字数、および 1 ページあたりの行数を設定できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、構成する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: レイアウトを設定する

次に、ドキュメントのレイアウトを構成しましょう。次のコードを使用して、レイアウト モード、1 行あたりの文字数、および 1 ページあたりの行数を設定します。

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

このコードは、レイアウト モードを「グリッド」に設定し、1 行あたりの文字数と 1 ページあたりの行数を指定します。

### Aspose.Words for .NET を使用したドキュメント ページ設定のソース コード例


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//セクションのレイアウト モードを設定すると、ドキュメント グリッドの動作を定義できるようになります。
	// MS Word の [ページ設定] ダイアログに [ドキュメント グリッド] タブが表示されることに注意してください。
	//アジア言語が編集言語として定義されている場合。
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントのレイアウトを構成する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントのレイアウトを簡単にカスタマイズできます。
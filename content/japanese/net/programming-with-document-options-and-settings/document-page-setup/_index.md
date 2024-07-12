---
title: ドキュメントページ設定
linktitle: ドキュメントページ設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント レイアウトを設定するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/document-page-setup/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント レイアウトを構成するための C# ソース コードについて説明します。この機能を使用すると、レイアウト モード、1 行あたりの文字数、1 ページあたりの行数を設定できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、構成する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: レイアウトの設定

次に、ドキュメントのレイアウトを設定しましょう。次のコードを使用して、レイアウト モード、1 行あたりの文字数、1 ページあたりの行数を設定します。

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

このコードは、レイアウト モードを「グリッド」に設定し、行あたりの文字数とページあたりの行数を指定します。

### Aspose.Words for .NET を使用したドキュメント ページ設定のサンプル ソース コード


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//ドキュメント グリッドの動作を定義できるセクションのレイアウト モードを設定します。
	// MS Wordのページ設定ダイアログにドキュメントグリッドタブが表示されることに注意してください。
	//編集言語として定義されているアジア言語がある場合。
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

必ず正しいドキュメントパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントのレイアウトを構成する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントのレイアウトを簡単にカスタマイズできます。
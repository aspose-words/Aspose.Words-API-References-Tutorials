---
title: ページ設定とセクションの書式設定
linktitle: ページ設定とセクションの書式設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントのレイアウトとセクションの書式を設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

このチュートリアルでは、C# ソース コードを使用して、Aspose.Words for .NET でレイアウトとセクションの書式を設定する方法について説明します。この機能を使用すると、ページの向き、余白、用紙サイズを設定できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの作成

このステップでは、新しいドキュメントを作成します。次のコードを使用してドキュメントを作成し、コンストラクターを初期化します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントを保存するディレクトリの実際のパスを入力します。

## ステップ3: レイアウトを設定してドキュメントを保存する

次に、ドキュメントのレイアウトを設定しましょう。次のコードを使用して、向き、余白、用紙サイズを設定します。

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

このコードは、ページの向きを横向きに、左余白を 50 に、用紙サイズを 10x14 に設定します。

### Aspose.Words for .NET を使用してページ設定とセクションの書式を設定するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

ドキュメントを保存するディレクトリへの正しいパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントのレイアウトとセクションの書式設定を構成する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントのレイアウトと書式設定を簡単にカスタマイズできます。
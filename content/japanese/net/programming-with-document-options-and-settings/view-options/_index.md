---
title: 表示オプション
linktitle: 表示オプション
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント表示オプションを構成するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/view-options/
---

このチュートリアルでは、C# ソース コードを使用して Aspose.Words for .NET の表示オプションを構成する方法について説明します。この機能を使用すると、ドキュメントの表示モードとズーム レベルをカスタマイズできます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、表示オプションを構成する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: 表示オプションの設定

次に、ドキュメントの表示オプションを設定します。次のコードを使用して、表示モードとズーム レベルを設定します。

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

このコードは、表示モードを「PageLayout」に設定し、ズーム レベルを 50% に設定します。

### Aspose.Words for .NET を使用したビュー オプションのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

正しいドキュメントパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントの表示オプションを構成する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントの表示を簡単にカスタマイズできます。
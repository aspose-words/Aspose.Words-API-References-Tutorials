---
title: 表示オプション
linktitle: 表示オプション
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント表示オプションを構成するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/view-options/
---

このチュートリアルでは、Aspose.Words for .NET を使用して表示オプションを構成するための C# ソース コードを説明します。この機能を使用すると、ドキュメントの表示モードとズーム レベルをカスタマイズできます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、表示オプションを構成する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: 表示オプションの構成

次に、ドキュメントの表示オプションを構成します。次のコードを使用して、表示モードとズーム レベルを設定します。

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

このコードは、表示モードを「PageLayout」に設定し、ズーム レベルを 50% に設定します。

### Aspose.Words for .NET を使用した表示オプションのソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメント表示オプションを構成する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントの表示を簡単にカスタマイズできます。
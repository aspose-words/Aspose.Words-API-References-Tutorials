---
title: 文法およびスペルの間違いを表示する
linktitle: 文法およびスペルの間違いを表示する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内の文法エラーおよびスペル エラーを表示できるようにするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

このチュートリアルでは、Aspose.Words for .NET で文法エラーやスペル エラーを表示できるようにするための C# ソース コードを説明します。この機能を使用すると、文書内の文法およびスペルの間違いを表示できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

この手順では、文法エラーとスペル エラーを表示する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: エラー表示を有効にする

次に、ドキュメント内の文法エラーとスペル エラーの表示を有効にします。エラー表示を有効にするには、次のコードを使用します。

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

このコードにより、文法エラーの表示が有効になります (`ShowGrammaticalErrors`) とスペルミス (`ShowSpellingErrors`) 文書に記載されています。

### Aspose.Words for .NET を使用して文法エラーとスペル エラーを表示するためのソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメント内の文法エラーとスペル エラーの表示を有効にする方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントでこの機能を簡単に有効にすることができます。
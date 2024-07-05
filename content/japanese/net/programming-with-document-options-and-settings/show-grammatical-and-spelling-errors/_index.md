---
title: 文法やスペルの間違いを表示する
linktitle: 文法やスペルの間違いを表示する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内の文法エラーやスペルエラーを表示できるようにするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

このチュートリアルでは、Aspose.Words for .NET で文法エラーやスペル エラーを表示できるようにするための C# ソース コードについて説明します。この機能を使用すると、ドキュメント内の文法エラーやスペル エラーを表示できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

このステップでは、文法エラーとスペルエラーを表示する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: エラー表示を有効にする

ここで、ドキュメント内の文法エラーとスペルエラーの表示を有効にします。エラー表示を有効にするには、次のコードを使用します。

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

このコードは文法エラーの表示を可能にします（`ShowGrammaticalErrors`) およびスペルミス (`ShowSpellingErrors`) を文書内に含めます。

### Aspose.Words for .NET を使用して文法およびスペルのエラーを表示するサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

正しいドキュメントパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NET を使用して、ドキュメント内の文法エラーやスペルエラーの表示を有効にする方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、自分のドキュメントでこの機能を簡単に有効にすることができます。
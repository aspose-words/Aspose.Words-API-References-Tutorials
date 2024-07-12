---
title: 編集言語として日本語を追加
linktitle: 編集言語として日本語を追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して日本語を編集言語として追加するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

このチュートリアルでは、Aspose.Words for .NET を使用して日本語を編集言語として追加する機能について、手順を追って理解し、実装する方法を説明します。この機能を使用すると、ドキュメントを読み込むときに言語の設定を行い、日本語を編集言語として追加できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、デフォルトの編集言語が含まれておらず、日本語を追加する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
LoadOptions loadOptions = new LoadOptions();

//ドキュメントを読み込むときに使用する言語設定を指定します。
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## ステップ3: デフォルトの言語を確認する

ドキュメントを読み込んだ後、デフォルトの編集言語が正しく日本語に設定されているかどうかを確認します。極東言語 ID を取得するには、次のコードを使用します。

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

コードは、極東の言語 ID が日本語の ID と一致するかどうかをチェックします。結果に応じて、対応するメッセージが表示されます。

### Aspose.Words for .NET を使用して日本語を編集言語として追加するためのサンプル ソース コード

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	//ドキュメントの読み込み時に使用される言語設定を指定します。
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```


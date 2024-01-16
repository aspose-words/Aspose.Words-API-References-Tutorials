---
title: 編集言語として日本語を追加
linktitle: 編集言語として日本語を追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して日本語を編集言語として追加するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

このチュートリアルでは、Aspose.Words for .NET を使用して編集言語として日本語を追加する機能を理解し、実装する方法を段階的に説明します。この機能を使用すると、ドキュメントをロードするときに言語設定を設定し、編集言語として日本語を追加できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、デフォルトの編集言語が含まれておらず、日本語を追加する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
LoadOptions loadOptions = new LoadOptions();

//ドキュメントをロードするときに使用される言語設定を設定します。
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## ステップ 3: デフォルトの言語を確認する

ドキュメントをロードした後、デフォルトの編集言語が日本語に正しく設定されているかどうかを確認します。次のコードを使用して極東言語 ID を取得します。

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

このコードは、極東言語 ID が日本語の ID と一致するかどうかをチェックします。結果に応じて、対応するメッセージを表示します。

### Aspose.Words for .NET を使用して日本語を編集言語として追加するソース コードの例

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	//ドキュメントの読み込み時に使用される言語設定を設定します。
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```


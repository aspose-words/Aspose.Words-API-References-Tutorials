---
title: デフォルトの編集言語としてロシア語を設定する
linktitle: デフォルトの編集言語としてロシア語を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ドキュメントの既定の編集言語としてロシア語を設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

このチュートリアルでは、Aspose.Words for .NET でロシア語を既定の編集言語として設定するための C# ソース コードについて説明します。この機能を使用すると、ドキュメントを読み込むときに既定の言語を設定できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、ロシア語をデフォルトの編集言語として設定する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: デフォルトの言語を確認する

ドキュメントをアップロードした後、デフォルトの言語が正しくロシア語に設定されているかどうかを確認します。デフォルトの言語 ID を取得するには、次のコードを使用します。

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

コードは、言語 ID がロシア語と一致するかどうかを確認します。結果に応じて、対応するメッセージが表示されます。

### Aspose.Words for .NET を使用してロシア語を既定の編集言語として設定するためのサンプル ソース コード

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

正しいドキュメントパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NETを使用して、ドキュメントの既定の編集言語としてロシア語を設定する方法を学びました。ステップガイドに従って
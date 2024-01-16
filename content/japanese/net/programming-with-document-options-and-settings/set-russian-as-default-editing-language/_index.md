---
title: ロシア語をデフォルトの編集言語として設定する
linktitle: ロシア語をデフォルトの編集言語として設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントのデフォルト編集言語としてロシア語を設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

このチュートリアルでは、Aspose.Words for .NET でロシア語をデフォルトの編集言語として設定するための C# ソース コードを説明します。この機能を使用すると、ドキュメントをロードするときにデフォルトの言語を設定できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、ロシア語をデフォルトの編集言語として設定する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: デフォルトの言語を確認する

ドキュメントをアップロードした後、デフォルト言語がロシア語に正しく設定されているかどうかを確認します。次のコードを使用して、デフォルトの言語 ID を取得します。

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

このコードは、言語 ID がロシア語の ID と一致するかどうかをチェックします。結果に応じて、対応するメッセージを表示します。

### Aspose.Words for .NET を使用してロシア語をデフォルトの編集言語として設定するためのソース コードの例

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用して、ドキュメントのデフォルトの編集言語としてロシア語を設定する方法を学習しました。ステップガイドに従ってください
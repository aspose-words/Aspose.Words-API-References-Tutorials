---
title: フォント名の解決
linktitle: フォント名の解決
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して HTML に変換するときに見つからないフォント名を解決するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/resolve-font-names/
---

このチュートリアルでは、Aspose.Words for .NET を使用して欠落しているフォント名を解決するための C# ソース コードを説明します。この機能を使用すると、ドキュメントを HTML に変換するときに、不足しているフォント名を自動的に解決できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、処理するドキュメントをロードします。次のコードを使用して、指定したディレクトリからドキュメントをロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

このコードは、次のインスタンスを作成します。`Document`指定されたディレクトリからドキュメントをロードします。

## ステップ 3: HTML バックアップ オプションの構成

次に、変換中に見つからないフォント名を解決するために HTML 保存オプションを構成します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`そして、`ResolveFontNames`というオプション`true`HTML に変換するときに欠落しているフォント名を解決します。また、`PrettyFormat`オプションはに設定されています`true`適切にフォーマットされた HTML コードを取得します。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に構成した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

このコードは、不足しているフォント名を自動的に解決することでドキュメントを HTML に変換し、変換された HTML ファイルを指定されたディレクトリに保存します。

### Aspose.Words for .NET を使用したフォント名の解決のソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

必ずドキュメント ディレクトリへの正しいパスを指定してください。`dataDir`変数。
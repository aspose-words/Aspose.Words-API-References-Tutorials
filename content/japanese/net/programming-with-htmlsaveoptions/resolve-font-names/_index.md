---
title: フォント名を解決する
linktitle: フォント名を解決する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して HTML に変換するときに、フォント名が見つからない場合の解決方法をステップバイステップで説明します。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/resolve-font-names/
---

このチュートリアルでは、Aspose.Words for .NET で見つからないフォント名を解決するための C# ソース コードについて説明します。この機能を使用すると、ドキュメントを HTML に変換するときに、見つからないフォント名を自動的に解決できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

このステップでは、処理するドキュメントを読み込みます。指定されたディレクトリからドキュメントを読み込むには、次のコードを使用します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

このコードはインスタンスを作成します`Document`指定されたディレクトリからドキュメントを読み込みます。

## ステップ3: HTMLバックアップオプションの設定

ここで、変換中に欠落しているフォント名を解決するために、HTML 保存オプションを設定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

このコードはインスタンスを作成します`HtmlSaveOptions`そして、`ResolveFontNames`オプション`true`HTMLに変換するときにフォント名が見つからない場合の解決に役立ちます。また、`PrettyFormat`オプションは`true`適切にフォーマットされた HTML コードを取得します。

## ステップ4: ドキュメントをHTMLに変換して保存する

最後に、先ほど設定した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

このコードは、不足しているフォント名を自動的に解決してドキュメントを HTML に変換し、変換された HTML ファイルを指定されたディレクトリに保存します。

### Aspose.Words for .NET を使用してフォント名を解決するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

ドキュメントディレクトリへの正しいパスを必ず指定してください。`dataDir`変数。
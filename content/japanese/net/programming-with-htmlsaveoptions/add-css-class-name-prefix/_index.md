---
title: CSSクラス名のプレフィックスを追加
linktitle: CSSクラス名のプレフィックスを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML に変換するときに CSS クラス名のプレフィックスを追加するためのステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

このチュートリアルでは、Aspose.Words for .NET を使用して CSS クラス名プレフィックスを追加するための C# ソース コードを説明します。この機能を使用すると、ドキュメントを HTML に変換するときに、生成された CSS クラス名にカスタム プレフィックスを追加できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、HTML に変換する Word ドキュメントを読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: HTML 保存オプションを設定する

次に、CSS スタイルシート タイプや CSS クラス名のプレフィックスなどの HTML 保存オプションを設定しましょう。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`とセット`CssStyleSheetType`に`CssStyleSheetType.External`外部 CSS スタイル シートを生成し、`CssClassNamePrefix`に`"pfx_"`接頭辞を付ける`"pfx_"`CSS クラスに名前を付けます。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に定義した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

このコードは、ドキュメントを HTML に変換し、CSS クラス名のプレフィックスを追加してファイルに保存します。

### Aspose.Words for .NET を使用して Css クラス名プレフィックスを追加するソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントを HTML に変換するときに CSS クラス名のプレフィックスを追加する方法を学習しました。このチュートリアルで提供されているステップバイステップのガイド手順に従って、変換された HTML ドキュメント内の CSS クラス名をカスタマイズできます。
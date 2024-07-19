---
title: CSSクラス名プレフィックスを追加する
linktitle: CSSクラス名プレフィックスを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML に変換するときに CSS クラス名プレフィックスを追加するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

このチュートリアルでは、C# ソース コードを使用して、Aspose.Words for .NET で CSS クラス名プレフィックスを追加する方法について説明します。この機能を使用すると、ドキュメントを HTML に変換するときに、生成された CSS クラス名にカスタム プレフィックスを追加できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、HTML に変換する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: HTML保存オプションを設定する

次に、CSS スタイルシートの種類や CSS クラス名のプレフィックスなどの HTML 保存オプションを設定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

このコードはインスタンスを作成します`HtmlSaveOptions`そしてセット`CssStyleSheetType`に`CssStyleSheetType.External`外部CSSスタイルシートを生成するため、`CssClassNamePrefix`に`"pfx_"`接頭辞を付ける`"pfx_"`CSS クラスに名前を付けます。

## ステップ4: ドキュメントをHTMLに変換して保存する

最後に、先ほど定義した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

このコードはドキュメントを HTML に変換し、CSS クラス名プレフィックスを追加したファイルに保存します。

### Aspose.Words for .NET を使用して CSS クラス名プレフィックスを追加するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

必ず正しいドキュメントパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントを HTML に変換するときに CSS クラス名プレフィックスを追加する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドの手順に従って、変換された HTML ドキュメントの CSS クラス名をカスタマイズできます。
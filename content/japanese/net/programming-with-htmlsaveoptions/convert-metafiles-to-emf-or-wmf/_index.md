---
title: メタファイルを EMF または WMF に変換する
linktitle: メタファイルを EMF または WMF に変換する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML に変換するときに、メタファイルを EMF または WMF 形式に変換するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---
## 導入

Aspose.Words for .NET の世界を深く掘り下げる旅へようこそ。今日は、Word 文書で SVG 画像を EMF または WMF 形式に変換するという巧妙なトリックを取り上げます。少し技術的に聞こえるかもしれませんが、心配はいりません。このチュートリアルを終える頃には、あなたもプロになっていることでしょう。熟練した開発者であっても、Aspose.Words for .NET を使い始めたばかりであっても、このガイドでは、知っておく必要のあるすべてのことをステップ バイ ステップで説明します。

## 前提条件

コードに進む前に、すべてが設定されていることを確認しましょう。必要なものは次のとおりです。

1. Aspose.Words for .NET ライブラリ: 最新バージョンであることを確認してください。最新バージョンでない場合は、以下からダウンロードできます。[ここ](https://releases.aspose.com/words/net/).
2. .NET Framework: マシンに .NET Framework がインストールされていることを確認します。
3. 開発環境: Visual Studio のような IDE を使用すると、作業が楽になります。
4. C# の基本知識: 専門家である必要はありませんが、基本的な理解があると役立ちます。

すべて揃いましたか？素晴らしい！始めましょう。

## 名前空間のインポート

まず最初に、必要な名前空間をインポートする必要があります。これは、使用するクラスとメソッドがどこにあるかをプログラムに伝えるため、非常に重要です。

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

これらの名前空間は、基本的なシステム関数から、このチュートリアルに必要な特定の Aspose.Words 機能まですべてをカバーします。

## ステップ1: ドキュメントディレクトリを設定する

まず、ドキュメント ディレクトリへのパスを定義します。これは、メタファイルを変換した後に Word ドキュメントが保存される場所です。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存する実際のパスを入力します。

## ステップ2: SVGでHTML文字列を作成する

次に、変換したい SVG 画像を含む HTML 文字列が必要です。簡単な例を次に示します。

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' 幅='500' 高さ='40' ビューボックス='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";
```

この HTML スニペットには、「Hello world!」という基本的な SVG が含まれています。

## ステップ3: ConvertSvgToEmfオプションを使用してHTMLをロードする

さて、私たちは`HtmlLoadOptions`HTMLでSVG画像をどのように処理するかを指定します。設定`ConvertSvgToEmf`に`true`SVG 画像が EMF 形式に変換されることを保証します。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

このコードスニペットは新しい`Document`指定された読み込みオプションを使用して HTML 文字列をオブジェクトに読み込みます。

## ステップ4: メタファイル形式のHtmlSaveOptionsを設定する

正しいメタファイル形式で文書を保存するには、`HtmlSaveOptions`ここでは、`MetafileFormat`に`HtmlMetafileFormat.Png`ですが、これを変更することもできます`Emf`または`Wmf`ニーズに応じて。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Png };
```

## ステップ5: ドキュメントを保存する

最後に、指定された保存オプションを使用してドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToPng.html", saveOptions);
```

これにより、定義どおりにメタファイル形式に変換されたドキュメントが指定されたディレクトリに保存されます。

## 結論

これで完了です。これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書内の SVG イメージを EMF または WMF 形式に正常に変換できました。この方法は、異なるプラットフォーム間での互換性を確保し、文書の視覚的な整合性を維持するのに便利です。コーディングを楽しんでください。

## よくある質問

### この方法を使用して他の画像形式を変換できますか?
はい、読み込みおよび保存オプションを適切に調整することで、さまざまな画像形式を変換できます。

### 特定の .NET Framework バージョンを使用する必要はありますか?
Aspose.Words for .NET は複数の .NET Framework バージョンをサポートしていますが、最高の互換性と機能を得るには、常に最新バージョンを使用することをお勧めします。

### SVG を EMF または WMF に変換する利点は何ですか?
SVG を EMF または WMF に変換すると、SVG が完全にサポートされていない環境でもベクター グラフィックスが保持され、正しくレンダリングされるようになります。

### 複数のドキュメントに対してこのプロセスを自動化できますか?
もちろんです! 複数の HTML ファイルをループし、同じプロセスを適用して、バッチ処理の変換を自動化できます。

### Aspose.Words for .NET のその他のリソースやサポートはどこで見つかりますか?
包括的なドキュメントが見つかります[ここ](https://reference.aspose.com/words/net/) Asposeコミュニティからサポートを受ける[ここ](https://forum.aspose.com/c/words/8).
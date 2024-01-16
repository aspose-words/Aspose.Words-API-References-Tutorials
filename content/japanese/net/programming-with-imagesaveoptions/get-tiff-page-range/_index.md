---
title: Tiff ページ範囲の取得
linktitle: Tiff ページ範囲の取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してさまざまな TIFF ページを抽出する方法を学びます。カスタム TIFF ファイルの完全なチュートリアル。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

このチュートリアルでは、提供されている C# ソース コードを調べて、Aspose.Words for .NET を使用してさまざまな TIFF ページを取得します。この機能を使用すると、ドキュメントから特定の範囲のページを抽出し、TIFF ファイルとして保存できます。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用して開発環境がセットアップされていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ 2: ドキュメントをロードする

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

このステップでは、`Document`メソッドを実行し、ロードする DOCX ファイルへのパスを渡します。

## ステップ 3: 完全なドキュメントを TIFF に保存する

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

このステップでは、`Save`メソッドを使用し、拡張子を付けて出力ファイルへのパスを指定します。`.tiff`.

## ステップ 4: ページ範囲のバックアップ オプションを構成する

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

このステップでは、特定のページ範囲のバックアップ オプションを構成します。新しいものを作成します`ImageSaveOptions`オブジェクトで目的の保存形式を指定します。ここでは TIFF 形式の場合は「Tiff」です。を使用しております`PageSet`抽出するページの範囲を指定します。ここではページ 0 からページ 1 (両端を含む) までです。また、TIFF 圧縮を次のように設定します。`Ccitt4`解像度は 160 dpi です。

## ステップ 5: ページ範囲を TIFF に保存する

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

この最後のステップでは、指定したページ範囲を TIFF 形式で保存します。`Save`メソッドを使用し、出力ファイルへのパスを渡します`.tiff`拡張子と、指定された保存オプションを追加します。

これで、ソース コードを実行してドキュメントから特定の範囲のページを取得し、TIFF ファイルとして保存できるようになりました。結果のファイルは、ドキュメント全体の場合は「WorkingWithImageSaveOptions.MultipageTiff.tiff」、指定されたページ範囲の場合は「WorkingWithImageSaveOptions.GetTiffPageRange.tiff」という名前で、指定されたディレクトリに保存されます。

### Aspose.Words for .NET を使用した Get Tiff Page Range のサンプル ソース コード

```csharp 

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してさまざまな TIFF ページを取得する機能を検討しました。ドキュメントから特定の範囲のページを抽出し、TIFF ファイルとして保存する方法を学習しました。

この機能は、文書から特定のページだけを抽出して、TIFF などの標準的な画像形式で保存する場合に便利です。圧縮および解像度のオプションをカスタマイズして、最高品質の TIFF ファイルを取得することもできます。

Aspose.Words for .NET は、ドキュメントの操作と生成のための広範な高度な機能を提供します。 TIFF ページ範囲の取得は、自由に使える数多くの強力なツールの 1 つです。

この機能を自由に Aspose.Words for .NET プロジェクトに統合して、ドキュメントから特定の範囲のページを抽出して TIFF 形式で保存できます。
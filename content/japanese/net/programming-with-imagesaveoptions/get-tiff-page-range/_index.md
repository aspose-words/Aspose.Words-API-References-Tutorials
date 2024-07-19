---
title: Tiff ページ範囲を取得
linktitle: Tiff ページ範囲を取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して TIFF ページの範囲を抽出する方法を学習します。カスタム TIFF ファイルの完全なチュートリアル。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

このチュートリアルでは、提供されている C# ソース コードを調べて、Aspose.Words for .NET を使用して TIFF ページの範囲を取得します。この機能を使用すると、ドキュメントから特定の範囲のページを抽出し、TIFF ファイルとして保存できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: ドキュメントの読み込み

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

このステップでは、`Document`メソッドを呼び出して、読み込む DOCX ファイルへのパスを渡します。

## ステップ3: 完全な文書をTIFFで保存する

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

このステップでは、完全な文書をTIFF形式で保存します。`Save`メソッドと拡張子を持つ出力ファイルへのパスを指定する`.tiff`.

## ステップ4: ページ範囲のバックアップオプションを構成する

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

このステップでは、特定のページ範囲のバックアップオプションを設定します。新しい`ImageSaveOptions`希望する保存形式を指定するオブジェクト。ここではTIFF形式の場合は「Tiff」。`PageSet`抽出したいページの範囲を指定します。ここでは0ページ目から1ページ目までです。また、TIFF圧縮を次のように設定します。`Ccitt4`解像度は160dpiです。

## ステップ5: ページ範囲をTIFFに保存する

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

この最後のステップでは、指定されたページ範囲をTIFF形式で保存します。`Save`メソッドを使用して出力ファイルへのパスを渡す`.tiff`拡張子と、指定された保存オプションを指定します。

これで、ソース コードを実行して、ドキュメントから特定の範囲のページを取得し、TIFF ファイルとして保存できます。結果のファイルは、完全なドキュメントの場合は「WorkingWithImageSaveOptions.MultipageTiff.tiff」、指定されたページ範囲の場合は「WorkingWithImageSaveOptions.GetTiffPageRange.tiff」という名前で、指定されたディレクトリに保存されます。

### Aspose.Words for .NET を使用して Tiff ページ範囲を取得するサンプル ソース コード

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

このチュートリアルでは、Aspose.Words for .NET を使用して TIFF ページの範囲を取得する機能について説明しました。ドキュメントから特定の範囲のページを抽出し、TIFF ファイルとして保存する方法を学びました。

この機能は、ドキュメントから特定のページのみを抽出し、TIFF などの標準画像形式で保存する場合に便利です。また、圧縮と解像度のオプションをカスタマイズして、最高品質の TIFF ファイルを取得することもできます。

Aspose.Words for .NET は、ドキュメントの操作と生成のための高度な機能を幅広く提供します。TIFF ページ範囲の取得は、Aspose.Words for .NET が提供する多くの強力なツールの 1 つです。

この機能を Aspose.Words for .NET プロジェクトに自由に統合して、ドキュメントから特定の範囲のページを抽出し、TIFF 形式で保存できます。
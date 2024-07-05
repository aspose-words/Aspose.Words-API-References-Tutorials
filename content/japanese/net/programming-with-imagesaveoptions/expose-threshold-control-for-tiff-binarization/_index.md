---
title: TIFF バイナリ化のしきい値コントロールを公開する
linktitle: TIFF バイナリ化のしきい値コントロールを公開する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して TIFF の 2 値化しきい値を制御する方法を学びます。より高品質の画像を得るための完全なチュートリアルです。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/expose-threshold-control-for-tiff-binarization/
---
このチュートリアルでは、Aspose.Words for .NET の「TIFF 2 値化しきい値制御露出」機能用に提供されている C# ソース コードについて説明します。この機能を使用すると、ドキュメントを TIFF 形式に変換するときに 2 値化しきい値を制御できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: ドキュメントの読み込み

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

このステップでは、`Document`メソッドを呼び出して、読み込む DOCX ファイルへのパスを渡します。

## ステップ3: イメージバックアップオプションを構成する

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
TiffCompression = TiffCompression.Ccitt3,
ImageColorMode = ImageColorMode.Grayscale,
TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
ThresholdForFloydSteinbergDithering = 254
};
```

このステップでは、画像のバックアップオプションを設定します。新しい`ImageSaveOptions`希望する保存形式を指定するオブジェクト。ここでは、TIFF 形式の場合は「Tiff」です。また、圧縮オプション、画像カラー モード、および指定された 2 値化しきい値による TIFF 2 値化方法も設定します。

## ステップ4: 画像のバックアップ

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
```

この最後のステップでは、ドキュメント画像をTIFF形式で保存します。`Save`メソッドを実行し、指定された保存オプションとともに出力ファイルへのパスを渡します。

これで、ソース コードを実行して、指定されたオプションで 2 値化しきい値を制御しながら、ドキュメントを TIFF 形式に変換できます。結果のファイルは、指定されたディレクトリに「WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff」という名前で保存されます。

### TIFF バイナリ化のしきい値制御を公開するサンプル ソース コード

```csharp 

//ドキュメントディレクトリへのパス
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	TiffCompression = TiffCompression.Ccitt3,
	ImageColorMode = ImageColorMode.Grayscale,
	TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
	ThresholdForFloydSteinbergDithering = 254
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
            
        
```

### 結論

このチュートリアルでは、Aspose.Words for .NET を使用した TIFF 2 値化しきい値コントロールの露出機能について説明しました。ドキュメントを TIFF 形式に変換するときに 2 値化しきい値を制御する方法を学習しました。

この機能は、2 値化しきい値を調整して、より高品質で鮮明な TIFF 画像を取得する場合に便利です。保存オプションで 2 値化しきい値を指定すると、ニーズに合わせたカスタム結果を得ることができます。

Aspose.Words for .NET は、ドキュメントの操作と生成のためのさまざまな高度な機能を提供します。TIFF バイナリ化しきい値コントロールを公開することは、Aspose.Words for .NET が提供する多くの強力なツールの 1 つです。

この機能を Aspose.Words for .NET プロジェクトに自由に組み込むことで、正確な二値化しきい値制御による高品質の TIFF 画像を実現できます。
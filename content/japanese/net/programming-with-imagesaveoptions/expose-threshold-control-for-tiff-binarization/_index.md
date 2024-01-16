---
title: Tiff 2 値化の露出しきい値制御
linktitle: Tiff 2 値化の露出しきい値制御
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して TIFF バイナリ化のしきい値を制御する方法を学びます。より高品質の画像を得るにはチュートリアルを完了してください。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/expose-threshold-control-for-tiff-binarization/
---
このチュートリアルでは、Aspose.Words for .NET を使用した「TIFF バイナリ化しきい値制御露出」機能用に提供されている C# ソース コードを調べます。この機能を使用すると、ドキュメントを TIFF 形式に変換するときに 2 値化のしきい値を制御できます。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用して開発環境がセットアップされていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ 2: ドキュメントをロードする

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

このステップでは、`Document`メソッドを実行し、ロードする DOCX ファイルへのパスを渡します。

## ステップ 3: イメージ バックアップ オプションを構成する

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
TiffCompression = TiffCompression.Ccitt3,
ImageColorMode = ImageColorMode.Grayscale,
TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
ThresholdForFloydSteinbergDithering = 254
};
```

このステップでは、イメージのバックアップ オプションを構成します。新しいものを作成します`ImageSaveOptions`オブジェクトで目的の保存形式を指定します。ここでは TIFF 形式の場合は「Tiff」です。また、圧縮オプション、画像カラー モード、二値化しきい値を指定した TIFF 二値化方法も設定します。

## ステップ 4: イメージをバックアップする

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
```

この最後のステップでは、ドキュメント画像を TIFF 形式で保存します。`Save`メソッドを実行し、指定された保存オプションとともに出力ファイルへのパスを渡します。

これで、指定したオプションで 2 値化のしきい値を制御しながら、ソース コードを実行してドキュメントを TIFF 形式に変換できるようになりました。結果のファイルは、「WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff」という名前で指定されたディレクトリに保存されます。

### サンプル ソース コード Tiff バイナリ化のしきい値制御を公開する

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

このチュートリアルでは、Aspose.Words for .NET を使用した TIFF 二値化しきい値コントロールの露出機能について調べました。ドキュメントを TIFF 形式に変換するときに 2 値化のしきい値を制御する方法を学習しました。

この機能は、二値化のしきい値を調整して、より良い品質と鮮明な TIFF 画像を取得する場合に便利です。保存オプションで二値化のしきい値を指定することで、ニーズに合わせたカスタム結果を得ることができます。

Aspose.Words for .NET は、ドキュメントの操作と生成のためのさまざまな高度な機能を提供します。 TIFF 二値化しきい値コントロールの公開は、自由に使える数多くの強力なツールの 1 つです。

この機能を自由に Aspose.Words for .NET プロジェクトに組み込んで、正確な 2 値化しきい値制御による高品質の TIFF 画像を実現します。
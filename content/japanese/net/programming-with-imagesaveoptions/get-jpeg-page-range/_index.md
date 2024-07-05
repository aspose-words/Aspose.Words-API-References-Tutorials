---
title: Jpeg ページ範囲を取得
linktitle: Jpeg ページ範囲を取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してさまざまな JPEG ページを取得する方法を学びます。カスタム イメージを抽出するための完全なチュートリアルです。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

このチュートリアルでは、Aspose.Words for .NET の「JPEG ページの範囲を取得」機能用に提供されている C# ソース コードについて説明します。この機能を使用すると、ドキュメントの特定の範囲のページを JPEG 形式の画像に変換できます。

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

このステップでは、画像のバックアップオプションを設定します。新しい`ImageSaveOptions`希望する保存形式を指定するオブジェクト。ここではJPEG形式の場合は「Jpeg」。また、変換するページの範囲も設定します。`PageSet`最後に、画像の明るさとコントラストを調整します。`ImageBrightness`そして`ImageContrast`それぞれのプロパティで水平解像度を変更します。`HorizontalResolution`財産。

## ステップ4: 画像のバックアップ

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

この最後のステップでは、指定されたページ範囲の画像をJPEG形式で保存します。`Save`メソッドを実行し、指定された保存オプションとともに出力ファイルへのパスを渡します。

これで、ソース コードを実行して、ドキュメント内の特定の範囲のページを JPEG 画像に変換できます。結果のファイルは、指定されたディレクトリに「WorkingWithImageSaveOptions.GetJpegPageRange.jpeg」という名前で保存されます。

### Aspose.Words For .NET を使用して Jpeg ページ範囲を取得するためのサンプル ソース コード

```csharp 
 //ドキュメントディレクトリへのパス
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

//ドキュメントの最初のページのみを変換するには、「PageSet」を「0」に設定します。
options.PageSet = new PageSet(0);

//画像の明るさとコントラストを変更します。
//どちらも 0 ～ 1 のスケールで、デフォルトでは 0.5 になっています。
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

//水平解像度を変更します。
//これらのプロパティのデフォルト値は 96.0 (解像度 96dpi) です。
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して JPEG ページ範囲を取得する機能について説明しました。保存オプションをカスタマイズしながら、ドキュメントの特定のページ範囲を JPEG 形式の画像に変換する方法を学習しました。

この機能は、ドキュメントから特定のページを抽出し、JPEG 画像として保存する場合に便利です。また、画像の明るさ、コントラスト、水平解像度を調整して、パーソナライズされた結果を得ることもできます。

Aspose.Words for .NET は、ドキュメントの操作と生成のための高度な機能を幅広く提供します。JPEG ページ範囲の取得は、Aspose.Words for .NET が提供する数多くの強力なツールの 1 つです。

この機能を Aspose.Words for .NET プロジェクトに自由に統合して、ドキュメントから高品質の JPEG 画像を取得できます。
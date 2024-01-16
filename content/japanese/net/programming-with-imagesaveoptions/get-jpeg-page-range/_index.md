---
title: JPEGページ範囲の取得
linktitle: JPEGページ範囲の取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してさまざまな JPEG ページを取得する方法を学びます。カスタム イメージを抽出するための完全なチュートリアル。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

このチュートリアルでは、Aspose.Words for .NET を使用して「JPEG ページの範囲を取得」機能用に提供されている C# ソース コードを調べます。この機能を使用すると、ドキュメントの特定の範囲のページを JPEG 形式の画像に変換できます。

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

このステップでは、イメージのバックアップ オプションを構成します。新しいものを作成します`ImageSaveOptions`オブジェクトで目的の保存形式を指定します。ここでは JPEG 形式を「Jpeg」とします。また、変換するページの範囲も、`PageSet`物体。最後に、画像の明るさとコントラストを調整します。`ImageBrightness`そして`ImageContrast`それぞれのプロパティ。また、次を使用して水平解像度を変更します。`HorizontalResolution`財産。

## ステップ 4: イメージをバックアップする

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

この最後のステップでは、指定したページ範囲の画像を JPEG 形式で保存します。`Save`メソッドを実行し、指定された保存オプションとともに出力ファイルへのパスを渡します。

これで、ソース コードを実行して、ドキュメント内の特定の範囲のページを JPEG 画像に変換できるようになりました。結果のファイルは、指定したディレクトリに「WorkingWithImageSaveOptions.GetJpegPageRange.jpeg」という名前で保存されます。

### Aspose.Words For .NET を使用した Jpeg ページ範囲の取得のサンプル ソース コード

```csharp 
 //ドキュメントディレクトリへのパス
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

//ドキュメントの最初のページのみを変換するには、「PageSet」を「0」に設定します。
options.PageSet = new PageSet(0);

//画像の明るさとコントラストを変更します。
//どちらも 0 ～ 1 のスケールで、デフォルトでは 0.5 です。
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

//水平解像度を変更します。
//これらのプロパティのデフォルト値は 96.0 (解像度 96dpi) です。
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して JPEG ページ範囲を取得する機能を検討しました。保存オプションをカスタマイズしながら、ドキュメントの特定の範囲のページを JPEG 形式の画像に変換する方法を学習しました。

この機能は、文書から特定のページを抽出して JPEG 画像として保存する場合に便利です。画像の明るさ、コントラスト、水平解像度を調整して、カスタマイズした結果を実現することもできます。

Aspose.Words for .NET は、ドキュメントの操作と生成のための広範な高度な機能を提供します。 JPEG ページ範囲の取得は、自由に使える数多くの強力なツールの 1 つです。

この機能を自由に Aspose.Words for .NET プロジェクトに統合して、ドキュメントから高品質の JPEG 画像を取得してください。
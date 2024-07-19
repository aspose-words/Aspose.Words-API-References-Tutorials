---
title: フォーマット 1Bpp インデックス
linktitle: フォーマット 1Bpp インデックス
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してインデックスされた 1 bpp で画像をフォーマットする方法を学びます。色深度の低い画像に関する完全なチュートリアルです。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
このチュートリアルでは、Aspose.Words for .NET の「Format 1Bpp Indexed」機能用に提供されている C# ソース コードについて説明します。この機能を使用すると、ドキュメント内の画像を、色深度 1 ビット/ピクセル (1 bpp) とインデックス カラー モードの PNG 形式でフォーマットできます。

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

このステップでは、画像のバックアップオプションを設定します。新しい`ImageSaveOptions`希望する保存形式を指定するオブジェクト。ここでは、PNG 形式の場合は「Png」です。また、画像に含めるページ、白黒カラー モード、インデックス付き 1 bpp ピクセル形式も定義します。

## ステップ4: 画像のバックアップ

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

この最後のステップでは、ドキュメント画像をPNG形式で保存します。`Save`メソッドを実行し、指定された保存オプションとともに出力ファイルへのパスを渡します。

これで、ソース コードを実行して、ドキュメント イメージを 1 bpp の色深度でインデックスされた PNG 形式でフォーマットできます。結果のファイルは、指定されたディレクトリに「WorkingWithImageSaveOptions.Format1BppIndexed.Png」という名前で保存されます。

### Aspose.Words for .NET を使用した Format 1Bpp Indexed のサンプル ソース コード

```csharp 
 
			 //ドキュメントディレクトリへのパス
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### 結論

このチュートリアルでは、Aspose.Words for .NET の 1Bpp インデックス形式機能について説明しました。ドキュメント内の画像を、色深度 1 ビット/ピクセル (1 bpp) とインデックス カラー モードを使用して PNG 形式でフォーマットする方法を学習しました。

この機能は、色深度が低くファイル サイズが小さい画像を取得する場合に便利です。1Bpp インデックス形式では、インデックス カラー パレットを使用して画像を表現できるため、特定のアプリケーションでは便利です。

Aspose.Words for .NET は、ドキュメントの操作と生成のための幅広い高度な機能を提供します。1Bpp インデックス形式は、Aspose.Words for .NET が提供する数多くの強力なツールの 1 つです。
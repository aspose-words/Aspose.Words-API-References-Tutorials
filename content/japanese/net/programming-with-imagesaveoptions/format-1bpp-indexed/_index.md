---
title: フォーマット 1Bpp インデックス付き
linktitle: フォーマット 1Bpp インデックス付き
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してインデックス付きの画像を 1 bpp でフォーマットする方法を学びます。色深度の低い画像に関する完全なチュートリアル。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
このチュートリアルでは、Aspose.Words for .NET を使用した「Format 1Bpp Indexed」機能用に提供されている C# ソース コードを調べます。この機能を使用すると、ドキュメント内の画像を、ピクセルあたり 1 ビット (1 bpp) の色深度およびインデックス付きカラー モードで PNG 形式にフォーマットできます。

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

このステップでは、イメージのバックアップ オプションを構成します。新しいものを作成します`ImageSaveOptions`オブジェクトで目的の保存形式を指定します。ここでは、PNG 形式の場合は「Png」です。また、画像に含めるページ、白黒カラー モード、インデックス付き 1 bpp ピクセル形式も定義します。

## ステップ 4: イメージをバックアップする

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

この最後のステップでは、ドキュメントの画像を PNG 形式で保存します。`Save`メソッドを実行し、指定された保存オプションとともに出力ファイルへのパスを渡します。

これで、ソース コードを実行して、インデックス付きの色深度 1 bpp の PNG 形式でドキュメントの画像をフォーマットできるようになりました。結果のファイルは、「WorkingWithImageSaveOptions.Format1BppIndexed.Png」という名前で指定されたディレクトリに保存されます。

### Aspose.Words for .NET を使用してインデックス付けされた形式 1Bpp のサンプル ソース コード

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

このチュートリアルでは、Aspose.Words for .NET を使用した 1Bpp インデックス形式機能を検討しました。ドキュメント内の画像を、ピクセルあたり 1 ビット (1 bpp) の色深度とインデックス付きカラー モードを使用して PNG 形式でフォーマットする方法を学習しました。

この機能は、色深度が低く、ファイル サイズが小さい画像を取得する場合に便利です。 1Bpp インデックス付きフォーマットでは、インデックス付きカラー パレットを使用して画像を表現できます。これは、一部の特定のアプリケーションにとって有益です。

Aspose.Words for .NET は、ドキュメントの操作と生成のための幅広い高度な機能を提供します。 1Bpp インデックス形式は、自由に使える数多くの強力なツールの 1 つです。
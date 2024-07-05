---
title: ページ保存コールバック
linktitle: ページ保存コールバック
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント ページを画像として保存する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/page-saving-callback/
---

このチュートリアルでは、.NET 用の Aspose.Words 画像保存オプションでページ保存コールバックを使用するために提供されている C# ソース コードについて説明します。この機能を使用すると、ドキュメントの各ページを画像として保存するときにカスタム アクションを実行できます。

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

このステップでは、新しい画像保存オプションを作成して設定します。`ImageSaveOptions`オブジェクト。希望するバックアップ形式を指定します。ここではPNG形式の場合は「Png」です。`PageSet`保存するページの範囲を指定します。ここでは、文書の最初のページから最後のページまでです（`doc.PageCount - 1`）。また、`PageSavingCallback`のインスタンスに`HandlePageSavingCallback`これは、ページ保存コールバックを処理するカスタム クラスです。

## ステップ4: ページ保存コールバックの実装

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         //ここでカスタムアクションを実装します
         //「args.PageIndex」プロパティを通じてページ情報にアクセスできます。
         //各ページの保存オプションを個別に変更することもできます
     }
}
```

このステップでは、`HandlePageSavingCallback`を実装するクラス`IPageSavingCallback`インターフェース。このクラスをカスタマイズするには、`PageSaving`方法。ページ情報にアクセスするには、`args.PageIndex`の財産`PageSavingArgs`引数として渡されるオブジェクト。

## ステップ5: ページを画像として保存する

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

この最後のステップでは、文書の各ページを画像として保存します。`Save`メソッドを使用し、出力ファイルへのパスを`.png`拡張子と保存オプションを指定します。

これで、ソース コードを実行して、ドキュメントの各ページを画像として保存するときにカスタム アクションを実行できるようになりました。結果のファイルは、指定されたディレクトリに「WorkingWithImageSaveOptions.PageSavingCallback.png」という名前で保存されます。

### Aspose.Words for .NET を使用したページ保存コールバックのサンプル ソース コード


```csharp 
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## 結論

このチュートリアルでは、.NET 用の Aspose.Words 画像保存オプションを使用したページ保存コールバック機能について説明しました。ドキュメントの各ページを画像として保存するときにカスタム アクションを実行する方法を学習しました。

この機能は、画像に変換するときに各ページで特定の操作を実行したい場合に便利です。ページ情報にアクセスし、それを使用してバックアップ オプションをカスタマイズしたり、その他のページ固有の処理を実行したりできます。

Aspose.Words for .NET は、ドキュメントの操作と生成のための高度な機能を幅広く提供します。ページ保存リマインダーは、ページを画像に保存するプロセスをカスタマイズできる強力なツールの 1 つです。
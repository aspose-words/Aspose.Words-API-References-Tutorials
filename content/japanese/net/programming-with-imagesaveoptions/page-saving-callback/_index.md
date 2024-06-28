---
title: ページ保存コールバック
linktitle: ページ保存コールバック
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント ページの画像への保存をカスタマイズする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-imagesaveoptions/page-saving-callback/
---

このチュートリアルでは、.NET の Aspose.Words 画像保存オプションでページ保存コールバックを使用するために提供されている C# ソース コードを調べます。この機能を使用すると、ドキュメントの各ページを画像として保存するときにカスタム アクションを実行できます。

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

このステップでは、新しいファイルを作成して画像保存オプションを構成します。`ImageSaveOptions`物体。希望のバックアップ形式を指定します。ここでは、PNG 形式の場合は「Png」を指定します。を使用しております`PageSet`保存するページ範囲を指定します。ここではドキュメントの最初のページから最後のページまでです (`doc.PageCount - 1`）。私たちも設定しました`PageSavingCallback`のインスタンスに`HandlePageSavingCallback`これは、ページ保存コールバックを処理するカスタム クラスです。

## ステップ 4: ページ保存コールバックの実装

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         //ここにカスタムアクションを実装します
         //「args.PageIndex」プロパティを通じてページ情報にアクセスできます。
         //各ページの保存オプションを個別に変更することもできます。
     }
}
```

このステップでは、`HandlePageSavingCallback`を実装するクラス`IPageSavingCallback`インターフェース。このクラスは、特定のアクションを追加することでカスタマイズできます。`PageSaving`方法。ページ情報には、`args.PageIndex`の財産`PageSavingArgs`引数として渡されるオブジェクト。

## ステップ 5: ページを画像として保存する

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

この最後のステップでは、ドキュメントの各ページを画像として保存します。`Save`メソッドを使用し、出力ファイルへのパスを渡します。`.png`拡張子と、指定された保存オプションを追加します。

これで、ソース コードを実行して、ドキュメントの各ページを画像として保存するときにカスタム アクションを実行できるようになりました。結果のファイルは、「WorkingWithImageSaveOptions.PageSavingCallback.png」という名前で指定されたディレクトリに保存されます。

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

このチュートリアルでは、.NET の Aspose.Words 画像保存オプションを使用したページ保存コールバック機能を検討しました。ドキュメントの各ページを画像として保存するときにカスタム アクションを実行する方法を学習しました。

この機能は、画像に変換するときにページごとに特定の操作を実行したい場合に便利です。ページ情報にアクセスし、それを使用してバックアップ オプションをカスタマイズしたり、その他のページ固有の処理を実行したりできます。

Aspose.Words for .NET は、ドキュメントの操作と生成のための広範な高度な機能を提供します。ページ保存リマインダーは、ページを画像に保存するプロセスをカスタマイズできる強力なツールの 1 つです。
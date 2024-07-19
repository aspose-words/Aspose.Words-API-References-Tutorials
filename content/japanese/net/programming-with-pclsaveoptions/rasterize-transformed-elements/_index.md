---
title: 変換された要素をラスタライズする
linktitle: 変換された要素をラスタライズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PCL 形式に変換するときに、変換された要素のラスタライズを無効にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET は、C# アプリケーションで Word ドキュメントを作成、操作、変換するための強力なライブラリです。Aspose.Words が提供する機能の 1 つに、ドキュメントを別の形式に変換するときに変換された要素をラスタライズする機能があります。このガイドでは、Aspose.Words for .NET の C# ソース コードを使用して、ドキュメントを PCL 形式に変換するときに変換された要素のラスタライズを無効にする方法を説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、Word ドキュメントでの Words 処理を簡単かつ効率的にする人気のライブラリです。変換中に変換された要素をラスタライズするサポートなど、Word ドキュメントの作成、編集、変換のための幅広い機能を提供します。

## Word文書の読み込み

最初のステップは、PCL 形式に変換する Word 文書を読み込むことです。Document クラスを使用して、ソース ファイルから文書を読み込みます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

この例では、ドキュメント ディレクトリにある「Rendering.docx」ドキュメントを読み込んでいます。

## バックアップオプションの設定

次のステップは、PCL 形式に変換するための保存オプションを構成することです。PclSaveOptions クラスを使用して、RasterizeTransformedElements プロパティを false に設定します。手順は次のとおりです。

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

新しい PclSaveOptions オブジェクトを作成し、SaveFormat プロパティを SaveFormat.Pcl に設定して、ドキュメントを PCL 形式で保存することを指定します。次に、RasterizeTransformedElements プロパティを false に設定して、変換された要素のラスタライズを無効にします。

## ドキュメントをPCL形式に変換する

保存オプションの設定が完了したので、ドキュメントを PCL 形式に変換する手順に進みます。Document クラスの Save メソッドを使用して、保存オプションを指定して、変換されたドキュメントを PCL 形式で保存します。次に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl」として保存します。

### Aspose.Words for .NET の「変換された要素をラスタライズ」機能のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書を読み込む


Document doc = new Document(dataDir + "Rendering.docx");

//PCL形式への変換のためのバックアップオプションを構成する
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

//ドキュメントをPCL形式に変換する
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## 結論

このガイドでは、提供されている C# ソース コードを使用してドキュメントを PCL 形式に変換するときに、Aspose.Words for .NET を使用して変換された要素のラスタライズを無効にする方法について説明しました。提供されている手順に従うことで、Word ドキュメントを別の形式に変換するときに、変換された要素のラスタライズ動作を簡単に制御できます。Aspose.Words は、変換された要素を操作するための優れた柔軟性とパワーを備えているため、特定のニーズにぴったり合った変換されたドキュメントを作成できます。
---
title: 変換された要素をラスタライズする
linktitle: 変換された要素をラスタライズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PCL 形式に変換するときに、変換された要素のラスタライズを無効にする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET は、C# アプリケーションで Word ドキュメントを作成、操作、変換するための強力なライブラリです。 Aspose.Words が提供する機能には、ドキュメントを別の形式に変換するときに、変換された要素をラスタライズする機能があります。このガイドでは、Aspose.Words for .NET の C# ソース コードを使用して、ドキュメントを PCL 形式に変換するときに、変換された要素のラスタライズを無効にする方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、Word 文書のワープロ処理を簡単かつ効率的に行う人気のライブラリです。 Word 文書の作成、編集、変換のための幅広い機能を提供します。これには、変換中の変換された要素のラスタライズのサポートも含まれます。

## Word文書のロード

最初のステップは、PCL 形式に変換する Word 文書をロードすることです。 Document クラスを使用して、ソース ファイルからドキュメントを読み込みます。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

この例では、ドキュメント ディレクトリにある「Rendering.docx」ドキュメントをロードしています。

## バックアップ オプションの構成

次のステップは、PCL 形式に変換するための保存オプションを構成することです。 PclSaveOptions クラスを使用し、RasterizeTransformedElements プロパティを false に設定します。その方法は次のとおりです。

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

新しい PclSaveOptions オブジェクトを作成し、SaveFormat プロパティを SaveFormat.Pcl に設定して、ドキュメントを PCL 形式で保存することを指定します。次に、RasterizeTransformedElements プロパティを false に設定して、変換された要素のラスター化を無効にします。

## ドキュメントを PCL 形式に変換する

保存オプションを設定したので、ドキュメントを PCL 形式に変換することに進むことができます。 Document クラスの Save メソッドを使用して、保存オプションを指定して、変換されたドキュメントを PCL 形式で保存します。以下に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl」として保存します。

### Aspose.Words for .NET を使用した「変換された要素のラスタライズ」機能のソース コード例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書をロードする


Document doc = new Document(dataDir + "Rendering.docx");

//PCL 形式に変換するためのバックアップ オプションを構成する
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

//ドキュメントを PCL 形式に変換します
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## 結論

このガイドでは、提供されている C# ソース コードを使用してドキュメントを PCL 形式に変換するときに、Aspose.Words for .NET を使用して、変換された要素のラスタライズを無効にする方法について説明しました。示されている手順に従うことで、Word 文書を別の形式に変換するときに、変換された要素のラスタライズ動作を簡単に制御できます。 Aspose.Words は、変換された要素を操作するための優れた柔軟性と機能を提供し、特定のニーズに合わせて変換されたドキュメントを正確に作成できます。
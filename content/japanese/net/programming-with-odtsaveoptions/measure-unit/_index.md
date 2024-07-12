---
title: 測定単位
linktitle: 測定単位
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を ODT に変換するときに測定単位を指定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-odtsaveoptions/measure-unit/
---

C# アプリケーションで Word 文書を OpenDocument Text (ODT) 形式に変換する場合、測定可能な書式設定とコンテンツ プロパティに使用する測定単位を指定する必要がある場合があります。Aspose.Words ライブラリ for .NET では、OdtSaveOptions 保存オプションを使用してこの機能を簡単に指定できます。このステップ バイ ステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、OdtSaveOptions で測定単位を指定し、Word 文書を ODT に変換する方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## Word文書の読み込み

最初のステップは、ODT に変換する Word 文書を読み込むことです。Document クラスを使用して、ソース ファイルから文書を読み込みます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「Document.docx」を読み込みます。

## バックアップオプションの設定

次のステップは、ODT に変換するためのバックアップ オプションを構成することです。OdtSaveOptions クラスを使用して、MeasureUnit プロパティを目的の値に設定します。たとえば、測定単位としてインチを使用する場合は、MeasureUnit を OdtSaveMeasureUnit.Inches に設定します。手順は次のとおりです。

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

新しい OdtSaveOptions オブジェクトを作成し、MeasureUnit プロパティを目的の値に設定します。この例では、測定単位としてインチを使用するために OdtSaveMeasureUnit.Inches を設定します。

## ドキュメントをODTに変換する

保存オプションの設定が完了したので、ドキュメントを ODT に変換する手順に進みます。Document クラスの Save メソッドを使用して、保存オプションを指定して、変換されたドキュメントを ODT 形式で保存します。次に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithOdtSaveOptions.MeasureUnit.odt」として保存します。

### Aspose.Words for .NET を使用した「測定単位」機能を備えた OdtSaveOptions のサンプル ソース コード



```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書を読み込む
Document doc = new Document(dataDir + "Document.docx");

//「測定単位」機能を使用したバックアップ オプションの構成
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

//ドキュメントをODTに変換する
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリで OdtSaveOptions 保存オプションを使用して測定単位を指定し、Word 文書を ODT に変換する方法について説明しました。提供されている手順に従い、提供されている C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。ODT に変換するときに測定単位を指定すると、結果の文書の書式設定と寸法を特定のニーズに合わせて制御できます。
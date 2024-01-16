---
title: 測定単位
linktitle: 測定単位
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を ODT に変換するときに測定単位を指定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-odtsaveoptions/measure-unit/
---

C# アプリケーションで Word 文書を OpenDocument Text (ODT) 形式に変換する場合、測定可能な書式設定とコンテンツ プロパティに使用される測定単位を指定することが必要になる場合があります。 .NET 用の Aspose.Words ライブラリでは、OdtSaveOptions 保存オプションを使用してこの機能を簡単に指定できます。このステップバイステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、OdtSaveOptions を使用して測定単位を指定して Word ドキュメントを ODT に変換する方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## Word文書のロード

最初のステップは、ODT に変換する Word 文書をロードすることです。 Document クラスを使用して、ソース ファイルからドキュメントを読み込みます。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「Document.docx」をロードします。

## バックアップ オプションの構成

次のステップは、ODT に変換するためのバックアップ オプションを構成することです。 OdtSaveOptions クラスを使用して、MeasureUnit プロパティを目的の値に設定します。たとえば、測定単位としてインチを使用する場合は、MeasureUnit を OdtSaveMeasureUnit.Inches に設定します。その方法は次のとおりです。

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

新しい OdtSaveOptions オブジェクトを作成し、MeasureUnit プロパティを目的の値に設定します。この例では、測定単位としてインチを使用するための OdtSaveMeasureUnit.Inches を設定します。

## ドキュメントをODTに変換する

保存オプションを設定したので、ドキュメントの ODT への変換に進むことができます。 Document クラスの Save メソッドを使用し、保存オプションを指定して、変換されたドキュメントを ODT 形式で保存します。以下に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithOdtSaveOptions.MeasureUnit.odt」として保存します。

### Aspose.Words for .NET を使用した「測定単位」機能を備えた OdtSaveOptions のソース コードの例



```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書をロードする
Document doc = new Document(dataDir + "Document.docx");

//「測定単位」機能を使用したバックアップ オプションの構成
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

//ドキュメントを ODT に変換する
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## 結論

このガイドでは、.NET 用 Aspose.Words ライブラリの OdtSaveOptions 保存オプションを使用して測定単位を指定し、Word ドキュメントを ODT に変換する方法を説明しました。提供された手順に従い、提供された C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。 ODT に変換するときに測定単位を指定すると、特定のニーズに応じて結果のドキュメントの書式設定とサイズを制御できます。
---
title: すべての CSS ルールを 1 つのファイルに記述する
linktitle: すべての CSS ルールを 1 つのファイルに記述する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、すべての CSS ルールを 1 つのファイルに記述して、Word ドキュメントを固定 HTML に変換する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

C# アプリケーションで Word ドキュメントを固定 HTML に変換する場合、整理と移植性を向上させるために、すべての CSS ルールを 1 つのファイルに統合することができます。 .NET 用の Aspose.Words ライブラリでは、HtmlFixedSaveOptions 保存オプションを使用してこの機能を簡単に指定できます。このステップバイステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、保存オプション HtmlFixedSaveOptions を使用してすべての CSS ルールを 1 つのファイルに記述し、Word ドキュメントを固定 HTML に変換する方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## Word文書のロード

最初のステップは、固定 HTML に変換する Word 文書をロードすることです。 Document クラスを使用して、ソース ファイルからドキュメントを読み込みます。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「Document.docx」をロードします。

## バックアップ オプションの構成

次のステップは、固定 HTML に変換するための保存オプションを構成することです。 HtmlFixedSaveOptions クラスを使用し、SaveFontFaceCssSeparately プロパティを false に設定して、すべての CSS ルールを 1 つのファイルに書き込みます。その方法は次のとおりです。

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

新しい HtmlFixedSaveOptions オブジェクトを作成し、SaveFontFaceCssSeparately プロパティを false に設定して、すべての CSS ルールを 1 つのファイルに書き込みます。

## HTMLドキュメント変換を修正

保存オプションを設定したので、ドキュメントを固定 HTML に変換する作業に進むことができます。 Document クラスの Save メソッドを使用して、保存オプションを指定して、変換されたドキュメントを固定 HTML 形式で保存します。以下に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html」として保存します。

### Aspose.Words for .NET を使用した「すべての CSS ルールを 1 つのファイルに書き込む」機能を備えた HtmlFixedSaveOptions のソース コードの例

```csharp
//ドキュメント ディレクトリへのアクセス パス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書をロードする
Document doc = new Document(dataDir + "Document.docx");

//「すべての CSS ルールを 1 つのファイルに書き込む」機能を使用してバックアップ オプションを構成する
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

//ドキュメントを固定HTMLに変換する
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリで HtmlFixedSaveOptions を使用して、すべての CSS ルールを 1 つのファイルに記述することにより、Word ドキュメントを固定 HTML に変換する方法について説明しました。提供された手順に従い、提供された C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。すべての CSS ルールを 1 つのファイルに記述すると、ドキュメントの変換中に生成される HTML コードの整理と管理が容易になります。
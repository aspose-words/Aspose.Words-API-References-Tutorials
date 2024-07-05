---
title: すべての CSS ルールを 1 つのファイルに記述する
linktitle: すべての CSS ルールを 1 つのファイルに記述する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、すべての CSS ルールを 1 つのファイルに記述し、Word 文書を固定 HTML に変換する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

C# アプリケーションで Word 文書を固定 HTML に変換する場合、整理と移植性を高めるために、すべての CSS ルールを 1 つのファイルに統合したい場合があります。Aspose.Words ライブラリ for .NET では、HtmlFixedSaveOptions 保存オプションを使用してこの機能を簡単に指定できます。このステップ バイ ステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、保存オプション HtmlFixedSaveOptions を使用してすべての CSS ルールを 1 つのファイルに記述し、Word 文書を固定 HTML に変換する方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## Word文書の読み込み

最初のステップは、固定 HTML に変換する Word 文書を読み込むことです。Document クラスを使用して、ソース ファイルから文書を読み込みます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「Document.docx」を読み込みます。

## バックアップオプションの設定

次のステップは、固定 HTML に変換するための保存オプションを構成することです。HtmlFixedSaveOptions クラスを使用し、SaveFontFaceCssSeparately プロパティを false に設定して、すべての CSS ルールを 1 つのファイルに書き込みます。方法は次のとおりです。

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

新しい HtmlFixedSaveOptions オブジェクトを作成し、SaveFontFaceCssSeparately プロパティを false に設定して、すべての CSS ルールを 1 つのファイルに書き込みます。

## HTMLドキュメント変換を修正

保存オプションを設定したので、ドキュメントを固定 HTML に変換する手順に進むことができます。Document クラスの Save メソッドを使用して、保存オプションを指定して、変換されたドキュメントを固定 HTML 形式で保存します。次に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html」として保存します。

### Aspose.Words for .NET を使用した「すべての CSS ルールを 1 つのファイルに書き込む」機能を備えた HtmlFixedSaveOptions のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのアクセスパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書を読み込む
Document doc = new Document(dataDir + "Document.docx");

//「すべての CSS ルールを 1 つのファイルに書き込む」機能を使用してバックアップ オプションを構成する
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

//ドキュメントを固定HTMLに変換する
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## 結論

このガイドでは、Aspose.Words ライブラリの .NET で HtmlFixedSaveOptions を使用してすべての CSS ルールを 1 つのファイルに記述し、Word 文書を固定 HTML に変換する方法について説明しました。提供されている手順に従い、提供されている C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。すべての CSS ルールを 1 つのファイルに記述すると、文書の変換中に生成される HTML コードの整理と管理が容易になります。
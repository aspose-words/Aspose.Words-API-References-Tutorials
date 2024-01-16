---
title: ターゲットマシンのフォントを使用する
linktitle: ターゲットマシンのフォントを使用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ターゲット マシンのフォントを使用して Word ドキュメントを固定 HTML に変換する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

C# アプリケーションで Word ドキュメントを固定 HTML に変換する場合、レンダリングされた HTML がドキュメントの元の外観とスタイルを確実に保持するために、ターゲット マシンのフォントを使用することができます。 .NET 用の Aspose.Words ライブラリでは、HtmlFixedSaveOptions 保存オプションを使用してこの機能を簡単に指定できます。このステップバイステップ ガイドでは、Aspose.Words for .NET の C# ソース コードを使用し、HtmlFixedSaveOptions を使用してターゲット マシンのフォントを使用して Word ドキュメントを固定 HTML に変換する方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## Word文書のロード

最初のステップは、固定 HTML に変換する Word 文書をロードすることです。 Document クラスを使用して、ソース ファイルからドキュメントを読み込みます。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「代替フォントを使用した箇条書き.docx」をロードします。

## バックアップ オプションの構成

次のステップは、固定 HTML に変換するための保存オプションを構成することです。 HtmlFixedSaveOptions クラスを使用し、UseTargetMachineFonts プロパティを true に設定して、ターゲット コンピューターのフォントを使用するように Aspose.Words に指示します。その方法は次のとおりです。

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

新しい HtmlFixedSaveOptions オブジェクトを作成し、UseTargetMachineFonts プロパティを true に設定して、変換時にターゲット マシンのフォントを使用します。

## HTMLドキュメント変換を修正

保存オプションを設定したので、ドキュメントを固定 HTML に変換する作業に進むことができます。 Document クラスの Save メソッドを使用して、保存オプションを指定して、変換されたドキュメントを固定 HTML 形式で保存します。以下に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html」として保存します。

### Aspose.Words for .NET を使用した「ターゲット マシンのフォントを使用する」機能を備えた HtmlFixedSaveOptions のソース コードの例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書をロードする
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//「ターゲット マシンのフォントを使用」機能を使用してバックアップ オプションを構成する
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

//ドキュメントを固定HTMLに変換する
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、ターゲット マシンのフォントを使用して Word ドキュメントを固定 HTML に変換する方法を説明しました。提供された手順に従い、提供された C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。ターゲット マシンのフォントを使用した固定 HTML への変換により、HTML 形式でのドキュメントの忠実かつ一貫したレンダリングが保証されます。

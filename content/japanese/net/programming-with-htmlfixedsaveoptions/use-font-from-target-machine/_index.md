---
title: ターゲットマシンのフォントを使用する
linktitle: ターゲットマシンのフォントを使用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ターゲット マシンのフォントを使用して Word 文書を固定 HTML に変換する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

C# アプリケーションで Word 文書を固定 HTML に変換する場合、レンダリングされた HTML が文書の元の外観とスタイルを保持するように、ターゲット マシンのフォントを使用することをお勧めします。Aspose.Words ライブラリ for .NET では、HtmlFixedSaveOptions 保存オプションを使用してこの機能を簡単に指定できます。このステップ バイ ステップ ガイドでは、Aspose.Words for .NET の C# ソース コードを使用して、HtmlFixedSaveOptions を使用してターゲット マシンのフォントを使用して Word 文書を固定 HTML に変換する方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## Word文書の読み込み

最初のステップは、固定 HTML に変換する Word 文書を読み込むことです。Document クラスを使用して、ソース ファイルから文書を読み込みます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「Bullet points with alternative font.docx」を読み込みます。

## バックアップオプションの設定

次の手順では、固定 HTML に変換するための保存オプションを構成します。HtmlFixedSaveOptions クラスを使用して、UseTargetMachineFonts プロパティを true に設定し、Aspose.Words にターゲット マシンのフォントを使用するように指示します。手順は次のとおりです。

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

新しい HtmlFixedSaveOptions オブジェクトを作成し、UseTargetMachineFonts プロパティを true に設定して、変換時にターゲット マシンのフォントを使用します。

## HTMLドキュメント変換を修正

保存オプションを設定したので、ドキュメントを固定 HTML に変換する手順に進むことができます。Document クラスの Save メソッドを使用して、保存オプションを指定して、変換されたドキュメントを固定 HTML 形式で保存します。次に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

この例では、指定された保存オプションを使用して、変換されたドキュメントを「WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html」として保存します。

### Aspose.Words for .NET を使用した「ターゲット マシンのフォントを使用する」機能を備えた HtmlFixedSaveOptions のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書を読み込む
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//「ターゲットマシンのフォントを使用する」機能を使用してバックアップオプションを構成する
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

//ドキュメントを固定HTMLに変換する
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、ターゲット マシンのフォントを使用して Word 文書を固定 HTML に変換する方法について説明しました。提供されている手順に従い、提供されている C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。ターゲット マシンのフォントを使用して固定 HTML に変換すると、HTML 形式での文書の忠実で一貫したレンダリングが保証されます。

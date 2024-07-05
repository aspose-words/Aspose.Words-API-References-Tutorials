---
title: Ms Word バージョンの設定
linktitle: Ms Word バージョンの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、指定されたバージョンの MS Word でドキュメントを読み込む方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-loadoptions/set-ms-word-version/
---
C# アプリケーションで Word ドキュメントを処理する場合、ドキュメントを読み込むときに使用する Microsoft Word のバージョンを指定する必要がある場合があります。Aspose.Words ライブラリ for .NET を使用すると、LoadOptions を使用して、使用する MS Word のバージョンを簡単に設定できます。このステップ バイ ステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、LoadOptions 読み込みオプションを使用して、指定したバージョンの MS Word でドキュメントを読み込む方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## 読み込みオプションの設定

最初のステップは、ドキュメントの読み込みオプションを構成することです。読み込みパラメータを指定するには、LoadOptions クラスを使用します。この場合、MswVersion プロパティを MS Word の希望するバージョンに設定する必要があります。たとえば、Microsoft Word 2010 バージョンを使用します。その方法は次のとおりです。

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

新しい LoadOptions オブジェクトを作成し、MswVersion プロパティを MsWordVersion.Word2010 に設定して、MS Word 2010 のバージョンを指定します。

## 指定されたバージョンの MS Word でドキュメントを読み込み中

読み込みオプションを設定したので、Document クラスを使用してドキュメントを読み込み、読み込みオプションを指定できます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

この例では、指定された読み込みオプションを使用して、ドキュメント ディレクトリにあるドキュメント「Document.docx」を読み込みます。

### Aspose.Words for .NET を使用した「MS Word バージョンの設定」機能を備えた LoadOptions のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//「MS Word バージョンの設定」機能を使用して読み込みオプションを設定します
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

//指定されたバージョンのMS Wordで文書を読み込み
Document doc = new Document(dataDir + "Document.docx", loadOptions);

//文書を保存する
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、特定のバージョンの MS Word を指定してドキュメントをアップロードする方法について説明しました。提供されている手順に従い、提供されているコード C# ソースを使用すると、この機能を C# アプリケーションに簡単に適用できます。指定されたバージョンの MS Word でドキュメントをロードすると、アプリケーションでドキュメントの適切な互換性と処理が保証されます。


### よくある質問

#### Q: C# アプリケーションでドキュメントを読み込むときに、MS Word のバージョンを指定する必要があるのはなぜですか?

MS Word のバージョンを指定すると、特にバージョン間で異なる可能性のある特定の書式や機能を扱う場合に、ドキュメントが正しく読み込まれ、処理されることが保証されます。

#### Q: Aspose.Words はどのバージョンの MS Word をサポートしていますか?

A: Aspose.Words for .NET は、Word 97、Word 2003、Word 2007、Word 2010、Word 2013、Word 2016、Word 2019 など、さまざまなバージョンの MS Word をサポートしています。

#### Q: システムにインストールされているものとは異なるバージョンの MS Word でドキュメントを読み込むことはできますか?

A: はい、Aspose.Words では、ドキュメントを読み込むときに別のバージョンの MS Word を指定できるため、ターゲット システムに別のバージョンの MS Word があっても互換性が確保されます。

#### Q: MS Word のバージョンを設定すると、C# アプリケーションにどのようなメリットがありますか?

A: MS Word のバージョンを設定すると、その特定のバージョンの意図された書式と機能に従ってドキュメントが処理され、一貫した出力が提供されます。

#### Q: Aspose.Words は DOCX ドキュメントのみの処理に制限されていますか?

A: いいえ、Aspose.Words は DOC、RTF、HTML、PDF など、さまざまなドキュメント形式をサポートしており、さまざまな種類のドキュメントを処理できる多目的ツールとなっています。
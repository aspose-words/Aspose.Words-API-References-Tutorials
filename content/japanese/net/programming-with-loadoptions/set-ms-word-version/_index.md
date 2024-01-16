---
title: Ms Word のバージョンを設定する
linktitle: Ms Word のバージョンを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、指定したバージョンの MS Word でドキュメントを読み込む方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-loadoptions/set-ms-word-version/
---
C# アプリケーションで Word ドキュメントを使用して Word 処理を行う場合、ドキュメントをロードするときに使用する Microsoft Word のバージョンを指定することが必要になる場合があります。 .NET 用の Aspose.Words ライブラリを使用すると、LoadOptions を使用して、使用する MS Word のバージョンを簡単に設定できます。このステップバイステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、LoadOptions 読み込みオプションを使用して指定されたバージョンの MS Word でドキュメントを読み込む方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## 読み込みオプションの構成

最初のステップは、ドキュメントの読み込みオプションを設定することです。 LoadOptions クラスを使用して、読み込みパラメータを指定します。この例では、MswVersion プロパティを MS Word の目的のバージョンに設定する必要があります。たとえば、Microsoft Word 2010 バージョンを使用しています。その方法は次のとおりです。

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

新しい LoadOptions オブジェクトを作成し、MswVersion プロパティを MsWordVersion.Word2010 に設定して、MS Word 2010 のバージョンを指定します。

## 指定されたバージョンの MS Word を使用したドキュメントの読み込み

ロード オプションを設定したので、Document クラスを使用してドキュメントをロードし、ロード オプションを指定できます。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

この例では、指定されたロード オプションを使用して、ドキュメント ディレクトリにあるドキュメント「Document.docx」をロードします。

### Aspose.Words for .NET を使用した「MS Word バージョンの設定」機能を備えた LoadOptions のソース コードの例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//「MS Word バージョンの設定」機能を使用してロード オプションを構成する
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

//指定されたバージョンの MS Word を使用してドキュメントをロードします
Document doc = new Document(dataDir + "Document.docx", loadOptions);

//文書を保存する
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、MS Word の特定のバージョンを指定してドキュメントをアップロードする方法を説明しました。提供された手順に従い、提供されたコード C# ソースを使用することで、この機能を C# アプリケーションに簡単に適用できます。指定したバージョンの MS Word を使用して文書をロードすると、アプリケーションでの文書の適切な互換性と処理を確保できます。


### よくある質問

#### Q: C# アプリケーションにドキュメントをロードするときに MS Word のバージョンを指定する必要があるのはなぜですか?

MS Word のバージョンを指定すると、特にバージョン間で異なる可能性がある特定の書式設定や機能を扱う場合に、文書が正しく読み込まれて処理されることが保証されます。

#### Q: Aspose.Words はどのバージョンの MS Word をサポートしていますか?

A: Aspose.Words for .NET は、Word 97、Word 2003、Word 2007、Word 2010、Word 2013、Word 2016、Word 2019 など、さまざまなバージョンの MS Word をサポートしています。

#### Q: システムにインストールされているものとは異なるバージョンの MS Word を使用してドキュメントをロードできますか?

A: はい、Aspose.Words を使用すると、ドキュメントをロードするときに異なるバージョンの MS Word を指定できるため、ターゲット システムの MS Word バージョンが異なる場合でも互換性が確保されます。

#### Q: MS Word のバージョンを設定すると、C# アプリケーションにどのようなメリットがありますか?

A: MS Word のバージョンを設定すると、その特定のバージョンの意図した書式設定と機能に従って文書が処理され、一貫した出力が得られます。

#### Q: Aspose.Words は DOCX ドキュメントのみの処理に限定されていますか?

A: いいえ、Aspose.Words は DOC、RTF、HTML、PDF などを含むさまざまなドキュメント形式をサポートしており、さまざまな種類のドキュメントを処理するための多用途ツールとなっています。
---
title: 小さなメタファイルを圧縮しない
linktitle: 小さなメタファイルを圧縮しない
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ドキュメントを保存するときに「小さなメタファイルを圧縮しない」機能を有効にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

ドキュメント内のメタデータを圧縮することは、C# アプリケーションでファイルを処理する際の一般的な機能です。ただし、品質を維持するために、小さなファイルのメタデータを圧縮しない必要がある場合があります。このステップバイステップ ガイドでは、Aspose.Words for .NET の C# ソース コードを使用して、ドキュメント保存オプションで「小さなメタファイルを圧縮しない」機能を有効にする方法を説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## ステップ1: ドキュメントディレクトリを設定する

最初のステップは、ドキュメントを保存するディレクトリを定義することです。完全なディレクトリ パスを指定する必要があります。例:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ2: セクションとテキストを挿入する

次に、ドキュメントにセクションとテキストを挿入します。Aspose.Words が提供する DocumentBuilder クラスを使用して、ドキュメントのコンテンツを構築します。簡単な例を次に示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

この例では、新しい空白のドキュメントを作成し、DocumentBuilder を使用してテキストの行を追加します。

## ステップ3: セットアップオプション

'登録

次に、ドキュメントの保存オプションを設定しましょう。保存設定を指定するには、DocSaveOptions クラスを使用します。例:

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

この例では、保存オプションを設定するために新しい DocSaveOptions オブジェクトを作成しています。

## ステップ4: 「小さなメタファイルを圧縮しない」機能を有効にする

「小さなメタファイルを圧縮しない」機能を有効にするには、`Compliance` DocSaveOptionsオブジェクトのプロパティを値に設定する`PdfCompliance.PdfA1a`方法は次のとおりです。

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

この構成により、ドキュメントを保存するときに小さなファイルのメタデータが圧縮されなくなります。

## ステップ5: ドキュメントを保存する

最後に、`Save` Document クラスのメソッド。ファイルへのフルパスと希望のファイル名を指定します。例:

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

必ず「dataDir」をドキュメント ディレクトリへのパスに置き換えてください。

### Aspose.Words for .NET を使用した DocSaveOptions の DonCompress Small Metafiles 機能のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//テキストを含む 2 つのセクションを挿入します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//「小さなメタファイルを圧縮しない」機能を使用して保存オプションを構成する
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

//指定されたオプションでドキュメントを保存します
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、ドキュメントを保存するときに「小さなメタファイルを圧縮しない」機能を有効にする方法について説明しました。提供されている手順に従い、提供されている C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。圧縮されていない小さなファイルのメタデータを保持することは、ドキュメントの品質と整合性を維持するために重要です。
---
title: 小さなメタファイルを圧縮しないでください
linktitle: 小さなメタファイルを圧縮しないでください
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ドキュメントを保存するときに小さなメタファイルを圧縮しない機能を有効にする方法について説明します。
type: docs
weight: 10
url: /ja/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

ドキュメント内のメタデータの圧縮は、C# アプリケーションでファイルを文書処理する場合の一般的な機能です。ただし、品質を維持するために、小さなファイルのメタデータを圧縮しないことが必要な場合があります。このステップバイステップ ガイドでは、Aspose.Words for .NET の C# ソース コードを使用して、ドキュメント保存オプションの [小さなメタファイルを圧縮しない] 機能を有効にする方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## ステップ 1: ドキュメント ディレクトリを設定する

最初のステップは、ドキュメントを保存するディレクトリを定義することです。完全なディレクトリ パスを指定する必要があります。例えば ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 2: セクションとテキストを挿入する

その後、ドキュメントにセクションやテキストを挿入できます。 Aspose.Words が提供する DocumentBuilder クラスを使用して、ドキュメントのコンテンツを構築します。簡単な例を次に示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

この例では、新しい空のドキュメントを作成し、DocumentBuilder を使用してテキスト行を追加します。

## ステップ 3: セットアップ オプション

'登録

次に、ドキュメントの保存オプションを設定しましょう。 DocSaveOptions クラスを使用して保存設定を指定します。例えば ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

この例では、保存オプションを設定するために新しい DocSaveOptions オブジェクトを作成しています。

## ステップ 4: 「小さなメタファイルを圧縮しない」機能を有効にする

「小さなメタファイルを圧縮しない」機能を有効にするには、`Compliance` DocSaveOptions オブジェクトのプロパティを値に設定します。`PdfCompliance.PdfA1a`。その方法は次のとおりです。

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

この構成により、ドキュメントの保存時に小さなファイルのメタデータが圧縮されなくなります。

## ステップ 5: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを保存できます。`Save` Document クラスのメソッド。ファイルへのフルパスと任意のファイル名を指定します。例えば ：

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

必ず「dataDir」をドキュメント ディレクトリへのパスに置き換えてください。

### Aspose.Words for .NET を使用した、小さなメタファイルを圧縮しない機能を備えた DocSaveOptions のソース コード例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//テキストを含む 2 つのセクションを挿入します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//「小さなメタファイルを圧縮しない」機能で保存オプションを構成する
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

//指定したオプションを使用してドキュメントを保存します
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、ドキュメントを保存するときに「小さなメタファイルを圧縮しない」機能を有効にする方法について説明しました。提供された手順に従い、提供された C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。非圧縮の小さなファイルのメタデータを保存することは、ドキュメントの品質と整合性を維持するために重要です。
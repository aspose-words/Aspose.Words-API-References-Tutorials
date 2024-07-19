---
title: セクションをコピー
linktitle: セクションをコピー
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のセクションを別の文書にコピーする方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-section/copy-section/
---

このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して、Word 文書のセクションを別の文書にコピーする方法について説明します。セクションをコピーすると、ソース ドキュメントの特定のセクションをコピー先のドキュメントに転送できます。.NET プロジェクトでコードを理解して実装できるように、手順を追って説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- コピーしたいセクションを含むソース文書
- セクションをコピーする空の宛先ドキュメント

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメントが保存されているディレクトリパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`コード内に適切なパスを追加します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ソースドキュメントと宛先ドキュメントを読み込む
次に、ソースドキュメントを`Document`クラスと呼ばれる`srcDoc`空のインスタンスも作成します。`Document`クラスと呼ばれる`dstDoc`宛先ドキュメント用。

```csharp
//ソースドキュメントを読み込む
Document srcDoc = new Document(dataDir + "Document.docx");

//空の宛先ドキュメントを作成する
Document dstDoc = new Document();
```

## ステップ3: セクションをコピー先のドキュメントにコピーする
ソース文書から宛先文書にセクションをコピーするには、`ImportNode`ソース セクションをインポートし、それを宛先ドキュメントに追加するメソッド。

```csharp
//ソースセクションを取得する
Section sourceSection = srcDoc.Sections[0];

//セクションをコピー先のドキュメントにコピーします
Section newSection = (Section)dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
```

## ステップ4: 宛先ドキュメントを保存する
最後に、コピーしたセクションを含む宛先ドキュメントをファイルに保存します。

```csharp
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");
```

### Aspose.Words for .NET を使用したセクションのコピーのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document.docx");
Document dstDoc = new Document();
Section sourceSection = srcDoc.Sections[0];
Section newSection = (Section) dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");

```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のセクションを別の文書にコピーする方法を説明しました。セクションをコピーすると、ソース文書の特定のセクションをコピー先の文書に簡単に転送できます。この方法を使用して、文書のセクションを効率的に整理および操作してください。

### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書のセクションを別の文書にコピーするための前提条件は何ですか?

A: 始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた Aspose.Words for .NET ライブラリ
- コピーしたいセクションを含むソース文書
- セクションをコピーする空の宛先ドキュメント

#### Q: Aspose.Words for .NET でドキュメント ディレクトリを設定するにはどうすればいいですか?

A: ドキュメントを含むディレクトリへのパスを設定するには、`"YOUR DOCUMENT DIRECTORY"`コードに適切なパスを追加します。方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### Q: Aspose.Words for .NET でソース ドキュメントと宛先ドキュメントを読み込む方法を教えてください。

 A: ソースドキュメントを`Document`クラスと呼ばれる`srcDoc`空のインスタンスを作成し、`Document`クラスと呼ばれる`dstDoc`宛先ドキュメントの場合は、次のコードを使用できます。

```csharp
//ソースドキュメントを読み込む
Document srcDoc = new Document(dataDir + "Document.docx");

//空の宛先ドキュメントを作成する
Document dstDoc = new Document();
```

#### Q: Aspose.Words for .NET でソース ドキュメントから宛先ドキュメントにセクションをコピーするにはどうすればよいですか?

A: ソース ドキュメントから宛先ドキュメントにセクションをコピーするには、次のコードを使用できます。

```csharp
//ソースセクションを取得する
Section sourceSection = srcDoc.Sections[0];

//セクションをコピー先のドキュメントにコピーします
Section newSection = (Section)dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
```

#### Q: Aspose.Words for .NET でコピーしたセクションを含む宛先ドキュメントを保存するにはどうすればよいですか?

A: 最後に、次のコードを使用して、コピーしたセクションを含む宛先ドキュメントをファイルに保存できます。

```csharp
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");
```
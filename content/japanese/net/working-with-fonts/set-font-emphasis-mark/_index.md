---
title: フォント強調マークを設定する
linktitle: フォント強調マークを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のフォント強調スタイルを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-font-emphasis-mark/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント強調スタイルを設定する方法を説明します。フォントの強調は、テキスト内の特定の単語や語句を強調するために使用されます。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントを作成してカスタマイズする
のインスタンスを作成します。`Document`クラスと関連する`DocumentBuilder`ドキュメントのコンテンツを構築します。使用`Font.EmphasisMark`フォント強調スタイルを設定するプロパティ`EmphasisMark.UnderSolidCircle`。次に、`Write`そして`Writeln`のメソッド`DocumentBuilder`指定したフォントを強調してテキストを追加します。

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## ステップ 3: ドキュメントを保存する
を使用して文書を保存します。`Save`の方法`Document`適切なパスとファイル名を付けてください。

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Aspose.Words for .NET を使用したフォント強調マークの設定のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント強調スタイルを設定する方法を学習しました。さまざまな強調スタイルを試し、この機能を使用して文書内の単語や語句を強調表示します。

### よくある質問

#### Q: Aspose.Words を使用して Word 文書内の特定のフォントにアクセント記号を追加するにはどうすればよいですか?

A: Aspose.Words を使用して Word 文書内の特定のフォントにアクセント記号を追加するには、API を使用して目的のフォントに移動し、適切なアクセント記号を適用できます。これにより、選択したフォントでテキストにアクセント記号が追加されます。

#### Q: Aspose.Words を使用して Word 文書内のアクセント記号のスタイルを変更することはできますか?

A: はい、Aspose.Words を使用すると、Word 文書内のアクセント記号のスタイルを変更できます。 API を使用すると、色、サイズ、線種などのスタイル プロパティを調整して、アクセント マークの外観をカスタマイズできます。

#### Q: Aspose.Words を使用して Word 文書からすべてのアクセント記号を削除するにはどうすればよいですか?

A: Aspose.Words を使用して Word 文書からすべてのアクセント記号を削除するには、API を使用して文書を参照し、既存のアクセント記号を検出し、適切なメソッドを使用してそれらを削除します。これにより、ドキュメントからすべての強調マークが削除されます。

#### Q: Word 文書内のテキストの特定の部分にアクセント記号を追加できますか?

A: はい、Aspose.Words を使用して、Word 文書内のテキストの特定の部分にアクセント記号を追加できます。 API を使用してテキストの目的の範囲を選択し、テキストのその部分に適切な強調マークを追加できます。

#### Q: アクセント記号をニーズに合わせてカスタマイズできますか?

A: はい、Aspose.Words を使用して、ニーズに合わせてアクセント記号をカスタマイズできます。書式設定に合わせて、色、サイズ、線種などのアクセント マークのスタイル プロパティを調整できます。
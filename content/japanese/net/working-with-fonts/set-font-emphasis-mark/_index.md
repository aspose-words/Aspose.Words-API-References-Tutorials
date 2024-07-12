---
title: フォント強調マークの設定
linktitle: フォント強調マークの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のフォント強調スタイルを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-font-emphasis-mark/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント強調スタイルを設定する方法を説明します。フォント強調は、テキスト内の特定の単語またはフレーズを強調表示するために使用されます。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ1: ドキュメントディレクトリを定義する
まず、Word文書の場所にディレクトリパスを設定します。`"YOUR DOCUMENT DIRECTORY"`コード内に適切なパスを追加します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを作成してカスタマイズする
インスタンスを作成する`Document`クラスと関連する`DocumentBuilder`ドキュメントコンテンツを構築します。`Font.EmphasisMark`フォントの強調スタイルを設定するプロパティ`EmphasisMark.UnderSolidCircle` 次に、`Write`そして`Writeln`の`DocumentBuilder`指定されたフォント強調でテキストを追加します。

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## ステップ3: ドキュメントを保存する
ドキュメントを保存するには、`Save`方法の`Document`適切なパスとファイル名を使用します。

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Aspose.Words for .NET を使用してフォント強調マークを設定するサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のフォント強調スタイルを設定する方法を学習しました。さまざまな強調スタイルを試し、この機能を使用して文書内の単語やフレーズを強調表示します。

### よくある質問

#### Q: Aspose.Words を使用して Word 文書内の特定のフォントにアクセント記号を追加するにはどうすればよいですか?

A: Aspose.Words を使用して Word 文書内の特定のフォントにアクセント記号を追加するには、API を使用して目的のフォントに移動し、適切なアクセント記号を適用します。これにより、選択したフォントのテキストにアクセント記号が追加されます。

#### Q: Aspose.Words を使用して Word 文書内のアクセント記号のスタイルを変更することは可能ですか?

A: はい、Aspose.Words を使用すると、Word 文書内のアクセント記号のスタイルを変更できます。API を使用すると、色、サイズ、線種などのスタイル プロパティを調整して、アクセント記号の外観をカスタマイズできます。

#### Q: Aspose.Words を使用して Word 文書からすべてのアクセント記号を削除するにはどうすればよいですか?

A: Aspose.Words を使用して Word 文書からすべてのアクセント記号を削除するには、API を使用して文書を参照し、既存のアクセント記号を検出し、適切な方法で削除します。これにより、文書からすべての強調記号が削除されます。

#### Q: Word 文書内のテキストの特定の部分にアクセント記号を追加できますか?

A: はい、Aspose.Words を使用して Word 文書内のテキストの特定の部分にアクセント記号を追加できます。API を使用して必要なテキスト範囲を選択し、そのテキスト部分に適切な強調記号を追加できます。

#### Q: アクセント記号はニーズに合わせてカスタマイズできますか?

A: はい、Aspose.Words を使用してアクセント記号をニーズに合わせてカスタマイズできます。アクセント記号の色、サイズ、線種などのスタイル プロパティを、書式設定の設定に合わせて調整できます。
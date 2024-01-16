---
title: Aspose.Words for Java でドキュメントをマークダウンとして保存する
linktitle: ドキュメントをマークダウンとして保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用して Word ドキュメントを Markdown に変換する方法を学びます。このステップバイステップのガイドでは、テーブルの位置合わせ、画像の処理などについて説明します。
type: docs
weight: 18
url: /ja/java/document-loading-and-saving/saving-documents-as-markdown/
---

## Aspose.Words for Java でドキュメントをマークダウンとして保存する方法の概要

このステップバイステップ ガイドでは、Aspose.Words for Java を使用してドキュメントを Markdown として保存する方法を説明します。 Markdown は、テキスト ドキュメントの書式設定に一般的に使用される軽量のマークアップ言語です。 Aspose.Words for Java を使用すると、Word ドキュメントを Markdown 形式に簡単に変換できます。テーブルコンテンツの配置や画像の処理など、Markdown ファイルの保存に関するさまざまな側面について説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
-  Aspose.Words for Java ライブラリ。からダウンロードできます[ここ](https://releases.aspose.com/words/java/).

## ステップ 1: Word 文書を作成する

まず Word ドキュメントを作成します。後で Markdown 形式に変換します。このドキュメントは要件に応じてカスタマイズできます。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 2 つのセルを含む表を挿入する
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

//ドキュメントをMarkdownとして保存する
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

この例では、2 つのセルを含む単純な表を作成し、これらのセル内の段落の配置を設定します。次に、ドキュメントを Markdown として保存します。`MarkdownSaveOptions`.

## ステップ 2: テーブルコンテンツの配置をカスタマイズする

Aspose.Words for Java を使用すると、Markdown として保存するときにテーブルのコンテンツの配置をカスタマイズできます。表の内容を左、右、中央に配置したり、表の各列の最初の段落に基づいて自動的に決定させたりすることができます。

テーブルコンテンツの配置をカスタマイズする方法は次のとおりです。

```java
//テーブルコンテンツの配置を左に設定します
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

//テーブルコンテンツの配置を右に設定します
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

//テーブルコンテンツの配置を中央に設定します
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//表のコンテンツの配置を自動に設定します (最初の段落によって決定されます)。
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

を変更することで、`TableContentAlignment`プロパティを使用すると、Markdown に変換するときにテーブル内のコンテンツをどのように配置するかを制御できます。

## ステップ 3: 画像の処理

Markdown ドキュメントに画像を含めるには、画像が配置されているフォルダーを指定する必要があります。 Aspose.Words for Java を使用すると、画像フォルダーを`MarkdownSaveOptions`.

画像フォルダーを設定し、画像を含むドキュメントを保存する方法は次のとおりです。

```java
//画像を含むドキュメントをロードする
Document doc = new Document("document_with_images.docx");

//画像フォルダーのパスを設定します
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

//ドキュメントを画像とともに保存する
doc.save("document_with_images.md", saveOptions);
```

必ず交換してください`"document_with_images.docx"`画像を含む Word 文書へのパスと`"images_folder/"`画像が保存されているフォルダーへの実際のパスを置き換えます。

## Aspose.Words for Java でドキュメントをマークダウンとして保存するための完全なソース コード

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	//表内のすべての段落を揃えます。
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	//この場合の配置は、対応するテーブル列の最初の段落から取得されます。
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## 結論

このガイドでは、Aspose.Words for Java を使用してドキュメントを Markdown として保存する方法を説明しました。 Word ドキュメントの作成、表コンテンツの配置のカスタマイズ、Markdown ファイル内の画像の処理について説明しました。 Word ドキュメントを Markdown 形式に効率的に変換して、さまざまな出版プラットフォームやドキュメントのニーズに適したものにすることができるようになりました。

## よくある質問

### Aspose.Words for Java をインストールするにはどうすればよいですか?

 Aspose.Words for Java は、Java プロジェクトにライブラリを含めることによってインストールできます。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/words/java/)ドキュメントに記載されているインストール手順に従ってください。

### 表や画像を含む複雑な Word 文書を Markdown に変換できますか?

はい、Aspose.Words for Java は、表、画像、さまざまな書式設定要素を含む複雑な Word ドキュメントの Markdown への変換をサポートしています。ドキュメントの複雑さに応じて Markdown 出力をカスタマイズできます。

### Markdown ファイル内の画像を処理するにはどうすればよいですか?

 Markdown ファイルに画像を含めるには、次のコマンドを使用して画像フォルダーのパスを設定します。`setImagesFolder`のメソッド`MarkdownSaveOptions`。画像ファイルが指定されたフォルダーに保存されていることを確認してください。Aspose.Words for Java はそれに応じて画像参照を処理します。

### Aspose.Words for Java の試用版は利用可能ですか?

はい、Aspose Web サイトから Aspose.Words for Java の試用版を入手できます。試用版を使用すると、ライセンスを購入する前にライブラリの機能を評価できます。

### 他の例やドキュメントはどこで入手できますか?

 Aspose.Words for Java のその他の例、ドキュメント、詳細情報については、次の Web サイトを参照してください。[ドキュメンテーション](https://reference.aspose.com/words/java/).
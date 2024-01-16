---
title: Aspose.Words for Java を使用したテキスト ファイルのロード
linktitle: テキストファイルをロードする
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java のパワーを解き放ちます。テキストドキュメントのロード、リストの管理、スペースの処理、テキストの方向の制御を学びます。
type: docs
weight: 13
url: /ja/java/document-loading-and-saving/loading-text-files/
---

## Aspose.Words for Java を使用したテキスト ファイルのロードの概要

このガイドでは、Aspose.Words for Java を使用してテキスト ファイルをロードし、それらを Word ドキュメントとして操作する方法を説明します。リストの検出、スペースの処理、テキストの方向の制御など、さまざまな側面について説明します。

## ステップ 1: リストの検出

テキストドキュメントをロードしてリストを検出するには、次の手順に従います。

```java
//リストとして解釈される可能性のある部分を含む文字列の形式でプレーンテキストのドキュメントを作成します。
//ロード時に、最初の 3 つのリストは常に Aspose.Words によって検出されます。
//ロード後にリスト オブジェクトが作成されます。
final String TEXT_DOC = "Full stop delimiters:\n" +
        "1. First list item 1\n" +
        "2. First list item 2\n" +
        "3. First list item 3\n\n" +
        "Right bracket delimiters:\n" +
        "1) Second list item 1\n" +
        "2) Second list item 2\n" +
        "3) Second list item 3\n\n" +
        "Bullet delimiters:\n" +
        "• Third list item 1\n" +
        "• Third list item 2\n" +
        "• Third list item 3\n\n" +
        "Whitespace delimiters:\n" +
        "1 Fourth list item 1\n" +
        "2 Fourth list item 2\n" +
        "3 Fourth list item 3";
// 番目のリスト (リスト番号とリスト項目の内容の間に空白が入っています)
// LoadOptions オブジェクトの "DetectNumberingWithWhitespaces" が true に設定されている場合にのみ、リストとして検出されます。
//数字で始まる段落が誤ってリストとして検出されるのを避けるため。
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// LoadOptions をパラメータとして適用しながらドキュメントをロードし、結果を確認します。
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

このコードは、さまざまなリスト形式のテキスト ドキュメントをロードし、`DetectNumberingWithWhitespaces`リストを正しく検出するためのオプション。

## ステップ 2: スペース オプションの処理

テキストドキュメントをロードするときに先頭と末尾のスペースを制御するには、次のコードを使用できます。

```java
@Test
public void handleSpacesOptions() throws Exception {
    final String TEXT_DOC = "      Line 1 \n" +
            "    Line 2   \n" +
            " Line 3       ";
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
        loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
    }
    Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
```

この例では、テキストドキュメントをロードし、次を使用して先頭と末尾のスペースをトリミングします。`TxtLeadingSpacesOptions.TRIM`そして`TxtTrailingSpacesOptions.TRIM`.

## ステップ 3: テキストの方向を制御する

テキスト ドキュメントを読み込むときにテキストの方向を指定するには、次のコードを使用できます。

```java
@Test
public void documentTextDirection() throws Exception {
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setDocumentDirection(DocumentDirection.AUTO);
    }
    Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
    Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
    System.out.println(paragraph.getParagraphFormat().getBidi());
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
}
```

このコードは、ドキュメントの方向を自動検出に設定します (`DocumentDirection.AUTO`ヘブライ語テキストを含むテキスト ドキュメントを読み込みます。必要に応じて原稿の方向を調整できます。

## Aspose.Words for Java でテキスト ファイルをロードするための完全なソース コード

```java
public void detectNumberingWithWhitespaces() throws Exception {
	//リストとして解釈される可能性のある部分を含む文字列の形式でプレーンテキストのドキュメントを作成します。
	//ロード時に、最初の 3 つのリストは常に Aspose.Words によって検出されます。
	//ロード後にリスト オブジェクトが作成されます。
	final String TEXT_DOC = "Full stop delimiters:\n" +
			"1. First list item 1\n" +
			"2. First list item 2\n" +
			"3. First list item 3\n\n" +
			"Right bracket delimiters:\n" +
			"1) Second list item 1\n" +
			"2) Second list item 2\n" +
			"3) Second list item 3\n\n" +
			"Bullet delimiters:\n" +
			"• Third list item 1\n" +
			"• Third list item 2\n" +
			"• Third list item 3\n\n" +
			"Whitespace delimiters:\n" +
			"1 Fourth list item 1\n" +
			"2 Fourth list item 2\n" +
			"3 Fourth list item 3";
	// 番目のリスト (リスト番号とリスト項目の内容の間に空白が入っています)
	// LoadOptions オブジェクトの "DetectNumberingWithWhitespaces" が true に設定されている場合にのみ、リストとして検出されます。
	//数字で始まる段落が誤ってリストとして検出されるのを避けるため。
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// LoadOptions をパラメータとして適用しながらドキュメントをロードし、結果を確認します。
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
}
@Test
public void handleSpacesOptions() throws Exception {
	final String TEXT_DOC = "      Line 1 \n" +
			"    Line 2   \n" +
			" Line 3       ";
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
		loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
	}
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
@Test
public void documentTextDirection() throws Exception {
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDocumentDirection(DocumentDirection.AUTO);
	}
	Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
	Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
	System.out.println(paragraph.getParagraphFormat().getBidi());
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
	}
```

## 結論

このガイドでは、Aspose.Words for Java を使用してテキスト ファイルをロードし、リストを検出し、スペースを処理し、テキストの方向を制御する方法を説明しました。これらの手法を使用すると、Java アプリケーションでテキスト ドキュメントを効率的に操作できるようになります。

## よくある質問

### Aspose.Words for Java とは何ですか?

Aspose.Words for Java は、開発者が Java アプリケーションで Word ドキュメントをプログラム的に作成、操作、変換できるようにする強力なドキュメント処理ライブラリです。テキスト、表、画像、その他の文書要素を操作するための幅広い機能を提供します。

### Aspose.Words for Java を使い始めるにはどうすればよいですか?

Aspose.Words for Java の使用を開始するには、次の手順に従います。
1. Aspose.Words for Java ライブラリをダウンロードしてインストールします。
2. 次のドキュメントを参照してください。[Aspose.Words for Java API リファレンス](https://reference.aspose.com/words/java/)詳細な情報と例については、
3. サンプル コードとチュートリアルを参照して、ライブラリを効果的に使用する方法を学びます。

### Aspose.Words for Java を使用してテキスト ドキュメントをロードするにはどうすればよいですか?

 Aspose.Words for Java を使用してテキスト ドキュメントをロードするには、`TxtLoadOptions`クラスと`Document`クラス。必要に応じて、スペースとテキストの方向を処理するための適切なオプションを必ず指定してください。詳細な例については、この記事のステップバイステップ ガイドを参照してください。

### 読み込んだテキストドキュメントを他の形式に変換できますか?

はい、Aspose.Words for Java を使用すると、ロードされたテキスト ドキュメントを DOCX、PDF などのさまざまな形式に変換できます。使用できます`Document`変換を実行するクラス。具体的な変換例についてはドキュメントを確認してください。

### 読み込まれたテキストドキュメント内のスペースはどのように処理すればよいですか?

次を使用して、読み込まれたテキストドキュメント内で先頭と末尾のスペースをどのように処理するかを制御できます。`TxtLoadOptions` 。のようなオプション`TxtLeadingSpacesOptions`そして`TxtTrailingSpacesOptions`必要に応じてスペースをトリミングまたは保存できます。例については、このガイドの「スペースの処理オプション」セクションを参照してください。

### Aspose.Words for Java におけるテキスト方向の重要性は何ですか?

テキストの方向は、ヘブライ語やアラビア語などのスクリプトや言語が混在するドキュメントには不可欠です。 Aspose.Words for Java には、テキストの方向を指定するオプションが用意されており、これらの言語でのテキストの適切なレンダリングと書式設定が保証されます。このガイドの「テキストの方向の制御」セクションでは、テキストの方向を設定する方法を説明します。

### Aspose.Words for Java のその他のリソースとサポートはどこで入手できますか?

追加のリソース、ドキュメント、サポートについては、次のサイトにアクセスしてください。[Aspose.Words for Java ドキュメント](https://reference.aspose.com/words/java/)。また、Aspose.Words コミュニティ フォーラムに参加したり、特定の問題や問い合わせについてサポートが必要な場合は Aspose サポートに連絡したりすることもできます。

### Aspose.Words for Java は商用プロジェクトに適していますか?

はい、Aspose.Words for Java は個人プロジェクトと商用プロジェクトの両方に適しています。さまざまな使用シナリオに対応するライセンス オプションを提供します。 Aspose Web サイトでライセンス条項と価格を必ず確認し、プロジェクトに適切なライセンスを選択してください。
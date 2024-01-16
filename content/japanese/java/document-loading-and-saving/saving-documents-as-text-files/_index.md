---
title: Aspose.Words for Java でドキュメントをテキスト ファイルとして保存する
linktitle: 文書をテキストファイルとして保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java でドキュメントをテキスト ファイルとして保存する方法を学びます。 Java コード例を含むステップバイステップ ガイドに従ってください。
type: docs
weight: 24
url: /ja/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Aspose.Words for Java でドキュメントをテキスト ファイルとして保存する方法の概要

このチュートリアルでは、Aspose.Words for Java ライブラリを使用してドキュメントをテキスト ファイルとして保存する方法を説明します。 Aspose.Words は Word ドキュメントを操作するための強力な Java API であり、プレーン テキストを含むさまざまな形式でドキュメントを保存するためのさまざまなオプションを提供します。これを実現する手順を説明し、途中でサンプル Java コードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
-  Aspose.Words for Java ライブラリがプロジェクトに統合されました。からダウンロードできます[ここ](https://releases.aspose.com/words/java/).
- Java プログラミングの基本的な知識。

## ステップ 1: ドキュメントを作成する

ドキュメントをテキスト ファイルとして保存するには、まず Aspose.Words を使用してドキュメントを作成する必要があります。いくつかのコンテンツを含むドキュメントを作成するための簡単な Java コード スニペットを次に示します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

このコードでは、新しいドキュメントを作成し、そこにさまざまな言語のテキストを含むテキストを追加します。

## ステップ 2: テキスト保存オプションを定義する

次に、ドキュメントをテキスト ファイルとして保存する方法を指定するテキスト保存オプションを定義する必要があります。 Bidi マークの追加、リストのインデントなど、さまざまな設定を構成できます。 2 つの例を見てみましょう。

### 例 1: Bidi マークの追加

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

この例では、`TxtSaveOptions`オブジェクトを設定して、`AddBidiMarks`財産を`true`テキスト出力に Bidi マークを含めます。

### 例 2: リストのインデントにタブ文字を使用する

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

ここでは、カウント 1 でリストのインデントにタブ文字を使用するように保存オプションを構成します。

## ステップ 3: ドキュメントをテキストとして保存する

テキスト保存オプションを定義したので、ドキュメントをテキスト ファイルとして保存できます。次のコードは、これを行う方法を示しています。

```java
doc.save("output.txt", saveOptions);
```

交換する`"output.txt"`テキスト ファイルを保存する目的のファイル パスを入力します。

## Aspose.Words for Java でドキュメントをテキスト ファイルとして保存するための完全なソース コード

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // レベルのインデントを持つリストを作成します。
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // レベルのインデントを持つリストを作成します。
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## 結論

このチュートリアルでは、Aspose.Words for Java でドキュメントをテキスト ファイルとして保存する方法を学習しました。ドキュメントを作成し、テキスト保存オプションを定義し、ドキュメントをテキスト形式で保存する手順について説明しました。 Aspose.Words はドキュメントの保存に関して幅広い柔軟性を提供し、特定の要件に合わせて出力を調整できます。

## よくある質問

### テキスト出力に Bidi マークを追加するにはどうすればよいですか?

テキスト出力に Bidi マークを追加するには、`AddBidiMarks`の財産`TxtSaveOptions`に`true`。例えば：

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### リストのインデント文字をカスタマイズできますか?

はい、リストのインデント文字をカスタマイズするには、`ListIndentation`の財産`TxtSaveOptions`。たとえば、リストのインデントにタブ文字を使用するには、次の操作を実行できます。

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words for Java は多言語テキストの処理に適していますか?

はい、Aspose.Words for Java は多言語テキストの処理に適しています。さまざまな言語と文字エンコーディングをサポートしているため、さまざまな言語のドキュメントを操作するための多用途の選択肢となります。

### Aspose.Words for Java のその他のドキュメントやリソースにアクセスするにはどうすればよいですか?

 Aspose.Words for Java の包括的なドキュメントとリソースは、Aspose ドキュメント Web サイトで見つけることができます。[Aspose.Words for Java ドキュメント](https://reference.aspose.com/words/java/).

### Aspose.Words for Java はどこでダウンロードできますか?

 Aspose.Words for Java ライブラリは、Aspose Web サイトからダウンロードできます。[Java 用 Aspose.Words をダウンロード](https://releases.aspose.com/words/java/).
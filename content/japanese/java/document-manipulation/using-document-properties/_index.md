---
title: Aspose.Words for Java でのドキュメント プロパティの使用
linktitle: ドキュメントのプロパティの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用してドキュメント管理を最適化します。この包括的なチュートリアルでは、ドキュメント プロパティの操作方法、カスタム メタデータの追加方法などを学びます。
type: docs
weight: 32
url: /ja/java/document-manipulation/using-document-properties/
---

## ドキュメントのプロパティの概要

ドキュメントのプロパティは、あらゆるドキュメントの重要な部分です。これらは、タイトル、作成者、件名、キーワードなど、ドキュメント自体に関する追加情報を提供します。 Aspose.Words for Java では、組み込みドキュメント プロパティとカスタム ドキュメント プロパティの両方を操作できます。

## ドキュメントのプロパティの列挙

### 組み込みプロパティ

組み込みのドキュメント プロパティを取得して操作するには、次のコード スニペットを使用できます。

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

このコードは、ドキュメントの名前と、「タイトル」、「作成者」、「キーワード」などのプロパティを含む組み込みプロパティを表示します。

### カスタムプロパティ

カスタム ドキュメント プロパティを操作するには、次のコード スニペットを使用できます。

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

このコード スニペットは、ブール値、文字列、日付、リビジョン番号、数値などのカスタム ドキュメント プロパティを追加する方法を示します。

## ドキュメントのプロパティの削除

特定のドキュメント プロパティを削除するには、次のコードを使用できます。

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

このコードは、カスタム プロパティ「承認日」をドキュメントから削除します。

## コンテンツへのリンクの構成

場合によっては、ドキュメント内にリンクを作成することが必要になる場合があります。その方法は次のとおりです。

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // content プロパティにリンクを追加します。
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

このコード スニペットは、ドキュメント内にブックマークを作成し、そのブックマークにリンクするカスタム ドキュメント プロパティを追加する方法を示しています。

## 測定単位間の変換

Aspose.Words for Java では、測定単位を簡単に変換できます。その方法の例を次に示します。

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    //余白をインチ単位で設定します。
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

このコード スニペットは、さまざまなマージンと距離をポイントに変換することでインチ単位で設定します。

## 制御文字の使用

制御文字はテキストを扱うときに便利です。テキスト内の制御文字を置換する方法は次のとおりです。

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // 「\r」制御文字を「\r\n」に置き換えます。
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

この例では、キャリッジ リターン (`\r`) キャリッジリターンとそれに続くラインフィード (`\r\n`）。

## 結論

ドキュメント プロパティは、Aspose.Words for Java でドキュメントを効果的に管理および整理する上で重要な役割を果たします。組み込みプロパティ、カスタム プロパティ、または制御文字の使用のいずれを使用する場合でも、ドキュメント管理機能を強化するためのさまざまなツールを自由に使用できます。

## よくある質問

### 組み込みのドキュメント プロパティにアクセスするにはどうすればよいですか?

 Aspose.Words for Java の組み込みドキュメント プロパティにアクセスするには、`getBuiltInDocumentProperties`のメソッド`Document`物体。このメソッドは、反復処理できる組み込みプロパティのコレクションを返します。

### カスタムドキュメントプロパティをドキュメントに追加できますか?

はい、カスタム ドキュメント プロパティをドキュメントに追加するには、`CustomDocumentProperties`コレクション。文字列、ブール値、日付、数値などのさまざまなデータ型を使用してカスタム プロパティを定義できます。

### 特定のカスタム ドキュメント プロパティを削除するにはどうすればよいですか?

特定のカスタム ドキュメント プロパティを削除するには、`remove`のメソッド`CustomDocumentProperties`コレクションを作成し、削除するプロパティの名前をパラメーターとして渡します。

### ドキュメント内のコンテンツにリンクする目的は何ですか?

ドキュメント内のコンテンツにリンクすると、ドキュメントの特定の部分への動的な参照を作成できます。これは、インタラクティブなドキュメントやセクション間の相互参照を作成する場合に役立ちます。

### Aspose.Words for Java で異なる測定単位間で変換するにはどうすればよいですか?

 Aspose.Words for Java では、`ConvertUtil`クラス。インチからポイント、ポイントからセンチメートルなどの単位を変換するメソッドが提供されます。
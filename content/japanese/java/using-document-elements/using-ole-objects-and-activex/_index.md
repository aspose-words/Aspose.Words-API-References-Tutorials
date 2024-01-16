---
title: Aspose.Words for Java での OLE オブジェクトと ActiveX コントロールの使用
linktitle: OLE オブジェクトと ActiveX コントロールの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java で OLE オブジェクトと ActiveX コントロールを使用する方法を学びます。インタラクティブなドキュメントを簡単に作成できます。今すぐ始めましょう！
type: docs
weight: 21
url: /ja/java/using-document-elements/using-ole-objects-and-activex/
---
このチュートリアルでは、Aspose.Words for Java で OLE (オブジェクトのリンクと埋め込み) オブジェクトと ActiveX コントロールを操作する方法を説明します。 OLE オブジェクトと ActiveX コントロールは、スプレッドシート、マルチメディア ファイル、対話型コントロールなどの外部コンテンツを埋め込んだり、リンクしたりしてドキュメントを強化できる強力なツールです。コード例を詳しく見て、これらの機能を効果的に使用する方法を学びましょう。

### 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Words for Java : Java プロジェクトに Aspose.Words ライブラリがインストールされていることを確認します。からダウンロードできます[ここ](https://releases.aspose.com/words/java/).

2. Java 開発環境 : システム上に動作する Java 開発環境がセットアップされている必要があります。

### OLE オブジェクトの挿入

まず、OLE オブジェクトを Word 文書に挿入します。単純な Word 文書を作成し、Web ページを表す OLE オブジェクトを挿入します。

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com"、"htmlfile"、true、true、null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

このコードでは、新しいドキュメントを作成し、Aspose Web サイトを表示する OLE オブジェクトを挿入します。 URL を目的のコンテンツに置き換えることができます。

### OlePackage を使用した OLE オブジェクトの挿入

次に、OlePackage を使用して OLE オブジェクトを挿入する方法を見てみましょう。これにより、外部ファイルを OLE オブジェクトとしてドキュメントに埋め込むことができます。

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

この例では、OlePackage を使用して OLE オブジェクトを挿入し、外部ファイルを埋め込みオブジェクトとして含めることができます。

### OLE オブジェクトをアイコンとして挿入する

次に、OLE オブジェクトをアイコンとして挿入する方法を見てみましょう。埋め込まれたファイルを表すアイコンを表示したい場合に便利です。

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

このコードでは、OLE オブジェクトをアイコンとして挿入し、埋め込みコンテンツをより視覚的に魅力的に表現します。

### ActiveX コントロールのプロパティの読み取り

ここで、ActiveX コントロールに焦点を移しましょう。 Word 文書内の ActiveX コントロールのプロパティを読み取る方法を学習します。

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

このコードでは、Word 文書内の図形を繰り返し処理し、ActiveX コントロールを識別し、そのプロパティを取得します。

### 結論

おめでとう！ Aspose.Words for Java で OLE オブジェクトと ActiveX コントロールを操作する方法を学習しました。これらの機能により、動的でインタラクティブなドキュメントを作成する可能性が広がります。

### よくある質問

### Word 文書内の OLE オブジェクトの目的は何ですか? 
   - OLE オブジェクトを使用すると、ファイルや Web ページなどの外部コンテンツを Word 文書内に埋め込んだり、リンクしたりできます。

### ドキュメント内の OLE オブジェクトの外観をカスタマイズできますか? 
   - はい、アイコンやファイル名の設定など、OLE オブジェクトの外観をカスタマイズできます。

### ActiveX コントロールとは何ですか? ActiveX コントロールを使用するとドキュメントをどのように強化できますか? 
   - ActiveX コントロールは、フォーム コントロールやマルチメディア プレーヤーなどの機能を Word 文書に追加できる対話型要素です。

### Aspose.Words for Java はエンタープライズ レベルのドキュメント自動化に適していますか? 
   - はい、Aspose.Words for Java は、Java アプリケーションでのドキュメントの生成と操作を自動化するための強力なライブラリです。

### Aspose.Words for Java にはどこからアクセスできますか? 
   -  Aspose.Words for Java は次からダウンロードできます。[ここ](https://releases.aspose.com/words/java/).

今すぐ Aspose.Words for Java を使い始めて、ドキュメントの自動化とカスタマイズの可能性を最大限に引き出してください。

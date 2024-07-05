---
title: Aspose.Words Java を使用した HTML ドキュメントの高度な保存オプション
linktitle: HTML文書を保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for Javaのさまざまな高度なHTMLドキュメント保存オプションについて説明しました。これらのオプションを使用すると、高品質のHTMLを作成できます。
type: docs
weight: 16
url: /ja/java/document-loading-and-saving/advance-html-documents-saving-options/
---

このチュートリアルでは、Aspose.Words for Java が提供する高度な HTML ドキュメント保存オプションについて説明します。Aspose.Words は、Word ドキュメントを操作するための強力な Java API であり、ドキュメントの操作と変換のための幅広い機能を提供します。

## 1. はじめに
Aspose.Words for Java を使用すると、Word 文書をプログラムで操作できます。このチュートリアルでは、Word 文書を HTML に変換する方法を制御できる、高度な HTML 文書保存オプションに焦点を当てます。

## 2. 輸出ラウンドトリップ情報
の`exportRoundtripInformation`この方法を使用すると、ラウンドトリップ情報を保持しながら Word 文書を HTML にエクスポートできます。この情報は、文書固有の詳細を失うことなく HTML を Word 形式に戻す場合に役立ちます。

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. フォントをBase64としてエクスポートする
とともに`exportFontsAsBase64`この方法を使用すると、文書で使用されているフォントを HTML 内の Base64 エンコード データとしてエクスポートできます。これにより、HTML 表現で元の Word 文書と同じフォント スタイルが保持されます。

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. リソースのエクスポート
の`exportResources`メソッドを使用すると、CSS スタイルシートの種類を指定し、フォント リソースをエクスポートできます。また、HTML 内のリソース フォルダーとリソースのエイリアスを設定することもできます。

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. メタファイルをEMFまたはWMFに変換する
の`convertMetafilesToEmfOrWmf`この方法を使用すると、ドキュメント内のメタファイルを EMF または WMF 形式に変換して、HTML での互換性とスムーズなレンダリングを確保できます。

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    //簡潔にするためにコード スニペットは表示されません。
}
```

## 6. メタファイルをSVGに変換する
使用`convertMetafilesToSvg`メタファイルを SVG 形式に変換する方法。この形式は、HTML ドキュメントでベクター グラフィックを表示するのに最適です。

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    //簡潔にするためにコード スニペットは表示されません。
}
```

## 7. CSSクラス名プレフィックスを追加する
とともに`addCssClassNamePrefix`メソッドを使用すると、エクスポートされた HTML 内の CSS クラス名にプレフィックスを追加できます。これにより、既存のスタイルとの競合を防ぐことができます。

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. MHTMLリソースのCID URLをエクスポートする
の`exportCidUrlsForMhtmlResources`このメソッドは、ドキュメントを MHTML 形式で保存するときに使用されます。これにより、リソースの Content-ID URL をエクスポートできます。

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    //簡潔にするためにコード スニペットは表示されません。
}
```

## 9. フォント名を解決する
の`resolveFontNames`このメソッドは、ドキュメントを HTML 形式で保存するときにフォント名を解決するのに役立ち、異なるプラットフォーム間で一貫したレンダリングを保証します。

```java
@Test
public void resolveFontNames() throws Exception {
    //簡潔にするためにコード スニペットは表示されません。
}
```

## 10. テキスト入力フォームフィールドをテキストとしてエクスポート
の`exportTextInputFormFieldAsText`このメソッドは、フォーム フィールドを HTML 内のプレーン テキストとしてエクスポートし、簡単に読み取りおよび編集できるようにします。

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    //簡潔にするためにコード スニペットは表示されません。
}
```

## 11. 結論
このチュートリアルでは、Aspose.Words for Java が提供する高度な HTML ドキュメント保存オプションについて説明しました。これらのオプションを使用すると、変換プロセスを細かく制御できるため、元の Word ドキュメントによく似た HTML ドキュメントを作成できます。

## 12. よくある質問
Aspose.Words for Java および HTML ドキュメント保存オプションの使用に関するよくある質問を以下に示します。

### Q1: Aspose.Words for Java を使用して HTML を Word 形式に戻すにはどうすればよいですか?
 HTMLをWord形式に戻すには、Aspose.Words APIの`load`HTML ドキュメントを読み込み、Word 形式で保存する方法。

### Q2: HTML にエクスポートするときに CSS スタイルをカスタマイズできますか?
はい、HTMLで使用されているスタイルシートを変更するか、`addCssClassNamePrefix` CSS クラス名にプレフィックスを追加するメソッド。

### Q3: HTML 出力を Web 表示用に最適化する方法はありますか?
はい、フォントを Base64 としてエクスポートしたり、メタファイルを SVG に変換したりするなどのオプションを構成することで、HTML 出力を Web 表示用に最適化できます。

### Q4: 複雑な Word 文書を HTML に変換する場合、何か制限はありますか?
Aspose.Words for Java は強力な変換機能を提供しますが、複雑なレイアウトを持つ複雑な Word 文書では、目的の HTML 出力を実現するために追加の後処理が必要になる場合があります。

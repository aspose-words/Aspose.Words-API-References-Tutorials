---
title: Aspose.Words Java を使用した高度な HTML ドキュメント保存オプション
linktitle: HTMLドキュメントを保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for Java を使用したさまざまな高度な HTML ドキュメント保存オプションについて説明しました。これらのオプションを使用すると、高品質の HTML を作成できます。
type: docs
weight: 16
url: /ja/java/document-loading-and-saving/advance-html-documents-saving-options/
---

このチュートリアルでは、Aspose.Words for Java が提供する高度な HTML ドキュメント保存オプションを検討します。 Aspose.Words は、Word ドキュメントを操作するための強力な Java API であり、ドキュメントの操作と変換のための幅広い機能を提供します。

## 1. はじめに
Aspose.Words for Java を使用すると、Word ドキュメントをプログラムで操作できます。このチュートリアルでは、Word 文書を HTML に変換する方法を制御できる、高度な HTML 文書保存オプションに焦点を当てます。

## 2.往復情報のエクスポート
の`exportRoundtripInformation`このメソッドを使用すると、ラウンドトリップ情報を保持しながら Word ドキュメントを HTML にエクスポートできます。この情報は、ドキュメント固有の詳細を失わずに HTML を Word 形式に変換し直す場合に役立ちます。

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. フォントを Base64 としてエクスポートする
とともに`exportFontsAsBase64`メソッドを使用すると、ドキュメントで使用されているフォントを HTML の Base64 エンコード データとしてエクスポートできます。これにより、HTML 表現が元の Word 文書と同じフォント スタイルを保持することが保証されます。

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
の`exportResources`メソッドを使用すると、CSS スタイルシートのタイプを指定し、フォント リソースをエクスポートできます。 HTML でリソース フォルダーとリソースのエイリアスを設定することもできます。

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

## 5. メタファイルを EMF または WMF に変換する
の`convertMetafilesToEmfOrWmf`このメソッドを使用すると、ドキュメント内のメタファイルを EMF または WMF 形式に変換でき、HTML での互換性とスムーズなレンダリングが保証されます。

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    //簡潔にするためにコード スニペットは示されていません。
}
```

## 6. メタファイルをSVGに変換する
使用`convertMetafilesToSvg`メタファイルをSVG形式に変換するメソッド。この形式は、HTML ドキュメントでベクター グラフィックを表示するのに最適です。

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    //簡潔にするためにコード スニペットは示されていません。
}
```

## 7. CSS クラス名のプレフィックスを追加する
とともに`addCssClassNamePrefix`メソッドを使用すると、エクスポートされた HTML 内の CSS クラス名にプレフィックスを追加できます。これは、既存のスタイルとの競合を防ぐのに役立ちます。

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

## 8. MHTML リソースの CID URL をエクスポートする
の`exportCidUrlsForMhtmlResources`メソッドは、ドキュメントを MHTML 形式で保存するときに使用されます。リソースの Content-ID URL をエクスポートできます。

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    //簡潔にするためにコード スニペットは示されていません。
}
```

## 9. フォント名の解決
の`resolveFontNames`このメソッドは、ドキュメントを HTML 形式で保存するときにフォント名を解決するのに役立ち、さまざまなプラットフォーム間で一貫したレンダリングを保証します。

```java
@Test
public void resolveFontNames() throws Exception {
    //簡潔にするためにコード スニペットは示されていません。
}
```

## 10. テキスト入力フォームフィールドをテキストとしてエクスポート
の`exportTextInputFormFieldAsText`このメソッドは、フォーム フィールドを HTML のプレーン テキストとしてエクスポートし、簡単に読み取ったり編集したりできるようにします。

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    //簡潔にするためにコード スニペットは示されていません。
}
```

## 11. 結論
このチュートリアルでは、Aspose.Words for Java が提供する高度な HTML ドキュメント保存オプションを検討しました。これらのオプションを使用すると、変換プロセスをきめ細かく制御できるため、元の Word 文書によく似た HTML 文書を作成できます。

## 12.よくある質問
Aspose.Words for Java および HTML ドキュメント保存オプションの操作に関してよくある質問をいくつか示します。

### Q1: Aspose.Words for Java を使用して HTML を Word 形式に変換するにはどうすればよいですか?
 HTML を Word 形式に変換するには、Aspose.Words API を使用できます。`load`メソッドを使用して、HTML ドキュメントをロードし、Word 形式で保存します。

### Q2: HTML にエクスポートするときに CSS スタイルをカスタマイズできますか?
はい、HTML で使用されているスタイルシートを変更するか、`addCssClassNamePrefix` CSS クラス名にプレフィックスを追加するメソッド。

### Q3: HTML 出力を Web 表示用に最適化する方法はありますか?
はい、フォントを Base64 としてエクスポートしたり、メタファイルを SVG に変換したりするオプションを構成することで、Web 表示用の HTML 出力を最適化できます。

### Q4: 複雑な Word 文書を HTML に変換する場合、制限はありますか?
Aspose.Words for Java は強力な変換機能を提供しますが、複雑なレイアウトを持つ複雑な Word 文書では、目的の HTML 出力を実現するために追加の後処理が必要になる場合があります。

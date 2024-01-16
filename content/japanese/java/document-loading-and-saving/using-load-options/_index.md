---
title: Aspose.Words for Java でのロード オプションの使用
linktitle: ロードオプションの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java のロード オプションをマスターします。効率的な Java ドキュメント処理のために、ドキュメントの読み込み、暗号化の処理、図形の変換、Word バージョンの設定などをカスタマイズします。
type: docs
weight: 11
url: /ja/java/document-loading-and-saving/using-load-options/
---

## Aspose.Words for Java でのロード オプションの使用の概要

このチュートリアルでは、Aspose.Words for Java でロード オプションを使用する方法を説明します。ロード オプションを使用すると、ドキュメントのロードと処理の方法をカスタマイズできます。ダーティ フィールドの更新、暗号化されたドキュメントの読み込み、図形の Office Math への変換、MS Word のバージョンの設定、一時フォルダーの指定、警告の処理、メタファイルの PNG への変換など、さまざまなシナリオを取り上げます。段階的に見ていきましょう。

## ダーティフィールドの更新

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

このコード スニペットは、ドキュメント内のダーティ フィールドを更新する方法を示しています。の`setUpdateDirtyFields(true)`メソッドは、ドキュメントのロード中にダーティ フィールドが確実に更新されるようにするために使用されます。

## 暗号化されたドキュメントをロードする

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

ここでは、パスワードを使用して暗号化されたドキュメントをロードします。の`LoadOptions`コンストラクターはドキュメントのパスワードを受け入れます。また、次を使用してドキュメントを保存するときに新しいパスワードを指定することもできます。`OdtSaveOptions`.

## 形状を Office Math に変換

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

このコードは、ドキュメントの読み込み中に図形を Office Math オブジェクトに変換する方法を示します。の`setConvertShapeToOfficeMath(true)`メソッドによってこの変換が可能になります。

## MS Wordのバージョンを設定する

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

ドキュメントをロードする MS Word のバージョンを指定できます。この例では、次を使用してバージョンを Microsoft Word 2010 に設定します。`setMswVersion`.

## 一時フォルダーを使用する

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

を使用して一時フォルダーを設定することで、`setTempFolder`を使用すると、ドキュメント処理中に一時ファイルを保存する場所を制御できます。

## 警告コールバック

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        //ドキュメントのロード中に警告が発生したときに処理します。
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

このコードは、ドキュメントの読み込み中に警告を処理するために警告コールバックを設定する方法を示します。警告が発生したときのアプリケーションの動作をカスタマイズできます。

## メタファイルを PNG に変換

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

ドキュメントの読み込み中にメタファイル (WMF など) を PNG イメージに変換するには、`setConvertMetafilesToPng(true)`方法。

## Aspose.Words for Java のロード オプションを操作するための完全なソース コード

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
}
@Test
public void setMsWordVersion() throws Exception {
	//新しい LoadOptions オブジェクトを作成します。これは、デフォルトで MS Word 2019 仕様に従ってドキュメントをロードします。
	//読み込みバージョンを Microsoft Word 2010 に変更します。
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//ドキュメントの読み込み中に発生した警告とその詳細を出力します。
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## 結論

このチュートリアルでは、Aspose.Words for Java でのロード オプションの操作に関するさまざまな側面を詳しく掘り下げました。ロード オプションは、ドキュメントのロードおよび処理方法をカスタマイズする上で重要な役割を果たし、ドキュメントの処理を特定のニーズに合わせて調整できるようになります。このガイドで説明されている重要なポイントを要約しましょう。

## よくある質問

### ドキュメントの読み込み中の警告にどう対処すればよいですか?

に示すように、警告コールバックを設定できます。`warningCallback()`上記の方法。をカスタマイズします。`DocumentLoadingWarningCallback`アプリケーションの要件に従って警告を処理するクラス。

### ドキュメントを読み込むときに図形を Office Math オブジェクトに変換できますか?

はい、次を使用して図形を Office Math オブジェクトに変換できます。`loadOptions.setConvertShapeToOfficeMath(true)`.

### ドキュメントを読み込む際に MS Word のバージョンを指定するにはどうすればよいですか?

使用`loadOptions.setMswVersion(MsWordVersion.WORD_2010)`ドキュメントをロードする MS Word のバージョンを指定します。

### の目的は何ですか`setTempFolder` method in Load Options?

の`setTempFolder`このメソッドを使用すると、ドキュメント処理中に一時ファイルが保存されるフォルダーを指定できます。
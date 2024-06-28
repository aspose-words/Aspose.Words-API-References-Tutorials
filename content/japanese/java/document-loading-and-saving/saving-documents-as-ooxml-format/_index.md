---
title: Aspose.Words for Java でドキュメントを OOXML 形式で保存する
linktitle: ドキュメントを OOXML 形式で保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用してドキュメントを OOXML 形式で保存する方法を学びます。ファイルを簡単に保護、最適化、カスタマイズします。
type: docs
weight: 20
url: /ja/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Aspose.Words for Java でドキュメントを OOXML 形式で保存する方法の概要

このガイドでは、Aspose.Words for Java を使用してドキュメントを OOXML 形式で保存する方法を説明します。 OOXML (Office Open XML) は、Microsoft Word およびその他のオフィス アプリケーションで使用されるファイル形式です。ドキュメントを OOXML 形式で保存するためのさまざまなオプションと設定について説明します。

## 前提条件

始める前に、Aspose.Words for Java ライブラリがプロジェクトに設定されていることを確認してください。

## パスワード暗号化を使用して文書を保存する

文書を OOXML 形式で保存するときに、パスワードを使用して文書を暗号化できます。その方法は次のとおりです。

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

//ドキュメントをロードする
Document doc = new Document("Document.docx");

// OoxmlSaveOptions を作成し、パスワードを設定する
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

//文書を暗号化して保存する
doc.save("EncryptedDoc.docx", saveOptions);
```

## OOXML 準拠の設定

ドキュメントを保存するときに、OOXML 準拠レベルを指定できます。たとえば、ISO 29500:2008 (厳密) に設定できます。その方法は次のとおりです。

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

//ドキュメントをロードする
Document doc = new Document("Document.docx");

// Word 2016 用に最適化する
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

//OoxmlSaveOptions を作成し、コンプライアンス レベルを設定する
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

//コンプライアンス設定でドキュメントを保存する
doc.save("ComplianceDoc.docx", saveOptions);
```

## 最終保存時刻プロパティの更新

ドキュメントを保存するときに、ドキュメントの「最終保存時刻」プロパティを更新することを選択できます。その方法は次のとおりです。

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

//ドキュメントをロードする
Document doc = new Document("Document.docx");

// OoxmlSaveOptions を作成し、最終保存時刻プロパティの更新を有効にする
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

//更新されたプロパティを使用してドキュメントを保存します
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## レガシー制御文字の保持

ドキュメントに従来の制御文字が含まれている場合は、保存時にそれらを保持することを選択できます。その方法は次のとおりです。

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

//従来の制御文字を含むドキュメントをロードする
Document doc = new Document("LegacyControlChars.doc");

//FLAT_OPC 形式で OoxmlSaveOptions を作成し、従来の制御文字の保持を有効にする
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

//従来の制御文字を使用してドキュメントを保存する
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## 圧縮レベルの設定

文書を保存する際の圧縮レベルを調整できます。たとえば、圧縮を最小限に抑えるために SUPER_FAST に設定できます。その方法は次のとおりです。

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

//ドキュメントをロードする
Document doc = new Document("Document.docx");

// OoxmlSaveOptions を作成し、圧縮レベルを設定する
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

//指定した圧縮レベルでドキュメントを保存します
doc.save("FastCompressionDoc.docx", saveOptions);
```

これらは、Aspose.Words for Java を使用してドキュメントを OOXML 形式で保存するときに使用できる重要なオプションと設定の一部です。必要に応じて、より多くのオプションを自由に検討し、ドキュメント保存プロセスをカスタマイズしてください。

## Aspose.Words for Java でドキュメントを OOXML 形式で保存するための完全なソース コード

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## 結論

この包括的なガイドでは、Aspose.Words for Java を使用してドキュメントを OOXML 形式で保存する方法を説明しました。パスワードによるドキュメントの暗号化、特定の OOXML 標準への準拠の確認、ドキュメント プロパティの更新、従来の制御文字の保持、圧縮レベルの調整が必要な場合でも、Aspose.Words は要件を満たす多用途のツール セットを提供します。

## よくある質問

### パスワードで保護されたドキュメントからパスワード保護を削除するにはどうすればよいですか?

パスワードで保護された文書からパスワード保護を解除するには、正しいパスワードを使用して文書を開いて、保存オプションでパスワードを指定せずに保存します。これにより、パスワード保護なしで文書が保存されます。

### ドキュメントを OOXML 形式で保存するときにカスタム プロパティを設定できますか?

はい、ドキュメントを OOXML 形式で保存する前に、ドキュメントのカスタム プロパティを設定できます。使用`BuiltInDocumentProperties`そして`CustomDocumentProperties`クラスを使用して、作成者、タイトル、キーワード、カスタム プロパティなどのさまざまなプロパティを設定します。

### ドキュメントを OOXML 形式で保存する場合のデフォルトの圧縮レベルは何ですか?

 Aspose.Words for Java を使用してドキュメントを OOXML 形式で保存する場合のデフォルトの圧縮レベルは次のとおりです。`NORMAL` 。圧縮レベルを次のように変更できます。`SUPER_FAST`または`MAXIMUM`必要に応じて。
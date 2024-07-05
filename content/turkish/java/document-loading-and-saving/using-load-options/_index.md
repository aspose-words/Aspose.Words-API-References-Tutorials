---
title: Aspose.Words for Java'da Yükleme Seçeneklerini Kullanma
linktitle: Yükleme Seçeneklerini Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da Yükleme Seçeneklerinde Uzmanlaşma. Verimli Java belge işleme için belge yüklemeyi özelleştirin, şifrelemeyi yönetin, şekilleri dönüştürün, Word sürümlerini ayarlayın ve daha fazlasını yapın.
type: docs
weight: 11
url: /tr/java/document-loading-and-saving/using-load-options/
---

## Aspose.Words for Java'da Yükleme Seçenekleri ile Çalışmaya Giriş

Bu derste Aspose.Words for Java'da Yükleme Seçenekleri ile nasıl çalışılacağını inceleyeceğiz. Yükleme Seçenekleri, belgelerin yüklenme ve işlenme şeklini özelleştirmenize olanak tanır. Kirli alanların güncellenmesi, şifrelenmiş belgelerin yüklenmesi, şekillerin Office Math'a dönüştürülmesi, MS Word sürümünün ayarlanması, geçici bir klasör belirlenmesi, uyarıların işlenmesi ve meta dosyaların PNG'ye dönüştürülmesi gibi çeşitli senaryoları ele alacağız. Adım adım dalalım.

## Kirli Alanları Güncelle

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 Bu kod parçacığı, bir belgedeki kirli alanların nasıl güncelleştirileceğini gösterir.`setUpdateDirtyFields(true)` Doküman yükleme sırasında kirli alanların güncellenmesini sağlamak için yöntem kullanılır.

## Şifreli Belgeyi Yükle

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 Burada şifrelenmiş bir belgeyi şifre kullanarak yüklüyoruz.`LoadOptions` yapıcı belge parolasını kabul eder ve ayrıca belgeyi kullanarak kaydederken yeni bir parola da belirleyebilirsiniz.`OdtSaveOptions`.

## Shape'i Ofis Matematiğine Dönüştür

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 Bu kod, belge yükleme sırasında şekillerin Office Math nesnelerine nasıl dönüştürüleceğini gösterir.`setConvertShapeToOfficeMath(true)`yöntemi bu dönüşümü sağlar.

## MS Word Sürümünü Ayarla

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 Belge yükleme için MS Word sürümünü belirleyebilirsiniz. Bu örnekte sürümü Microsoft Word 2010 olarak ayarladık.`setMswVersion`.

## Geçici Klasörü Kullan

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 Geçici klasörü kullanarak ayarlayarak`setTempFolder`, belge işleme sırasında geçici dosyaların nerede saklanacağını kontrol edebilirsiniz.

## Uyarı Geri Arama

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // Belge yükleme sırasında ortaya çıkan uyarıları ele alın.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

Bu kod, belge yükleme sırasında uyarıları işlemek için bir uyarı geri aramasının nasıl ayarlanacağını gösterir. Uyarılar oluştuğunda uygulamanızın davranışını özelleştirebilirsiniz.

## Meta Dosyalarını PNG'ye Dönüştür

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 Belge yükleme sırasında meta dosyalarını (örn. WMF) PNG görüntülerine dönüştürmek için`setConvertMetafilesToPng(true)` yöntem.

## Aspose.Words for Java'da Yükleme Seçenekleri ile Çalışmak İçin Tam Kaynak Kodu

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
	// Belgeleri varsayılan olarak MS Word 2019 spesifikasyonuna göre yükleyecek yeni bir LoadOptions nesnesi oluşturun
	// ve yükleme sürümünü Microsoft Word 2010 olarak değiştirin.
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
		//Belge yükleme sırasında ortaya çıkan uyarıları ve ayrıntılarını yazdırır.
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

## Çözüm

Bu eğitimde Aspose.Words for Java'da Yükleme Seçenekleri ile çalışmanın çeşitli yönlerini inceledik. Yükleme Seçenekleri, belgelerin yüklenme ve işlenme şeklinin özelleştirilmesinde önemli bir rol oynayarak belge işleme sürecinizi özel ihtiyaçlarınıza göre uyarlamanıza olanak tanır. Bu kılavuzda ele alınan önemli noktaları özetleyelim:

## SSS'ler

### Belge yükleme sırasında uyarıları nasıl halledebilirim?

 Şekilde gösterildiği gibi bir uyarı geri araması ayarlayabilirsiniz.`warningCallback()` Yukarıdaki yöntem. Özelleştirin`DocumentLoadingWarningCallback` uyarıları uygulamanızın gereksinimlerine göre işlemek için sınıf.

### Bir belgeyi yüklerken şekilleri Office Math nesnelerine dönüştürebilir miyim?

 Evet, kullanarak şekilleri Office Math nesnelerine dönüştürebilirsiniz.`loadOptions.setConvertShapeToOfficeMath(true)`.

### Belge yükleme için MS Word sürümünü nasıl belirlerim?

 Kullanmak`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` belge yükleme için MS Word sürümünü belirtmek için.

###  Amacı nedir?`setTempFolder` method in Load Options?

`setTempFolder`yöntemi, belge işleme sırasında geçici dosyaların depolandığı klasörü belirtmenize olanak tanır.
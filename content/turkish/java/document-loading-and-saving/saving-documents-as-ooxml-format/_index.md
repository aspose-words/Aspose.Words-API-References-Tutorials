---
title: Aspose.Words for Java'da Belgeleri OOXML Formatında Kaydetme
linktitle: Belgeleri OOXML Formatında Kaydetme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java ile belgeleri OOXML formatında nasıl kaydedeceğinizi öğrenin. Dosyalarınızı zahmetsizce koruyun, optimize edin ve özelleştirin.
type: docs
weight: 20
url: /tr/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Aspose.Words for Java'da Belgeleri OOXML Formatında Kaydetmeye Giriş

Bu kılavuzda Aspose.Words for Java kullanarak OOXML formatındaki belgelerin nasıl kaydedileceğini inceleyeceğiz. OOXML (Office Open XML), Microsoft Word ve diğer ofis uygulamaları tarafından kullanılan bir dosya formatıdır. Belgeleri OOXML formatında kaydetmek için çeşitli seçenekleri ve ayarları ele alacağız.

## Önkoşullar

Başlamadan önce projenizde Aspose.Words for Java kütüphanesinin kurulu olduğundan emin olun.

## Bir Belgeyi Parola Şifrelemeyle Kaydetme

Belgenizi OOXML formatında kaydederken şifre ile şifreleyebilirsiniz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Belgeyi yükleyin
Document doc = new Document("Document.docx");

// OoxmlSaveOptions oluşturun ve şifreyi ayarlayın
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Belgeyi şifrelemeyle kaydedin
doc.save("EncryptedDoc.docx", saveOptions);
```

## OOXML Uyumluluğunu Ayarlama

Belgeyi kaydederken OOXML uyumluluk düzeyini belirtebilirsiniz. Örneğin ISO 29500:2008 (Katı) olarak ayarlayabilirsiniz. İşte nasıl:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Belgeyi yükleyin
Document doc = new Document("Document.docx");

// Word 2016 için Optimize Etme
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// OoxmlSaveOptions oluşturun ve uyumluluk düzeyini ayarlayın
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Belgeyi uyumluluk ayarıyla kaydedin
doc.save("ComplianceDoc.docx", saveOptions);
```

## Son Kaydedilen Zaman Özelliği Güncelleniyor

Belgeyi kaydederken "Son Kaydedilen Zaman" özelliğini güncellemeyi seçebilirsiniz. İşte nasıl:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Belgeyi yükleyin
Document doc = new Document("Document.docx");

// OoxmlSaveOptions oluşturun ve Son Kaydedilen Zaman özelliğinin güncellenmesini etkinleştirin
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Belgeyi güncellenen özellikle kaydedin
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Eski Kontrol Karakterlerini Korumak

Belgeniz eski kontrol karakterleri içeriyorsa kaydederken bunları saklamayı seçebilirsiniz. İşte nasıl:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Eski kontrol karakterlerini içeren bir belge yükleyin
Document doc = new Document("LegacyControlChars.doc");

//FLAT_OPC formatıyla OoxmlSaveOptions oluşturun ve eski kontrol karakterlerinin korunmasını etkinleştirin
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Belgeyi eski kontrol karakterleriyle kaydedin
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Sıkıştırma Seviyesini Ayarlama

Belgeyi kaydederken sıkıştırma düzeyini ayarlayabilirsiniz. Örneğin, minimum sıkıştırma için bunu SUPER_FAST olarak ayarlayabilirsiniz. İşte nasıl:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Belgeyi yükleyin
Document doc = new Document("Document.docx");

// OoxmlSaveOptions oluşturun ve sıkıştırma düzeyini ayarlayın
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Belgeyi belirtilen sıkıştırma düzeyiyle kaydedin
doc.save("FastCompressionDoc.docx", saveOptions);
```

Bunlar, Aspose.Words for Java'yı kullanarak belgeleri OOXML formatında kaydederken kullanabileceğiniz temel seçeneklerden ve ayarlardan bazılarıdır. Daha fazla seçeneği keşfetmekten ve belge kaydetme sürecinizi gerektiği gibi özelleştirmekten çekinmeyin.

## Aspose.Words for Java'da Belgeleri OOXML Formatında Kaydetmek İçin Tam Kaynak Kodu

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

## Çözüm

Bu kapsamlı kılavuzda Aspose.Words for Java kullanarak OOXML formatındaki belgelerin nasıl kaydedileceğini araştırdık. Belgelerinizi parolalarla şifrelemeniz, belirli OOXML standartlarıyla uyumluluğu sağlamanız, belge özelliklerini güncellemeniz, eski kontrol karakterlerini korumanız veya sıkıştırma düzeylerini ayarlamanız gerekiyorsa Aspose.Words, gereksinimlerinizi karşılayacak çok yönlü bir araç seti sunar.

## SSS'ler

### Parola korumalı bir belgeden parola korumasını nasıl kaldırabilirim?

Parola korumalı bir belgedeki parola korumasını kaldırmak için belgeyi doğru parolayla açabilir ve ardından kaydetme seçeneklerinde parola belirtmeden kaydedebilirsiniz. Bu, belgeyi parola koruması olmadan kaydedecektir.

### Bir belgeyi OOXML formatında kaydederken özel özellikleri ayarlayabilir miyim?

 Evet, bir belgeyi OOXML formatında kaydetmeden önce onun özel özelliklerini ayarlayabilirsiniz. Kullan`BuiltInDocumentProperties`Ve`CustomDocumentProperties` yazar, başlık, anahtar kelimeler ve özel özellikler gibi çeşitli özellikleri ayarlamak için sınıflar.

### Bir belgeyi OOXML formatında kaydederken varsayılan sıkıştırma düzeyi nedir?

 Aspose.Words for Java kullanarak bir belgeyi OOXML formatında kaydederken varsayılan sıkıştırma düzeyi şu şekildedir:`NORMAL` . Sıkıştırma düzeyini şu şekilde değiştirebilirsiniz:`SUPER_FAST` veya`MAXIMUM` ihyaç olduğu gibi.
---
title: Aspose.Words for Java ile Metin Dosyalarını Yükleme
linktitle: Metin Dosyalarını Yükleme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'nın Gücünün Kilidini Açın. Metin Belgelerini Yüklemeyi, Listeleri Yönetmeyi, Boşlukları İşlemeyi ve Metin Yönünü Kontrol Etmeyi öğrenin.
type: docs
weight: 13
url: /tr/java/document-loading-and-saving/loading-text-files/
---

## Aspose.Words for Java ile Metin Dosyalarını Yüklemeye Giriş

Bu kılavuzda Aspose.Words for Java kullanarak metin dosyalarının nasıl yükleneceğini ve bunların Word belgeleri olarak nasıl değiştirileceğini inceleyeceğiz. Listeleri algılama, boşlukları yönetme ve metin yönünü kontrol etme gibi çeşitli hususları ele alacağız.

## Adım 1: Listeleri Algılama

Bir metin belgesi yüklemek ve listeleri algılamak için şu adımları takip edebilirsiniz:

```java
// Liste olarak yorumlanabilecek parçaları içeren bir dize biçiminde düz metin belgesi oluşturun.
// Yükleme sonrasında ilk üç liste her zaman Aspose.Words tarafından algılanacaktır.
// ve yükleme sonrasında onlar için List nesneleri oluşturulacaktır.
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
//Liste numarası ve liste öğesi içerikleri arasında boşluk bulunan dördüncü liste,
// Yalnızca LoadOptions nesnesindeki "DetectNumberingWithWhitespaces" true olarak ayarlandığında liste olarak algılanacaktır,
// Sayılarla başlayan paragrafların yanlışlıkla liste olarak algılanmasını önlemek için.
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// LoadOptions'ı parametre olarak uygularken belgeyi yükleyin ve sonucu doğrulayın.
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Bu kod, çeşitli liste formatlarına sahip bir metin belgesinin nasıl yükleneceğini ve`DetectNumberingWithWhitespaces` Listeleri doğru şekilde algılama seçeneği.

## Adım 2: Alan Seçeneklerini Kullanma

Bir metin belgesi yüklerken baştaki ve sondaki boşlukları kontrol etmek için aşağıdaki kodu kullanabilirsiniz:

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

 Bu örnekte, bir metin belgesi yüklüyoruz ve öndeki ve sondaki boşlukları kırpıyoruz.`TxtLeadingSpacesOptions.TRIM`Ve`TxtTrailingSpacesOptions.TRIM`.

## 3. Adım: Metin Yönünü Kontrol Etme

Bir metin belgesini yüklerken metnin yönünü belirtmek için aşağıdaki kodu kullanabilirsiniz:

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

Bu kod, belgenin yönünü otomatik algılamaya ayarlar (`DocumentDirection.AUTO`ve İbranice metin içeren bir metin belgesi yükler. Belge yönünü gerektiği gibi ayarlayabilirsiniz.

## Aspose.Words for Java ile Metin Dosyalarını Yüklemek İçin Tam Kaynak Kodu

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// Liste olarak yorumlanabilecek parçaları içeren bir dize biçiminde düz metin belgesi oluşturun.
	// Yükleme sonrasında ilk üç liste her zaman Aspose.Words tarafından algılanacaktır.
	// ve yükleme sonrasında onlar için List nesneleri oluşturulacaktır.
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
	// Liste numarası ile liste öğesi içeriği arasında boşluk bulunan dördüncü liste,
	// Yalnızca LoadOptions nesnesindeki "DetectNumberingWithWhitespaces" true olarak ayarlandığında liste olarak algılanacaktır,
	// Sayılarla başlayan paragrafların yanlışlıkla liste olarak algılanmasını önlemek için.
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// LoadOptions'ı parametre olarak uygularken belgeyi yükleyin ve sonucu doğrulayın.
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

## Çözüm

Bu kılavuzda Aspose.Words for Java kullanarak metin dosyalarının nasıl yükleneceğini, listelerin nasıl tespit edileceğini, boşlukların nasıl yönetileceğini ve metin yönünün nasıl kontrol edileceğini araştırdık. Bu teknikler, Java uygulamalarınızda metin belgelerini etkili bir şekilde değiştirmenize olanak tanır.

## SSS'ler

### Aspose.Words for Java nedir?

Aspose.Words for Java, geliştiricilerin Java uygulamalarında Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir belge işleme kitaplığıdır. Metin, tablolar, resimler ve diğer belge öğeleriyle çalışmak için çok çeşitli özellikler sunar.

### Aspose.Words for Java'yı nasıl kullanmaya başlayabilirim?

Aspose.Words for Java'yı kullanmaya başlamak için şu adımları izleyin:
1. Aspose.Words for Java kütüphanesini indirip yükleyin.
2.  adresindeki belgelere bakın.[Aspose.Words for Java API Referansı](https://reference.aspose.com/words/java/)detaylı bilgi ve örnekler için.
3. Kitaplığın etkili bir şekilde nasıl kullanılacağını öğrenmek için örnek kodu ve öğreticileri keşfedin.

### Aspose.Words for Java kullanarak bir metin belgesini nasıl yüklerim?

 Aspose.Words for Java'yı kullanarak bir metin belgesi yüklemek için`TxtLoadOptions` sınıf ve`Document` sınıf. Gerektiğinde boşlukları ve metin yönünü işlemek için uygun seçenekleri belirttiğinizden emin olun. Ayrıntılı bir örnek için bu makaledeki adım adım kılavuza bakın.

### Yüklenen bir metin belgesini diğer formatlara dönüştürebilir miyim?

 Evet, Aspose.Words for Java, yüklü bir metin belgesini DOCX, PDF ve daha fazlasını içeren çeşitli formatlara dönüştürmenize olanak tanır. Şunu kullanabilirsiniz:`Document` Dönüşümleri gerçekleştirmek için sınıf. Belirli dönüşüm örnekleri için belgelere bakın.

### Yüklenen metin belgelerindeki boşlukları nasıl yönetirim?

 Yüklenen metin belgelerinde baştaki ve sondaki boşlukların nasıl işleneceğini kullanarak kontrol edebilirsiniz.`TxtLoadOptions` . Gibi seçenekler`TxtLeadingSpacesOptions`Ve`TxtTrailingSpacesOptions`alanları gerektiği gibi kırpmanıza veya korumanıza olanak tanır. Örnek için bu kılavuzdaki "Taşıma Alanları Seçenekleri" bölümüne bakın.

### Aspose.Words for Java'da metin yönünün önemi nedir?

İbranice veya Arapça gibi karışık yazılar veya diller içeren belgeler için metin yönü önemlidir. Aspose.Words for Java, metin yönünü belirleme seçenekleri sunarak bu dillerdeki metnin doğru şekilde oluşturulmasını ve biçimlendirilmesini sağlar. Bu kılavuzdaki "Metin Yönünü Kontrol Etme" bölümü metin yönünün nasıl ayarlanacağını gösterir.

### Aspose.Words for Java için daha fazla kaynağı ve desteği nerede bulabilirim?

 Ek kaynaklar, belgeler ve destek için şu adresi ziyaret edin:[Aspose.Words for Java Belgelendirmesi](https://reference.aspose.com/words/java/). Ayrıca Aspose.Words topluluk forumlarına katılabilir veya belirli sorunlar veya sorularla ilgili yardım almak için Aspose desteğiyle iletişime geçebilirsiniz.

### Aspose.Words for Java ticari projelere uygun mu?

Evet, Aspose.Words for Java hem kişisel hem de ticari projeler için uygundur. Çeşitli kullanım senaryolarına uyum sağlamak için lisanslama seçenekleri sunar. Projenize uygun lisansı seçmek için Aspose web sitesindeki lisans koşullarını ve fiyatlandırmayı incelediğinizden emin olun.
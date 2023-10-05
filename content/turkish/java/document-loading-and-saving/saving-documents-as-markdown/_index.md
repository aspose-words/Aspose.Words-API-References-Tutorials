---
title: Aspose.Words for Java'da Belgeleri Markdown olarak Kaydetme
linktitle: Belgeleri Markdown Olarak Kaydetme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java ile Word belgelerini Markdown'a nasıl dönüştüreceğinizi öğrenin. Bu adım adım kılavuz, tablo hizalamayı, görüntü işlemeyi ve daha fazlasını kapsar.
type: docs
weight: 18
url: /tr/java/document-loading-and-saving/saving-documents-as-markdown/
---

## Aspose.Words for Java'da Belgeleri Markdown Olarak Kaydetmeye Giriş

Bu adım adım kılavuzda Aspose.Words for Java kullanarak belgelerin Markdown olarak nasıl kaydedileceğini göstereceğiz. Markdown, metin belgelerini biçimlendirmek için yaygın olarak kullanılan hafif bir biçimlendirme dilidir. Aspose.Words for Java ile Word belgelerinizi kolayca Markdown formatına dönüştürebilirsiniz. Tablo içeriği hizalaması ve görüntülerin işlenmesi de dahil olmak üzere Markdown dosyalarını kaydetmenin farklı yönlerini ele alacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Words for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).

## Adım 1: Word Belgesi Oluşturma

Daha sonra Markdown formatına dönüştüreceğimiz bir Word belgesi oluşturarak başlayalım. Bu belgeyi ihtiyaçlarınıza göre özelleştirebilirsiniz.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İki hücreli bir tablo ekleme
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

// Belgeyi Markdown olarak kaydedin
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

 Bu örnekte iki hücreli basit bir tablo oluşturuyoruz ve bu hücreler içindeki paragrafların hizalamasını ayarlıyoruz. Daha sonra belgeyi Markdown olarak kaydediyoruz.`MarkdownSaveOptions`.

## 2. Adım: Tablo İçeriği Hizalamasını Özelleştirin

Aspose.Words for Java, Markdown olarak kaydederken tablo içeriğinin hizalamasını özelleştirmenize olanak tanır. Tablo içeriğini sola, sağa, ortaya hizalayabilir veya her tablo sütunundaki ilk paragrafa göre otomatik olarak belirlenmesini sağlayabilirsiniz.

Tablo içeriği hizalamasını nasıl özelleştireceğiniz aşağıda açıklanmıştır:

```java
// Tablo içeriği hizalamasını sola ayarla
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

// Tablo içeriği hizalamasını sağa ayarla
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

// Tablo içeriği hizalamasını merkeze ayarlayın
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//Tablo içeriği hizalamasını otomatik olarak ayarlayın (ilk paragrafa göre belirlenir)
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

 Değiştirerek`TableContentAlignment` özelliğiyle, Markdown'a dönüştürme sırasında tabloların içindeki içeriğin nasıl hizalanacağını kontrol edebilirsiniz.

## 3. Adım: Görüntüleri İşleme

 Markdown belgenize görsel eklemek için görsellerin bulunduğu klasörü belirtmeniz gerekir. Aspose.Words for Java, resimler klasörünü`MarkdownSaveOptions`.

Resimler klasörünü nasıl ayarlayacağınız ve resimlerle birlikte belgeyi nasıl kaydedeceğiniz aşağıda açıklanmıştır:

```java
// Görüntü içeren bir belge yükleyin
Document doc = new Document("document_with_images.docx");

// Görüntüler klasörü yolunu ayarlayın
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

// Belgeyi resimlerle kaydedin
doc.save("document_with_images.md", saveOptions);
```

 Değiştirdiğinizden emin olun`"document_with_images.docx"` görüntüleri içeren Word belgenizin yolu ile birlikte`"images_folder/"` resimlerinizin saklandığı klasörün gerçek yolunu belirtin.

## Aspose.Words for Java'da Belgeleri Markdown Olarak Kaydetmek İçin Tam Kaynak Kodu

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	// Tablo içindeki tüm paragrafların hizalanmasını sağlar.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	// Bu durumda hizalama ilgili tablo sütunundaki ilk paragraftan alınacaktır.
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## Çözüm

Bu kılavuzda Aspose.Words for Java kullanarak belgelerin Markdown olarak nasıl kaydedileceğini araştırdık. Bir Word belgesinin oluşturulmasını, tablo içeriği hizalamasını özelleştirmeyi ve Markdown dosyalarındaki görüntüleri yönetmeyi ele aldık. Artık Word belgelerinizi verimli bir şekilde Markdown biçimine dönüştürebilir, böylece onları çeşitli yayınlama platformları ve belge gereksinimlerine uygun hale getirebilirsiniz.

## SSS'ler

### Aspose.Words for Java'yı nasıl yüklerim?

 Aspose.Words for Java, kütüphaneyi Java projenize dahil ederek kurulabilir. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/words/java/) ve belgelerde verilen kurulum talimatlarını izleyin.

### Tablolar ve resimler içeren karmaşık Word belgelerini Markdown'a dönüştürebilir miyim?

Evet, Aspose.Words for Java, tablolar, resimler ve çeşitli biçimlendirme öğeleri içeren karmaşık Word belgelerinin Markdown'a dönüştürülmesini destekler. Markdown çıktısını belgenizin karmaşıklığına göre özelleştirebilirsiniz.

### Markdown dosyalarındaki görselleri nasıl işleyebilirim?

 Görüntüleri Markdown dosyalarına dahil etmek için, görüntülerin klasör yolunu kullanarak ayarlayın.`setImagesFolder`yöntem`MarkdownSaveOptions`. Görüntü dosyalarının belirtilen klasörde saklandığından emin olun; Aspose.Words for Java, görüntü referanslarını buna göre işleyecektir.

### Aspose.Words for Java'nın deneme sürümü mevcut mu?

Evet, Aspose.Words for Java'nın deneme sürümünü Aspose web sitesinden edinebilirsiniz. Deneme sürümü, bir lisans satın almadan önce kütüphanenin yeteneklerini değerlendirmenize olanak tanır.

### Daha fazla örnek ve belgeyi nerede bulabilirim?

 Aspose.Words for Java ile ilgili daha fazla örnek, belge ve ayrıntılı bilgi için lütfen şu adresi ziyaret edin:[dokümantasyon](https://reference.aspose.com/words/java/).
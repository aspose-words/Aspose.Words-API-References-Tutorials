---
title: Word Belgesi Üst Bilgi Alt Bilgi Yer İşaretlerini PDF Belgesine Aktar
linktitle: Word Belgesi Üst Bilgi Alt Bilgi Yer İşaretlerini PDF Belgesine Aktar
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile kelime belgesi üst bilgi alt bilgi yer imlerini pdf belge yer imlerine dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Bu makale, Aspose.Words for .NET ile word belgesi başlık altbilgi yer imlerinin pdf belgesi özelliğine nasıl aktarılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgenin üst bilgilerinden ve alt bilgilerinden yer imlerini nasıl dışa aktaracağınızı ve uygun yer imleriyle bir PDF oluşturmayı öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Ardından, işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "Üstbilgilerdeki ve altbilgilerdeki yer imleri.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## 3. Adım: PDF olarak kaydetme seçeneklerini yapılandırın

 Üstbilgi ve altbilgi yer imlerini dışa aktarmak için,`PdfSaveOptions` nesne. Bu örnekte, varsayılan yer imi anahat seviyesini 1 olarak ve üst bilgi ve alt bilgi yer imi dışa aktarma modunu "Birinci" olarak ayarladık.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## 4. Adım: Belgeyi üst bilgiler ve alt bilgiler yer imleriyle birlikte PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET kullanarak bir belgeden üstbilgi ve altbilgi yer imlerini başarıyla dışa aktardınız ve uygun yer imleriyle bir PDF oluşturdunuz.

### Aspose.Words for .NET ile üstbilgi ve altbilgi yer imlerini dışa aktarmak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak üstbilgi ve altbilgi yer imlerinin bir Word belgesinden bir PDF belgesine nasıl aktarılacağını açıkladık. Dışa aktarılan yer imleri, oluşturulan PDF belgesinde kolay gezinmeye ve karşılık gelen üstbilgilere ve altbilgilere hızlı başvuruya olanak tanır. Aspose.Words for .NET kullanarak bir belgeden üstbilgi ve altbilgi yer imlerini dışa aktarmak ve uygun yer imleriyle bir PDF oluşturmak için açıklanan adımları izleyin. Belgelerinize giden doğru yolu belirttiğinizden ve kaydetme seçeneklerini gerektiği gibi yapılandırdığınızdan emin olun.

# Sıkça Sorulan Sorular

### S: Üstbilgi ve altbilgi yer imlerini bir Word belgesinden PDF belgesine dışa aktarmak nedir?
Y: Üstbilgi ve altbilgi yer imlerini Word belgesinden PDF belgesine dışa aktarmak, PDF belgesinde üstbilgilerden ve altbilgilerden yer imleri tutmaya ve oluşturmaya yönelik bir özelliktir. orijinal Word belgesinin altbilgileri. Bu, kullanıcıların üstbilgilere ve altbilgilere karşılık gelen yer imlerini kullanarak PDF belgesinde hızlı ve kolay bir şekilde gezinmesine olanak tanır.

### S: Aspose.Words for .NET'i üstbilgi ve altbilgi yer imlerini bir Word belgesinden bir PDF belgesine dışa aktarmak için nasıl kullanabilirim?
C: Aspose.Words for .NET kullanarak bir Word belgesinden üstbilgi ve altbilgi yer imlerini bir PDF belgesine dışa aktarmak için şu adımları izleyin:

 Değiştirerek belgelerinizin bulunduğu dizin yolunu ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 kullanarak işlemek istediğiniz belgeyi yükleyin.`Document` sınıfı ve belirtilen belgeler dizinindeki Word belgesinin yolunu belirtin.

 örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıfı ve uygun üstbilgi ve altbilgi yer imi seçeneklerini ayarlama.

 kullanarak belgeyi PDF formatında kaydedin.`Save` yöntemi`Document`yolu ve kaydetme seçeneklerini belirten sınıf.

### S: Üst bilgi ve alt bilgi yer imlerini bir PDF belgesine dışa aktarmanın faydaları nelerdir?
C: Üst bilgi ve alt bilgi yer imlerini bir PDF belgesine dışa aktarmanın avantajları şunlardır:

Kolay Gezinme: Yer imleri, kullanıcıların belirli üstbilgilere ve altbilgilere başvurarak bir PDF belgesinde kolayca gezinmesine olanak tanır.

Hızlı Referans: Yer imleri, kullanıcıların üstbilgi ve altbilgiye dayalı olarak PDF belgesinin ilgili bölümlerini hızlı bir şekilde bulmasına olanak tanır.
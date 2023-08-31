---
title: Word Belgesi Üst Bilgisi Alt Bilgisi Yer İmlerini PDF Belgesine Dışa Aktarma
linktitle: Word Belgesi Üst Bilgisi Alt Bilgisi Yer İmlerini PDF Belgesine Dışa Aktarma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile word belgesi üst bilgi alt bilgi yer imlerini pdf belge yer imlerine aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Bu makale, Aspose.Words for .NET ile word belgesi üst bilgi alt bilgi yer imlerinin pdf belgesi özelliğine nasıl aktarılacağı konusunda adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgenin üstbilgilerinden ve altbilgilerinden yer imlerini nasıl dışa aktaracağınızı ve uygun yer imleriyle bir PDF oluşturmayı anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Daha sonra işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "Üstbilgi ve altbilgilerdeki yer işaretleri.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## 3. Adım: PDF olarak kaydetme seçeneklerini yapılandırın

 Üstbilgi ve altbilgi yer işaretlerini dışa aktarmak için,`PdfSaveOptions` nesne. Bu örnekte, varsayılan yer imi anahat düzeyini 1'e ve üst bilgi ve alt bilgi yer imi dışa aktarma modunu "İlk" olarak ayarladık.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## 4. Adım: Belgeyi üstbilgi ve altbilgi yer işaretleriyle birlikte PDF olarak kaydedin

Son olarak daha önce yapılandırdığımız kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET'i kullanarak bir belgedeki üstbilgi ve altbilgi yer imlerini başarıyla dışa aktardınız ve uygun yer imleriyle bir PDF oluşturdunuz.

### Aspose.Words for .NET ile üstbilgi ve altbilgi yer işaretlerini dışa aktarmak için örnek kaynak kodu

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

Bu eğitimde, Aspose.Words for .NET kullanarak üstbilgi ve altbilgi yer işaretlerini bir Word belgesinden bir PDF belgesine nasıl aktaracağımızı açıkladık. Dışa aktarılan yer imleri, oluşturulan PDF belgesinde kolay gezinmeye ve karşılık gelen üstbilgilere ve altbilgilere hızlı başvuru yapılmasına olanak tanır. Bir belgeden üst bilgi ve alt bilgi yer imlerini dışa aktarmak ve Aspose.Words for .NET'i kullanarak uygun yer imleriyle bir PDF oluşturmak için açıklanan adımları izleyin. Belgelerinizin doğru yolunu belirttiğinizden ve kaydetme seçeneklerini gerektiği gibi yapılandırdığınızdan emin olun.

### Sıkça Sorulan Sorular

### S: Üstbilgi ve altbilgi yer işaretlerini bir Word belgesinden PDF belgesine aktarma nedir?
C: Üstbilgi ve altbilgi yer imlerini Word belgesinden PDF belgesine aktarmak, PDF belgesinde üstbilgi ve altbilgilerden yer imleri tutmaya ve oluşturmaya yönelik bir özelliktir. Orijinal Word belgesinin altbilgileri. Bu, kullanıcıların üstbilgilere ve altbilgilere karşılık gelen yer işaretlerini kullanarak PDF belgesinde hızlı ve kolay bir şekilde gezinmesine olanak tanır.

### S: Aspose.Words for .NET'i kullanarak üstbilgi ve altbilgi yer imlerini bir Word belgesinden PDF belgesine nasıl aktarabilirim?
C: Aspose.Words for .NET kullanarak üstbilgi ve altbilgi yer imlerini bir Word belgesinden PDF belgesine aktarmak için şu adımları izleyin:

 Belgelerinizin bulunduğu dizin yolunu değiştirerek ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

 İşlemek istediğiniz belgeyi kullanarak yükleyin.`Document` sınıfını seçin ve belirtilen belgeler dizinindeki Word belgesinin yolunu belirtin.

 Bir örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıf ve uygun üstbilgi ve altbilgi yer imi seçeneklerini ayarlama.

 Belgeyi kullanarak PDF formatında kaydedin.`Save` yöntemi`Document`yolu ve kaydetme seçeneklerini belirten sınıf.

### S: Üstbilgi ve altbilgi yer işaretlerini PDF belgesine aktarmanın faydaları nelerdir?
C: Üstbilgi ve altbilgi yer imlerini PDF belgesine aktarmanın avantajları şunlardır:

Kolay Gezinme: Yer imleri, kullanıcıların belirli üstbilgilere ve altbilgilere başvurarak bir PDF belgesinde kolayca gezinmesine olanak tanır.

Hızlı Başvuru: Yer imleri, kullanıcıların PDF belgesinin üstbilgi ve altbilgilerine göre ilgili bölümlerini hızlı bir şekilde bulmasına olanak tanır.
---
title: Üst Bilgi Alt Bilgi Yer İşaretlerini Dışa Aktar
linktitle: Üst Bilgi Alt Bilgi Yer İşaretlerini Dışa Aktar
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile üstbilgi ve altbilgi yer imlerini dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Bu makale, Üst Bilgi ve Alt Bilgi Yer İmlerini Dışa Aktar özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgenin üst bilgilerinden ve alt bilgilerinden yer imlerini nasıl dışa aktaracağınızı ve uygun yer imleriyle bir PDF oluşturmayı öğrenebileceksiniz.

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

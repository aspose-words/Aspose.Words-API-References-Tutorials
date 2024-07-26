---
title: Word Belgesi Üst Bilgisi Alt Bilgisi Yer İmlerini PDF Belgesine Dışa Aktarma
linktitle: Word Belgesi Üst Bilgisi Alt Bilgisi Yer İmlerini PDF Belgesine Dışa Aktarma
second_title: Aspose.Words Belge İşleme API'si
description: Adım adım kılavuzumuzla Aspose.Words for .NET kullanarak üst bilgi ve alt bilgi yer işaretlerini bir Word belgesinden PDF'ye nasıl aktaracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---
## giriiş

Word belgelerini PDF'ye dönüştürmek, özellikle belgeleri biçimlerini koruyarak paylaşmak veya arşivlemek istediğinizde yaygın bir iştir. Bazen bu belgelerin üstbilgileri ve altbilgileri içinde önemli yer imleri bulunur. Bu eğitimde, bu yer işaretlerini Aspose.Words for .NET kullanarak bir Word belgesinden PDF'ye aktarma sürecini anlatacağız.

## Önkoşullar

Dalışa geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Geliştirme ortamınızı ayarlayın. Visual Studio'yu veya herhangi bir .NET uyumlu IDE'yi kullanabilirsiniz.
- Temel C# Bilgisi: Kod örneklerini takip etmek için C# programlamaya aşinalık gerekir.

## Ad Alanlarını İçe Aktar

Öncelikle C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu satırları kod dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Süreci takip edilmesi kolay adımlara ayıralım.

## 1. Adım: Belgeyi Başlatın

İlk adım Word belgenizi yüklemektir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

Bu adımda, belge dizininizin yolunu belirtmeniz ve Word belgesini yüklemeniz yeterlidir.

## 2. Adım: PDF Kaydetme Seçeneklerini Yapılandırın

Daha sonra, üstbilgi ve altbilgilerdeki yer işaretlerinin doğru şekilde dışa aktarıldığından emin olmak için PDF kaydetme seçeneklerini yapılandırmanız gerekir.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

 Burada kurulumu yapıyoruz.`PdfSaveOptions` .`DefaultBookmarksOutlineLevel` özelliği, yer imlerinin anahat düzeyini ayarlar ve`HeaderFooterBookmarksExportMode` özelliği, yer işaretlerinin üstbilgi ve altbilgilerde yalnızca ilk geçtiği yerin dışa aktarılmasını sağlar.

## 3. Adım: Belgeyi PDF olarak kaydedin

Son olarak, yapılandırılmış seçeneklerle belgenizi PDF olarak kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Bu adımda, yapılandırdığınız seçeneklerle belgeyi belirtilen yola kaydediyorsunuz.

## Çözüm

İşte buyur! Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak bir Word belgesinin üstbilgi ve altbilgilerindeki yer işaretlerini kolayca PDF'ye aktarabilirsiniz. Bu yöntem, belgenizdeki önemli gezinme yardımcılarının PDF formatında korunmasını sağlayarak okuyucuların belgenizde gezinmesini kolaylaştırır.

## SSS'ler

### Word belgesindeki tüm yer imlerini PDF'ye aktarabilir miyim?

 Evet yapabilirsin. İçinde`PdfSaveOptions`gerekiyorsa ayarları tüm yer işaretlerini içerecek şekilde ayarlayabilirsiniz.

### Yer işaretlerini belgenin gövdesinden de dışa aktarmak istersem ne olur?

 Yapılandırabilirsiniz`OutlineOptions` içinde`PdfSaveOptions` belgenin gövdesinden yer imleri eklemek için.

### PDF'deki yer imi düzeylerini özelleştirmek mümkün mü?

 Kesinlikle! özelleştirebilirsiniz`DefaultBookmarksOutlineLevel` Yer işaretleriniz için farklı anahat düzeyleri ayarlama özelliği.

### Yer imi olmayan belgeleri nasıl işleyebilirim?

Belgenizde yer işareti yoksa PDF, yer işareti taslağı olmadan oluşturulur. PDF'de bunlara ihtiyacınız varsa belgenizin yer imleri içerdiğinden emin olun.

### Bu yöntemi DOCX veya RTF gibi diğer belge türleri için kullanabilir miyim?

Evet, Aspose.Words for .NET, DOCX, RTF ve diğerleri dahil olmak üzere çeşitli belge türlerini destekler.
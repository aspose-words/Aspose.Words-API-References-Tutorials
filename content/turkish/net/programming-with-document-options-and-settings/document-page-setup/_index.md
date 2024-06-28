---
title: Belge Sayfası Düzeni
linktitle: Belge Sayfası Düzeni
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belge düzeni oluşturmaya yönelik adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/document-page-setup/
---

Bu eğitimde, Aspose.Words for .NET ile belge düzenini yapılandırmak için C# kaynak kodunu size anlatacağız. Bu özellik, düzen modunu, satır başına karakter sayısını ve sayfa başına satır sayısını ayarlamanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda yapılandırmak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Düzeni ayarlama

Şimdi belge düzenini yapılandıralım. Düzen modunu, satır başına karakter sayısını ve sayfa başına satır sayısını ayarlamak için aşağıdaki kodu kullanın:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Bu kod, düzen modunu "Izgara" olarak ayarlar ve ardından satır başına karakter sayısını ve sayfa başına satır sayısını belirtir.

### Aspose.Words for .NET kullanılarak Belge Sayfası Kurulumu için örnek kaynak kodu


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Belge ızgara davranışını tanımlamaya izin veren bir bölüm için düzen modunu ayarlayın.
	// Belge Izgarası sekmesinin MS Word'ün Sayfa Yapısı iletişim kutusunda görünür hale geldiğini unutmayın.
	// Herhangi bir Asya dili düzenleme dili olarak tanımlanmışsa.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgenin düzenini nasıl yapılandıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek kendi belgelerinizin düzenini kolayca özelleştirebilirsiniz.
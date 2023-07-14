---
title: Üstbilgilere Taşı Altbilgiler
linktitle: Üstbilgilere Taşı Altbilgiler
second_title: Aspose.Words Belge İşleme API'sı
description: Bu adım adım kılavuz ile Word belgelerinde üst bilgiler ve alt bilgilerde gezinmek ve bunları değiştirmek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-headers-footers/
---

Bu örnekte, Aspose.Words for .NET'in Üst Bilgilere Alt Bilgilere Taşı özelliğini inceleyeceğiz. Aspose.Words, geliştiricilerin Word belgelerini program aracılığıyla oluşturmasına, değiştirmesine ve dönüştürmesine olanak sağlayan güçlü bir belge işleme kitaplığıdır. Üstbilgilere/Altbilgilere Taşı özelliği, bir belge içindeki farklı üstbilgilere ve altbilgilere gitmemizi ve bunlara içerik eklememizi sağlar.

Aspose.Words for .NET kullanarak Üstbilgilere/Altbilgilere Taşı özelliğinin nasıl kullanılacağını anlamak için kaynak kodunu adım adım inceleyelim.



## 1. Adım: Belge ve belge oluşturucuyu başlatma

Önce Document ve DocumentBuilder nesnelerini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Üst bilgileri ve alt bilgileri yapılandırma

Belge için üstbilgi/altbilgi ayarlarını belirtin. Bu örnekte, üst bilgileri ve alt bilgileri ilk sayfa ve tek/çift sayfalar için farklı olacak şekilde ayarladık:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## 3. Adım: Farklı sayfalar için başlıklar oluşturma

Her başlık türüne gidin ve bunlara içerik ekleyin. Bu örnekte, ilk sayfa, çift sayfalar ve diğer tüm sayfalar için başlıklar oluşturuyoruz:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## 4. Adım: Belgede sayfalar oluşturma
Birden çok sayfa oluşturmak için belgeye içerik ekleyin. Örneğin:

```csharp
// Belgede iki sayfa oluşturun.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## 5. Adım: Belgeyi kaydetme

Değiştirilen belgeyi istediğiniz bir konuma kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Uygun dosya yolunu ve biçimini (ör. DOCX) belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Üst Bilgilere/Alt Bilgilere Taşı için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İlk, çift ve tek sayfalar için farklı üstbilgiler ve altbilgiler istediğimizi belirtin.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Başlıkları oluşturun.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Belgede iki sayfa oluşturun.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

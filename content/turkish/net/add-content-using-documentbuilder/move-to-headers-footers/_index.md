---
title: Word Belgesinde Üstbilgi Altbilgilere Taşı
linktitle: Word Belgesinde Üstbilgi Altbilgilere Taşı
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

//İlk, çift ve tek sayfalar için farklı üstbilgiler ve altbilgiler istediğimizi belirtin.
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

## Çözüm

Bu örnekte, Aspose.Words for .NET'in Üst Bilgilere/Alt Bilgilere Taşı özelliğini inceledik. DocumentBuilder sınıfını kullanarak bir Word belgesinde farklı üstbilgilere ve altbilgilere nasıl gidileceğini ve bunlara içerik ekleneceğini öğrendik. Bu özellik, geliştiricilerin üstbilgileri ve altbilgileri belirli sayfalar veya bölümler için özelleştirmesine olanak tanıyarak profesyonel ve yapılandırılmış belgeler oluşturmada esneklik sağlar. Aspose.Words for .NET, Word belgelerini program aracılığıyla manipüle etmek için güçlü bir araç seti sağlar ve bu da onu belge işleme uygulamaları için temel bir kitaplık haline getirir.

### Word belgesinde üstbilgi altbilgilerine geçiş için SSS

#### S: Aspose.Words for .NET'teki Üst Bilgilere/Alt Bilgilere Taşı özelliğinin amacı nedir?

C: Aspose.Words for .NET'teki Üstbilgilere/Altbilgilere Taşı özelliği, geliştiricilerin bir Word belgesi içindeki farklı üstbilgilere ve altbilgilere gitmesine ve bunlara program aracılığıyla içerik eklemesine olanak tanır. Belgedeki farklı sayfalar veya bölümler için üst bilgileri ve alt bilgileri özelleştirmeniz gerektiğinde kullanışlıdır.

#### S: Belgedeki farklı sayfalar için farklı üstbilgiler ve altbilgiler alabilir miyim?

C: Evet, sırasıyla PageSetup.DifferentFirstPageHeaderFooter ve PageSetup.OddAndEvenPagesHeaderFooter özelliklerini kullanarak ilk sayfa, çift sayfalar ve tek sayfalar için farklı üst bilgiler ve alt bilgiler belirtebilirsiniz.

#### S: Belirli üstbilgilere ve altbilgilere nasıl içerik ekleyebilirim?

Y: Belirli üstbilgilere ve altbilgilere içerik eklemek için DocumentBuilder sınıfının MoveToHeaderFooter yöntemini kullanın. Gereksiniminize göre HeaderFirst, HeaderEven ve HeaderPrimary üstbilgilerine veya FooterFirst, FooterEven ve FooterPrimary altbilgilerine gidebilirsiniz.

#### S: Belgedeki belirli bir bölüm için üst bilgiler ve alt bilgiler oluşturabilir miyim?

Y: Evet, DocumentBuilder sınıfının MoveToSection yöntemini kullanarak belgede belirli bir bölüme gidebilir ve ardından bu bölümde üst bilgiler ve alt bilgiler oluşturabilirsiniz.

#### S: Değiştirilen belgeyi Aspose.Words for .NET kullanarak bir dosyaya nasıl kaydedebilirim?

A: Değiştirilen belgeyi, Document sınıfının Save yöntemini kullanarak istediğiniz bir konuma ve formata kaydedebilirsiniz. Uygun dosya yolunu ve dosya biçimini (ör. DOCX) belirttiğinizden emin olun.
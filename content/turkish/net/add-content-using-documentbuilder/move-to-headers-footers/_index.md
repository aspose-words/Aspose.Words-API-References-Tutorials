---
title: Word Belgesinde Üst Bilgilere Alt Bilgilere Taşı
linktitle: Word Belgesinde Üst Bilgilere Alt Bilgilere Taşı
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET'i kullanarak Word belgelerinde üstbilgi ve altbilgilerde gezinmeyi ve bunları değiştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-headers-footers/
---
Bu örnekte Aspose.Words for .NET'in Başlıklara Alt Bilgilere Taşı özelliğini inceleyeceğiz. Aspose.Words, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir belge işleme kitaplığıdır. Üstbilgilere/Altbilgilere Taşı özelliği, bir belgedeki farklı üstbilgilere ve altbilgilere gitmemize ve bunlara içerik eklememize olanak tanır.

Aspose.Words for .NET kullanarak Üst Bilgilere/Alt Bilgilere Taşı özelliğinin nasıl kullanılacağını anlamak için kaynak kodunu adım adım inceleyelim.

## 1. Adım: Belgeyi ve belge oluşturucuyu başlatma

Öncelikle Document ve DocumentBuilder nesnelerini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Üstbilgileri ve altbilgileri yapılandırma

Belgenin üstbilgi/altbilgi ayarlarını belirtin. Bu örnekte, üstbilgi ve altbilgileri ilk sayfa ve tek/çift sayfalar için farklı olacak şekilde ayarladık:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## 3. Adım: Farklı sayfalar için başlıklar oluşturma

Her başlık türüne gidin ve bunlara içerik ekleyin. Bu örnekte ilk sayfa, çift sayfalar ve diğer tüm sayfalar için başlıklar oluşturuyoruz:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## 4. Adım: Belgede sayfalar oluşturma
Birden fazla sayfa oluşturmak için belgeye içerik ekleyin. Örneğin:

```csharp
// Belgede iki sayfa oluşturun.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Adım 5: Belgeyi kaydetme

Değiştirilen belgeyi istediğiniz konuma kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Uygun dosya yolunu ve formatını (örn. DOCX) belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Üst Bilgilere/Alt Bilgilere Taşı için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//İlk, çift ve tek sayfalar için üstbilgi ve altbilgilerin farklı olmasını istediğimizi belirtin.
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

Bu örnekte Aspose.Words for .NET'in Üst Bilgilere/Alt Bilgilere Taşı özelliğini inceledik. DocumentBuilder sınıfını kullanarak bir Word belgesindeki farklı üstbilgilere ve altbilgilere nasıl gezineceğimizi ve bunlara nasıl içerik ekleyeceğimizi öğrendik. Bu özellik, geliştiricilerin belirli sayfalar veya bölümler için üstbilgileri ve altbilgileri özelleştirmesine olanak tanıyarak profesyonel ve yapılandırılmış belgeler oluşturmada esneklik sağlar. Aspose.Words for .NET, Word belgelerinin programlı olarak işlenmesi için güçlü bir araç seti sağlar ve bu da onu belge işleme uygulamaları için önemli bir kütüphane haline getirir.

### Word belgesindeki üstbilgi altbilgilerine geçişle ilgili SSS'ler

#### S: Aspose.Words for .NET'teki Üst Bilgilere/Alt Bilgilere Taşı özelliğinin amacı nedir?

C: Aspose.Words for .NET'teki Üstbilgilere/Altbilgilere Taşı özelliği, geliştiricilerin bir Word belgesi içindeki farklı üstbilgilere ve altbilgilere gitmesine ve bunlara programlı olarak içerik eklemesine olanak tanır. Belgedeki farklı sayfalar veya bölümler için üstbilgileri ve altbilgileri özelleştirmeniz gerektiğinde kullanışlıdır.

#### S: Belgedeki farklı sayfalar için farklı üstbilgi ve altbilgilere sahip olabilir miyim?

C: Evet, sırasıyla PageSetup.DifferentFirstPageHeaderFooter ve PageSetup.OddAndEvenPagesHeaderFooter özelliklerini kullanarak ilk sayfa, çift sayfalar ve tek sayfalar için farklı üstbilgiler ve altbilgiler belirtebilirsiniz.

#### S: Belirli üstbilgilere ve altbilgilere nasıl içerik ekleyebilirim?

C: Belirli üstbilgilere ve altbilgilere içerik eklemek için DocumentBuilder sınıfının MoveToHeaderFooter yöntemini kullanın. Gereksiniminize bağlı olarak HeaderFirst, HeaderEven ve HeaderPrimary üstbilgilerine veya FooterFirst, FooterEven ve FooterPrimary altbilgilerine gidebilirsiniz.

#### S: Belgedeki belirli bir bölüm için üstbilgi ve altbilgi oluşturabilir miyim?

C: Evet, belgedeki belirli bir bölüme gitmek ve ardından o bölüm içinde üstbilgiler ve altbilgiler oluşturmak için DocumentBuilder sınıfının MoveToSection yöntemini kullanabilirsiniz.

#### S: Değiştirilen belgeyi Aspose.Words for .NET kullanarak bir dosyaya nasıl kaydedebilirim?

C: Değiştirilen belgeyi, Document sınıfının Save yöntemini kullanarak istediğiniz konuma ve formata kaydedebilirsiniz. Uygun dosya yolunu ve dosya biçimini (örn. DOCX) belirttiğinizden emin olun.
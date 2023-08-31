---
title: Set metni Başlığı
linktitle: Set metni Başlığı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belgelerinizi formatlamak için Setext başlıklarını nasıl kullanacağınızı öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/setext-heading/
---

Bu eğitimde, Setext Heading özelliğinin Aspose.Words for .NET ile nasıl kullanılacağı konusunda size yol göstereceğiz. Setext Başlığı, Markdown belgelerinde başlıkları biçimlendirmenin alternatif bir yöntemidir.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Adım 2: Setext başlık stilini kullanma

Belgemizde 1. düzey başlık oluşturmak için varsayılan "Başlık 1" paragraf stilini kullanacağız.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 3. Adım: Stilleri Sıfırlama

Paragraflar arasında istenmeyen stil kombinasyonlarını önlemek için önceden uygulanmış yazı tipi stillerini sıfırladık.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Adım 4: Setext Başlık Düzeylerini Özelleştirme

Mevcut başlık stillerine dayalı olarak yeni paragraf stilleri ekleyerek Setext başlık seviyelerini özelleştirebiliriz. Bu örnekte, Setext formatındaki 1. düzey başlığı temsil etmek için "Başlık 1" stilini temel alan bir "SetextHeading1" stili oluşturuyoruz.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Adım 5: Belgeyi kaydetme

Son olarak belgeyi istediğimiz formatta kaydedebiliriz.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Aspose.Words for .NET ile Setext başlıkları için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Paragraflar arasında stilleri birleştirmemek için önceki paragraftaki stilleri sıfırlayın.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Paragraflar arasında stilleri birleştirmemek için önceki paragraftaki stilleri sıfırlayın.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Temel paragrafın Başlık düzeyi 2'den büyükse Setex başlık düzeyi 2'ye sıfırlanacaktır.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### SSS'ler

#### S: Setext Markdown başlığı nedir?

C: Setext Markdown başlığı, Markdown belgesinde başlıklar oluşturmanın alternatif bir yoludur. Farklı başlık düzeylerini belirtmek için alt çizgi karakterlerini (= veya -) kullanır.

#### S: Setext Markdown başlıkları nasıl kullanılır?

C: Setext Markdown başlıklarını kullanmak için başlık metninin altına alt çizgiler yerleştirin. 1. düzey başlık için eşittir işaretini (=) ve 2. düzey başlık için kısa çizgileri (-) kullanın.

#### S: Setext Markdown başlıklarının kullanımında herhangi bir sınırlama var mı?

C: Setext Markdown başlıklarının, başlık hiyerarşisi açısından sınırlamaları vardır ve görsel olarak standart Markdown başlıkları kadar belirgin değildir.

#### S: Setext Markdown başlıklarının görünümünü özelleştirebilir miyim?

C: Standart Markdown'da Setext Markdown başlıklarının görünümünü özelleştirmek mümkün değildir. Kullanılan alt çizgi karakterlerine göre önceden tanımlanmış bir görünüme sahiptirler.

#### S: Setext Markdown başlıkları tüm Markdown editörleri tarafından destekleniyor mu?

C: Setext Markdown başlıkları desteği, Markdown editörleri arasında farklılık gösterebilir. Emin olmak için yayıncınızın özel belgelerini kontrol edin.
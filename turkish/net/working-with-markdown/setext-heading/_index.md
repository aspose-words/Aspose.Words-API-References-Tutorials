---
title: Metin Başlığı
linktitle: Metin Başlığı
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET Adım adım kılavuz ile belgelerinizi biçimlendirmek için Setext başlıklarını nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/setext-heading/
---

Bu öğreticide, Setex Heading özelliğini Aspose.Words for .NET ile nasıl kullanacağınız konusunda size yol göstereceğiz. Setex Heading, Markdown belgelerinde başlıkları biçimlendirmenin alternatif bir yöntemidir.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Setex başlık stilini kullanma

Belgemizde 1. düzey bir başlık oluşturmak için varsayılan "Başlık 1" paragraf stilini kullanacağız.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## 3. Adım: Stilleri Sıfırlama

Paragraflar arasında istenmeyen stil kombinasyonlarını önlemek için önceden uygulanan yazı tipi stillerini sıfırladık.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Adım 4: Settext Başlık Düzeylerini Özelleştirme

Mevcut başlık stillerine dayalı olarak yeni paragraf stilleri ekleyerek Setex başlık düzeylerini özelleştirebiliriz. Bu örnekte, Setext formatında 1. seviye bir başlığı temsil etmek için "Başlık 1" stilini temel alan bir "SetextHeading1" stili oluşturuyoruz.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## 5. Adım: Belgeyi kaydetme

Son olarak belgeyi istediğimiz formatta kaydedebiliriz.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Aspose.Words for .NET ile Setext başlıkları için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
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

### SSS

#### S: Setext Markdown başlığı nedir?

Y: Setex Markdown başlığı, Markdown belgesinde başlıklar oluşturmanın alternatif bir yoludur. Farklı başlık düzeylerini belirtmek için alt çizgi karakterleri (= veya -) kullanır.

#### S: Setext Markdown başlıkları nasıl kullanılır?

C: Setex Markdown başlıklarını kullanmak için, başlık metninin altına alt çizgi koyun. 1. düzey başlık için eşittir işaretleri (=) ve 2. düzey başlık için kısa çizgiler (-) kullanın.

#### S: Setext Markdown başlıklarının kullanımında herhangi bir sınırlama var mı?

Y: Setex Markdown başlıkları, başlık hiyerarşisi açısından sınırlamalara sahiptir ve standart Markdown başlıkları kadar görsel olarak farklı değildir.

#### S: Setex Markdown başlıklarının görünümünü özelleştirebilir miyim?

C: Standart Markdown'da Setex Markdown başlıklarının görünümünü özelleştirmek mümkün değildir. Kullanılan alt çizgi karakterlerine göre önceden tanımlanmış bir görünüme sahiptirler.

#### S: Setex Markdown başlıkları tüm Markdown editörleri tarafından destekleniyor mu?

Y: Setex Markdown başlıkları desteği, Markdown editörleri arasında değişiklik gösterebilir. Emin olmak için yayıncınızın özel belgelerini kontrol edin.
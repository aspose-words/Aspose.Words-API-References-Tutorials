---
title: Word Belgesine İçindekiler Tablosu Ekleme
linktitle: Word Belgesine İçindekiler Tablosu Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerine içindekiler tablosunu nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine içindekiler tablosunu nasıl ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, uygun başlıklara ve sayfa numaralarına sahip bir içindekiler tablosu oluşturabileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Bir İçindekiler Tablosu Ekleyin
Ardından, bir içindekiler tablosu eklemek için DocumentBuilder sınıfının InsertTableOfContents yöntemini kullanın. Yöntem içinde gerekli biçimlendirme seçeneklerini belirtin:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 3. Adım: Belge İçeriği Ekleyin
İçindekiler tablosunu ekledikten sonra asıl belge içeriğini ekleyin. StyleIdentifier'ı kullanarak uygun başlık stillerini ayarlayın:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## 4. Adım: İçindekiler Tablosunu Güncelleyin
Yeni eklenen içindekiler tablosu başlangıçta boş olacaktır. Doldurmak için belgedeki alanları güncelleyin:

```csharp
doc.UpdateFields();
```

## 5. Adım: Belgeyi Kaydedin
İçindekiler tablosunu ekledikten ve alanları güncelledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Aspose.Words for .NET kullanarak İçindekiler Tablosu Ekleme için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir içindekiler tablosu eklemek için eksiksiz kaynak kodu burada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// DocumentBuilder'ı Document nesnesiyle başlat
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İçindekiler tablosu eklea
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Asıl belge içeriğini ikinci sayfada başlatın.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Yeni eklenen içindekiler tablosu başlangıçta boş olacaktır.
// Belgedeki alanlar güncellenerek doldurulması gerekir.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Çözüm

Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine içindekiler tablosunu nasıl ekleyeceğinizi başarıyla öğrendiniz. Bu adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık belgeleriniz için uygun başlıklara ve sayfa numaralarına sahip bir içindekiler tablosu oluşturabilirsiniz.

### Word belgesine içindekiler tablosu eklemek için SSS

#### S: İçindekiler tablosunun görünümünü özelleştirebilir miyim?

 Y: Evet, içinde belirtilen biçimlendirme seçeneklerini değiştirerek içindekiler tablosunun görünümünü özelleştirebilirsiniz.`InsertTableOfContents` yöntem. Parametreler, sayfa numaralarını, girintiyi ve diğer stilleri kontrol etmenizi sağlar.

#### S: İçindekiler tablosuna belirli başlık düzeylerini dahil etmek istersem ne olur?

 C: İçindekiler tablosuna dahil edilmesini istediğiniz başlık düzeylerini, içindeki değeri ayarlayarak belirleyebilirsiniz.`InsertTableOfContents` yöntem. Örneğin, kullanarak`"\\o \"1-3\""` 1'den 3'e kadar olan başlık seviyelerini içerecektir.

#### S: Belge içeriğinde değişiklik yaparsam içindekiler tablosunu otomatik olarak güncelleyebilir miyim?

 C: Evet, içindekileri arayarak otomatik olarak güncelleyebilirsiniz.`UpdateFields` belge üzerindeki yöntem. Bu, başlık ekleme veya çıkarma gibi belge içeriğinde yapılan değişikliklerin içindekiler tablosuna yansıtılmasını sağlayacaktır.

#### S: İçindekiler tablosundaki başlık düzeylerini nasıl farklı şekilde biçimlendirebilirim?

 C: Her başlık düzeyi için farklı paragraf stilleri kullanarak başlık düzeylerine farklı stil verebilirsiniz. Farklı atayarak`StyleIdentifier` değerleri`ParagraphFormat` arasında`DocumentBuilder`, her başlık düzeyi için farklı stiller oluşturabilirsiniz.

#### S: İçindekiler tablosundaki başlıklara ek biçimlendirme eklemek mümkün müdür?

 C: Evet, içindekiler tablosundaki başlıklara yazı tipi stilleri, renkler veya diğer özellikler gibi ek biçimlendirmeler ekleyebilirsiniz. ayarlayarak`Font` özellikleri`DocumentBuilder`, başlıklara özel biçimlendirme uygulayabilirsiniz.
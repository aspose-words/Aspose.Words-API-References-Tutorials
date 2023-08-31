---
title: Word Belgesine İçindekiler Tablosu Ekleme
linktitle: Word Belgesine İçindekiler Tablosu Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine nasıl içindekiler tablosu ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Bu kapsamlı eğitimde Aspose.Words for .NET'i kullanarak bir Word belgesine içindekiler tablosunu nasıl ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, uygun başlıklara ve sayfa numaralarına sahip bir içindekiler tablosu oluşturabileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesini başlatın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: İçindekiler Tablosu Ekleyin
Daha sonra içindekiler tablosu eklemek için DocumentBuilder sınıfının InsertTableOfContents yöntemini kullanın. Yöntem içinde gerekli biçimlendirme seçeneklerini belirtin:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 3. Adım: Belge İçeriğini Ekleyin
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

## Adım 5: Belgeyi Kaydedin
İçindekiler tablosunu ekledikten ve alanları güncelledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Aspose.Words for .NET kullanarak İçindekiler Tablosu Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak içindekiler tablosu eklemek için gereken kaynak kodun tamamı burada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// DocumentBuilder'ı Document nesnesiyle başlat
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İçerik tablosu eklea
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Asıl belge içeriğini ikinci sayfadan başlatın.
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
// Dokümandaki alanlar güncellenerek doldurulması gerekmektedir.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine içindekiler tablosunu nasıl ekleyeceğinizi başarıyla öğrendiniz. Bu adım adım kılavuzu izleyerek ve verilen kaynak kodunu kullanarak artık belgeleriniz için uygun başlıklara ve sayfa numaralarına sahip bir içindekiler tablosu oluşturabilirsiniz.

### Word belgesine içindekiler tablosu eklemek için SSS'ler

#### S: İçindekiler tablosunun görünümünü özelleştirebilir miyim?

 C: Evet, içindekiler tablosunun görünümünü, belirtilen biçimlendirme seçeneklerini değiştirerek özelleştirebilirsiniz.`InsertTableOfContents` yöntem. Parametreler sayfa numaralarını, girintiyi ve diğer stilleri kontrol etmenize olanak tanır.

#### S: İçindekiler tablosuna belirli başlık düzeyleri eklemek istersem ne olur?

 C: İçindekiler tablosuna dahil edilecek istenen başlık düzeylerini, içindeki değeri ayarlayarak belirleyebilirsiniz.`InsertTableOfContents` yöntem. Örneğin, kullanarak`"\\o \"1-3\""` 1'den 3'e kadar olan başlık düzeylerini içerecektir.

#### S: Belge içeriğinde değişiklik yaparsam içindekiler tablosunu otomatik olarak güncelleyebilir miyim?

 C: Evet, içindekileri arayarak otomatik olarak güncelleyebilirsiniz.`UpdateFields` belgedeki yöntem. Bu, belge içeriğinde yapılan, başlık ekleme veya kaldırma gibi değişikliklerin içindekiler tablosuna yansıtılmasını sağlayacaktır.

#### S: İçindekiler tablosundaki başlık düzeylerini nasıl farklı şekilde stillendirebilirim?

 C: Her başlık düzeyi için farklı paragraf stilleri kullanarak başlık düzeylerini farklı biçimlendirebilirsiniz. Farklı atama yaparak`StyleIdentifier` değerleri`ParagraphFormat` arasında`DocumentBuilder`ile her başlık düzeyi için farklı stiller oluşturabilirsiniz.

#### S: İçindekiler bölümündeki başlıklara ek biçimlendirme eklemek mümkün müdür?

 C: Evet, içindekiler tablosundaki başlıklara yazı tipi stilleri, renkler veya diğer özellikler gibi ek biçimlendirmeler ekleyebilirsiniz. Ayarlayarak`Font` özellikleri`DocumentBuilder`başlıklara özel biçimlendirme uygulayabilirsiniz.
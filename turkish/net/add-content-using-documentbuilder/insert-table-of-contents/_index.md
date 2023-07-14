---
title: İçindekiler Tablosu Ekle
linktitle: İçindekiler Tablosu Ekle
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

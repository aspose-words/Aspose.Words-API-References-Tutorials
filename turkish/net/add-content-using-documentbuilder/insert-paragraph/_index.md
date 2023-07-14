---
title: Paragraf Ekle
linktitle: Paragraf Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerine biçimlendirilmiş paragraflar eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-paragraph/
---

Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine nasıl paragraf ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda belgelerinize biçimlendirilmiş paragraflar ekleyebileceksiniz.

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

## 2. Adım: Yazı Tipi ve Biçimlendirmeyi Ayarlayın
Ardından, sırasıyla Font ve ParagraphFormat nesnelerini kullanarak font özelliklerini ve paragraf biçimlendirmesini ayarlayın:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## 3. Adım: Bir Paragraf Ekleyin
Yazı tipini ve biçimlendirmeyi ayarladıktan sonra, tam bir paragraf eklemek için DocumentBuilder sınıfının Writeln yöntemini kullanın:

```csharp
builder.Writeln("A whole paragraph.");
```

## 4. Adım: Belgeyi Kaydedin
Paragrafı ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Aspose.Words for .NET kullanarak Paragraf Ekleme için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir paragraf eklemek için eksiksiz kaynak kodu burada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine biçimlendirilmiş paragrafların nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık belgelerinize belirli yazı tipleri, biçimlendirme ve hizalama ile özelleştirilmiş paragraflar ekleyebilirsiniz.
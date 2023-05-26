---
title: Onay Kutusu Türü İçerik Kontrolü
linktitle: Onay Kutusu Türü İçerik Kontrolü
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesinde Onay Kutusu Tipi İçerik Kontrolü oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/check-box-type-content-control/
---

Bu eğitim, Aspose.Words for .NET kullanılarak bir Word belgesinde Onay Kutusu Tipi İçerik Kontrolü'nün nasıl oluşturulacağını açıklar. Onay kutusu içeriği denetimleri, kullanıcıların belge içinde bir onay kutusunu seçmesine veya temizlemesine olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` Belgenin içeriğini oluşturmak için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir Onay Kutusu Türü İçerik Denetimi Ekleyin
 Oluşturmak`StructuredDocumentTag` ile`SdtType.Checkbox` onay kutusu içerik kontrolünü temsil etmek için. Belirtin`MarkupLevel.Inline` metnin içine yerleştirmek için

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## 4. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.CheckBoxTypeContentControl.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Aspose.Words for .NET kullanan Check Box Type Content Control için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde bir Onay Kutusu Tipi İçerik Kontrolü başarıyla oluşturdunuz.
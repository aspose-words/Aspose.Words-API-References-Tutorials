---
title: Onay Kutusu Türü İçerik Denetimi
linktitle: Onay Kutusu Türü İçerik Denetimi
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde Onay Kutusu Türü İçerik Denetiminin nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/check-box-type-content-control/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesinde Onay Kutusu Türü İçerik Kontrolü'nün nasıl oluşturulacağı açıklanmaktadır. Onay kutusu içerik kontrolleri, kullanıcıların belge içindeki bir onay kutusunu seçmesine veya işaretini kaldırmasına olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir Document ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` Belgenin içeriğini oluşturmak için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Onay Kutusu Türü İçerik Denetimi Ekleme
 Oluşturmak`StructuredDocumentTag` ile`SdtType.Checkbox` onay kutusu içerik kontrolünü temsil etmek için. Belirt`MarkupLevel.Inline` metnin içine yerleştirmek için.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Adım 4: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.CheckBoxTypeContentControl.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Aspose.Words for .NET kullanan Onay Kutusu Tipi İçerik Kontrolü için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde başarıyla bir Onay Kutusu Türü İçerik Kontrolü oluşturdunuz.
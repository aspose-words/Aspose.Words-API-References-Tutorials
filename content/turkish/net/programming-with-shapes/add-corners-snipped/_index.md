---
title: Kırpılmış Köşeleri Ekle
linktitle: Kırpılmış Köşeleri Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesine köşeleri kesilmiş bir şekli nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/add-corners-snipped/
---

 Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesine köşeleri kesilmiş bir şeklin nasıl ekleneceği açıklanmaktadır. Köşelerin kesilmiş şekli özelleştirilebilir ve kullanılarak eklenebilir.`InsertShape` yöntem.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 3: Kesilmiş Köşeleri Ekleme
 Kullan`InsertShape` yöntemi`DocumentBuilder` Köşeleri kesilmiş bir şekil eklemek için nesne. Şekil türünü belirtin (bu durumda,`ShapeType.TopCornersSnipped`) ve şekil için istenen boyutu sağlayın.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Adım 4: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.AddCornersSnipped.docx" olarak kaydediyoruz.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Aspose.Words for .NET kullanarak Alıntılanan Köşeleri Ekleme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenize başarıyla köşelerden kesilmiş bir şekil eklediniz.
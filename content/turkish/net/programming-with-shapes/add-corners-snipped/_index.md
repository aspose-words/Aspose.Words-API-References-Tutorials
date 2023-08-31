---
title: Kesilen Köşeleri Ekle
linktitle: Kesilen Köşeleri Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesine köşeleri kırpılmış bir şekli nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/add-corners-snipped/
---

 Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesine köşeleri kırpılmış bir şeklin nasıl ekleneceğini açıklar. Köşelerden kırpılmış şekil, kullanılarak özelleştirilebilir ve eklenebilir.`InsertShape` yöntem.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Kesilmiş Köşeler Şeklini Ekleyin
 Kullan`InsertShape` yöntemi`DocumentBuilder` köşeleri kırpılmış bir şekil eklemek için nesne. Şekil türünü belirtin (bu durumda,`ShapeType.TopCornersSnipped`) ve şekil için istenen boyutu sağlayın.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## 4. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.AddCornersSnipped.docx" olarak kaydediyoruz.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Aspose.Words for .NET kullanılarak Alıntı Alınmış Köşe Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenize köşelerden kesilmiş bir şekli başarıyla eklediniz.
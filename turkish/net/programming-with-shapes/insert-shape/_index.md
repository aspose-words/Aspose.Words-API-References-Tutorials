---
title: Şekil Ekle
linktitle: Şekil Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesine nasıl şekil ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/insert-shape/
---

Bu öğretici, Aspose.Words for .NET kullanarak bir Word belgesine şekillerin nasıl ekleneceğini açıklar. Şekiller, belgelerinizin görsel görünümünü ve düzenini geliştirmek için kullanılabilir.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Şekilleri Ekleyin
 Kullan`InsertShape` yöntemi`DocumentBuilder` belgeye şekiller eklemek için nesne. Şekil tipini, göreli yatay ve dikey konumları, sayfa boyutlarını, boyutunu ve sarma tipini belirtin. İsterseniz şekillerin dönüş açısını da ayarlayabilirsiniz.

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## 4. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.InsertShape.docx" olarak kaydediyoruz.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### Aspose.Words for .NET kullanan Insert Shape için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenize şekilleri başarıyla eklediniz.
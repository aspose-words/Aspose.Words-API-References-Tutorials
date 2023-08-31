---
title: Şekil Ekle
linktitle: Şekil Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesine nasıl şekil ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/insert-shape/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesine nasıl şekil ekleneceği açıklanmaktadır. Şekiller, belgelerinizin görsel görünümünü ve düzenini geliştirmek için kullanılabilir.

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

## 3. Adım: Şekilleri Ekleme
 Kullan`InsertShape` yöntemi`DocumentBuilder` Belgeye şekiller eklemek için nesne. Şekil türünü, göreli yatay ve dikey konumları, sayfa boyutlarını, boyutunu ve sarma türünü belirtin. İsterseniz şekillerin dönüş açısını da ayarlayabilirsiniz.

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## Adım 4: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.InsertShape.docx" olarak kaydediyoruz.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### Aspose.Words for .NET kullanarak Şekil Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenize başarıyla şekiller eklediniz.
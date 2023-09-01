---
title: Grup Şekli Ekle
linktitle: Grup Şekli Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesine birden fazla şekle sahip bir grup şeklini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/add-group-shape/
---

Bu eğitimde Aspose.Words for .NET kullanılarak birden fazla şekil içeren bir grup şeklinin bir Word belgesine nasıl ekleneceği açıklanmaktadır. Grup şekilleri, birden çok şekli tek bir varlık olarak birleştirmenize ve değiştirmenize olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve GroupShape Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve`GroupShape` belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Adım 3: GroupShape'e Şekiller Oluşturun ve Ekleyin
 Gibi bireysel şekiller oluşturun`accentBorderShape` Ve`actionButtonShape` kullanmak`Shape` sınıf. Özelliklerini istediğiniz gibi özelleştirin. Bu şekilleri şuraya ekleyin:`groupShape` nesne.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Adım 4: GroupShape için Boyutları Ayarlayın
 Genişliği, yüksekliği ve koordinat boyutunu ayarlayın.`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Adım 5: GroupShape'i Belgeye Ekleme
 Oluşturmak`DocumentBuilder` nesneyi ekleyin ve`groupShape` kullanarak belgeye ekleyin.`InsertNode` yöntem.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Adım 6: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save`yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.AddGroupShape.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Aspose.Words for .NET kullanarak Grup Şekli Ekleme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Bu kadar! Aspose.W kullanarak Word belgenize birden fazla şekil içeren bir grup şeklini başarıyla eklediniz.
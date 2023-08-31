---
title: Grup Şekli Ekle
linktitle: Grup Şekli Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesine birden çok şekle sahip bir grup şekli eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/add-group-shape/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesine birden çok şekil içeren bir grup şeklinin nasıl ekleneceğini açıklar. Grup şekilleri, birden çok şekli tek bir varlık olarak birleştirmenize ve değiştirmenize olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve GroupShape Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve`GroupShape` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## 3. Adım: GroupShape'e Şekiller Oluşturun ve Ekleyin
 gibi bireysel şekiller oluşturun.`accentBorderShape` Ve`actionButtonShape` kullanmak`Shape` sınıf. Özelliklerini istediğiniz gibi özelleştirin. Bu şekilleri şuraya ekleyin:`groupShape` nesne.

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

## 4. Adım: GroupShape için Boyutları Ayarlayın
 için genişlik, yükseklik ve koordinat boyutunu ayarlayın.`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Adım 5: GroupShape'i Belgeye Ekleyin
 Oluşturmak`DocumentBuilder` nesne ve eklemek`groupShape` kullanarak belgeye`InsertNode` yöntem.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## 6. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save`yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.AddGroupShape.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Aspose.Words for .NET kullanarak Add Group Shape için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
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

Bu kadar! Aspose.W'yi kullanarak birden fazla şekil içeren bir grup şeklini Word belgenize başarıyla eklediniz.
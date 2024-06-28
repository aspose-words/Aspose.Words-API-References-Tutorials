---
title: Şekil Revizyonu
linktitle: Şekil Revizyonu
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki şekilleri gözden geçirin.
type: docs
weight: 10
url: /tr/net/working-with-revisions/shape-revision/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki şekillerde nasıl revizyonlar yapabileceğiniz konusunda size yol göstereceğiz. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi oluşturma ve şekiller ekleme

İlk adım, yeni bir belge oluşturmak ve şekiller eklemektir.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 2. Adım: Düzeltmeleri takip edin ve başka bir şekil ekleyin

Revizyon takibini açıp başka bir şekil ekleyeceğiz.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Adım 3: Şekil koleksiyonunu alın ve düzeltmeleri kontrol edin.

Belgeden şekil koleksiyonunu alacağız ve her şekille ilişkili düzeltmeleri kontrol edeceğiz.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Adım 4: Şekil Taşıma Revizyonlarını Kontrol Etme

Şekil değiştirme revizyonlarını içeren mevcut bir belgeyi yükleyeceğiz ve ilgili revizyonları kontrol edeceğiz.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Aspose.Words for .NET kullanılarak Şekil Revizyonu için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgedeki şekillerde revizyonlar yapmak için gereken kaynak kodun tamamı burada:

```csharp
Document doc = new Document();

//Düzeltmeleri izlemeden satır içi şekil ekleyin.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Düzeltmeleri izlemeye başlayın ve ardından başka bir şekil ekleyin.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Yalnızca eklediğimiz iki şekli içeren belgenin şekil koleksiyonunu edinin.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// İlk şekli kaldırın.
shapes[0].Remove();

// Değişiklikler izlenirken bu şekli kaldırdığımız için şekil, düzeltme silme işlemi olarak sayılır.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Değişiklikleri izlerken başka bir şekil ekledik, böylece bu şekil bir ekleme revizyonu olarak sayılacaktır.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Belgede taşınan bir şekil var ancak şekil taşıma düzeltmelerinde bu şeklin iki örneği olacak.
// Biri vardığı yerdeki şekil, diğeri ise orijinal konumundaki şekil olacaktır.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Bu, revizyona geçiştir, aynı zamanda varış noktasındaki şekildir.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Bu, orijinal konumundaki şekil olan revizyondan harekettir.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki şekillerde revizyonların nasıl yapılacağını öğrendik. Doküman oluşturma, revizyon takibini etkinleştirme, her şekle ilişkin revizyonları kontrol etme ve şekilleri taşımak için revizyonları kontrol etme adımlarını takip ederek revizyonları başarıyla yönetmeyi başardık. Aspose.Words for .NET, Word belgelerindeki incelemeler ve formlarla Kelime İşleme için güçlü bir API sunar.

### SSS'ler

#### S: Aspose.Words for .NET'te nasıl yeni bir belge oluşturabilir ve şekiller ekleyebilirim?

C: Aspose.Words for .NET'te yeni bir belge oluşturmak ve şekiller eklemek için aşağıdaki kodu kullanabilirsiniz. Burada belgenin ilk bölümüne bir küp ve bir güneş olmak üzere iki şekil ekliyoruz:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### S: Aspose.Words for .NET'te revizyon takibini nasıl etkinleştiririm?

 C: Aspose.Words for .NET'te revizyon izlemeyi etkinleştirmek için`StartTrackRevisions` yöntemi`Document` nesne. Bu yöntem, revizyonların yazarının adını parametre olarak alır:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### S: Aspose.Words for .NET belgesindeki her şekille ilişkili revizyonları nasıl kontrol edebilirim?

C: Aspose.Words for .NET belgesindeki her bir şekille ilgili revizyonları kontrol etmek için, belgenin şekil koleksiyonunu aşağıdaki komutu kullanarak alabilirsiniz:`GetChildNodes` yöntemi ile`NodeType.Shape` düğüm türü. Daha sonra her şeklin`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , Ve`IsMoveToRevision` Şekille hangi tür revizyonun ilişkilendirileceğini belirleyen özellikler:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### S: Aspose.Words for .NET belgesindeki şekillerin yer değiştirme revizyonlarını nasıl kontrol edebilirim?

 C: Bir Aspose.Words for .NET belgesindeki şekil değiştirme revizyonlarını kontrol etmek için, şekil değiştirme revizyonları içeren mevcut bir belgeyi yükleyebilirsiniz. Daha sonra her şeklin`IsMoveFromRevision` Ve`IsMoveToRevision` taşınıp taşınmadığını ve taşınıyorsa nereden ve nereye taşındığını belirlemek için özellikler:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```
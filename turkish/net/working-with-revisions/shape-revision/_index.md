---
title: Şekil Revizyonu
linktitle: Şekil Revizyonu
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki şekilleri gözden geçirin.
type: docs
weight: 10
url: /tr/net/working-with-revisions/shape-revision/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki şekillerde nasıl düzeltmeler yapacağınızı size göstereceğiz. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

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

## 2. Adım: Düzeltmeleri izleyin ve başka bir şekil ekleyin

Düzeltme izlemeyi açacağız ve başka bir şekil ekleyeceğiz.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 3. Adım: Şekil koleksiyonunu alın ve revizyonları kontrol edin

Belgeden şekil koleksiyonunu alacağız ve her şekille ilişkili düzeltmeleri kontrol edeceğiz.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## 4. Adım: Şekil Taşıma Düzeltmelerini Kontrol Etme

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

### Aspose.Words for .NET kullanan Shape Revision için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgedeki şekillerde revizyonlar yapmak için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document();

//Düzeltmeleri izlemeden satır içi bir şekil ekleyin.
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

// Yalnızca eklediğimiz iki şekli içeren belgenin şekil koleksiyonunu alın.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// İlk şekli çıkarın.
shapes[0].Remove();

// Değişiklikler izlenirken bu şekli kaldırdığımız için, şekil bir silme revizyonu olarak sayılır.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Ve değişiklikleri izlerken başka bir şekil ekledik, böylece bu şekil bir ekleme revizyonu olarak sayılacak.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Belgede taşınan bir şekil var, ancak şekil taşıma revizyonlarında bu şeklin iki örneği olacak.
// Biri varış noktasındaki şekil, diğeri ise orijinal konumundaki şekil olacaktır.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Bu, revizyona geçiş, aynı zamanda varış noktasındaki şekildir.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Bu, şeklin orijinal konumunda olduğu revizyondan harekettir.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki şekillerde revizyonlar yapmayı öğrendik. Belge oluşturma, revizyon takibini etkinleştirme, her şekle ilişkin revizyonları kontrol etme ve şekilleri taşımak için revizyonları kontrol etme adımlarını takip ederek revizyonları başarılı bir şekilde yönetebildik. Aspose.Words for .NET, Word belgelerindeki incelemeler ve formlarla çalışmak için güçlü bir API sunar.

### SSS

#### S: Aspose.Words for .NET'te nasıl yeni bir belge oluşturabilir ve şekiller ekleyebilirim?

C: Aspose.Words for .NET'te yeni bir belge oluşturmak ve şekiller eklemek için aşağıdaki kodu kullanabilirsiniz. Burada belgenin ilk bölümüne küp ve güneş olmak üzere iki şekil ekliyoruz:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### S: Aspose.Words for .NET'te revizyon izlemeyi nasıl etkinleştiririm?

 C: Aspose.Words for .NET'te revizyon takibini etkinleştirmek için`StartTrackRevisions` yöntemi`Document` nesne. Bu metot revizyonların yazarının ismini parametre olarak alır:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### S: Bir Aspose.Words for .NET belgesindeki her bir şekil ile ilgili revizyonları nasıl kontrol edebilirim?

C: Bir Aspose.Words for .NET belgesindeki her şekille ilişkili revizyonları kontrol etmek için, belgenin şekiller koleksiyonunu`GetChildNodes` ile yöntem`NodeType.Shape` düğüm türü. Ardından her şekle erişebilirsiniz`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , Ve`IsMoveToRevision` şekille ilişkilendirilmiş revizyon türünü belirlemek için özellikler:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### S: Bir Aspose.Words for .NET belgesinde şekillerin yer değiştirme revizyonlarını nasıl kontrol edebilirim?

 C: Bir Aspose.Words for .NET belgesinde şekil yer değiştirme revizyonlarını kontrol etmek için şekil yer değiştirme revizyonları içeren mevcut bir belgeyi yükleyebilirsiniz. Ardından her şekle erişebilirsiniz`IsMoveFromRevision` Ve`IsMoveToRevision` özellikleri, taşınıp taşınmadığını ve öyleyse nereden ve nereye taşındığını belirlemek için:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```
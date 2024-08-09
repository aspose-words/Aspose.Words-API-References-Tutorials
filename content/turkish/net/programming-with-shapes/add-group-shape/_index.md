---
title: Grup Şekli Ekle
linktitle: Grup Şekli Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı, adım adım eğitimle Aspose.Words for .NET kullanarak Word belgelerine nasıl grup şekilleri ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/add-group-shape/
---
## giriiş

Zengin görsel öğeler içeren karmaşık belgeler oluşturmak, özellikle grup şekilleriyle uğraşırken bazen göz korkutucu bir görev olabilir. Ama korkmayın! Aspose.Words for .NET bu süreci basitleştirerek çok kolay hale getiriyor. Bu eğitimde, Word belgelerinize grup şekilleri ekleme adımlarında size yol göstereceğiz. Dalmaya hazır mısınız? Hadi başlayalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: Buradan indirebilirsiniz.[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya .NET ile uyumlu başka bir IDE.
3. Temel C# Anlayışı: C# programlamaya aşinalık bir artıdır.

## Ad Alanlarını İçe Aktar

Başlamak için projemize gerekli ad alanlarını içe aktarmamız gerekiyor. Bu ad alanları, Word belgelerini Aspose.Words ile değiştirmek için gereken sınıflara ve yöntemlere erişim sağlar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 1. Adım: Belgeyi Başlatın

Öncelikle yeni bir Word belgesi başlatalım. Bunu, grup şekillerimizi ekleyeceğimiz boş bir tuval oluşturmak olarak düşünün.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Burada,`EnsureMinimum()` belge için gereken minimum düğüm kümesini ekler.

## Adım 2: GroupShape Nesnesini Oluşturun

 Daha sonra, bir oluşturmamız gerekiyor`GroupShape`nesne. Bu nesne diğer şekiller için bir kap görevi görecek ve onları bir arada gruplamamıza olanak tanıyacak.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## 3. Adım: GroupShape'e Şekiller Ekleme

 Şimdi şekillerimize tek tek şekiller ekleyelim.`GroupShape` konteyner. Vurgu kenarlığı şekliyle başlayacağız ve ardından bir eylem düğmesi şekli ekleyeceğiz.

### Vurgu Kenarlığı Şekli Ekleme

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Bu kod parçacığı, genişliği ve yüksekliği 100 birim olan bir vurgu kenarlığı şekli oluşturur ve bunu`GroupShape`.

### Eylem Düğmesi Şekli Ekleme

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Burada bir eylem düğmesi şekli oluşturuyoruz, konumlandırıyoruz ve dosyamıza ekliyoruz.`GroupShape`.

## Adım 4: GroupShape Boyutlarını Tanımlayın

 Şekillerimizin grup içinde iyi uyum sağlaması için boyutlarını ayarlamamız gerekir.`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Bu, genişliğini ve yüksekliğini tanımlar.`GroupShape` 200 birim olarak belirler ve koordinat boyutunu buna göre ayarlar.

## Adım 5: GroupShape'i Belgeye Ekleme

 Şimdi bizimkileri ekleyelim`GroupShape` kullanarak belgeye`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` Belgeye şekiller de dahil olmak üzere düğümler eklemenin kolay bir yolunu sağlar.

## Adım 6: Belgeyi Kaydedin

Son olarak belgeyi belirttiğiniz dizine kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Ve işte karşınızda! Grup şekillerinin bulunduğu belgeniz hazır.

## Çözüm

Word belgelerinize grup şekilleri eklemek karmaşık bir süreç olmak zorunda değildir. Aspose.Words for .NET ile şekilleri kolaylıkla oluşturup değiştirebilirsiniz, böylece belgelerinizi görsel olarak daha çekici ve işlevsel hale getirebilirsiniz. Bu eğitimde özetlenen adımları izleyin ve kısa sürede profesyonel olacaksınız!

## SSS'ler

### GroupShape'e ikiden fazla şekil ekleyebilir miyim?
 Evet, istediğiniz kadar şekil ekleyebilirsiniz.`GroupShape` . Sadece şunu kullan`AppendChild` Her şekil için yöntem.

### Bir GroupShape içindeki şekillere stil vermek mümkün müdür?
 Kesinlikle! Her şekle, mevcut özellikler kullanılarak ayrı ayrı stil verilebilir.`Shape` sınıf.

### GroupShape'i belge içinde nasıl konumlandırırım?
 Konumlandırabilirsiniz`GroupShape` ayarlayarak`Left`Ve`Top` özellikler.

### GroupShape içindeki şekillere metin ekleyebilir miyim?
 Evet, şekilleri kullanarak şekillere metin ekleyebilirsiniz.`AppendChild` ekleme yöntemi`Paragraph` içeren`Run` metin içeren düğümler.

### Şekilleri kullanıcı girişine göre dinamik olarak gruplamak mümkün müdür?
Evet, özellikleri ve yöntemleri uygun şekilde ayarlayarak, kullanıcı girişine göre şekilleri dinamik olarak oluşturabilir ve gruplandırabilirsiniz.
---
title: Şekil Ekle
linktitle: Şekil Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Adım adım kılavuzumuzla Aspose.Words for .NET kullanarak Word belgelerine şekilleri nasıl ekleyeceğinizi ve değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/insert-shape/
---
## giriiş

Görsel olarak çekici ve iyi yapılandırılmış Word belgeleri oluşturma söz konusu olduğunda şekiller hayati bir rol oynayabilir. İster oklar, kutular, hatta karmaşık özel şekiller ekliyor olun, bu öğeleri programlı olarak değiştirme yeteneği benzersiz bir esneklik sunar. Bu eğitimde Aspose.Words for .NET kullanarak Word belgelerine şekillerin nasıl eklendiğini ve değiştirildiğini inceleyeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: En son sürümü şuradan indirin ve yükleyin:[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi uygun bir .NET geliştirme ortamı.
3. Temel C# Bilgisi: C# programlama diline ve temel kavramlara aşinalık.

## Ad Alanlarını İçe Aktar

Başlamak için C# projenize gerekli ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 1. Adım: Projenizi Kurun

Şekil eklemeye başlamadan önce projenizi ayarlamanız ve Aspose.Words for .NET kitaplığını eklemeniz gerekir.

1. Yeni Bir Proje Oluşturun: Visual Studio'yu açın ve yeni bir C# Konsol Uygulaması projesi oluşturun.
2. Aspose.Words for .NET'i ekleyin: Aspose.Words for .NET kitaplığını NuGet Paket Yöneticisi aracılığıyla yükleyin.

```bash
Install-Package Aspose.Words
```

## Adım 2: Belgeyi Başlatın

İlk olarak, yeni bir belgeyi ve belgenin oluşturulmasına yardımcı olacak bir belge oluşturucuyu başlatmanız gerekir.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir belge başlat
Document doc = new Document();

// Belgeyi oluşturmaya yardımcı olması için DocumentBuilder'ı başlatın
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Şekil Ekleme

Şimdi belgeye bir şekil ekleyelim. Basit bir metin kutusu ekleyerek başlayacağız.

```csharp
// Belgeye metin kutusu şekli ekleme
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// Şekli döndür
shape.Rotation = 30.0;
```

Bu örnekte (100, 100) konumuna genişliği ve yüksekliği 50 birim olan bir metin kutusu ekliyoruz. Ayrıca şekli 30 derece döndürüyoruz.

## Adım 4: Başka Bir Şekil Ekleyin

Bu sefer konumu belirtmeden belgeye başka bir şekil ekleyelim.

```csharp
// Başka bir metin kutusu şekli ekleme
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// Şekli döndür
secondShape.Rotation = 30.0;
```

Bu kod parçacığı, ilkiyle aynı boyutlara ve dönüşe sahip ancak konumunu belirtmeden başka bir metin kutusu ekler.

## Adım 5: Belgeyi Kaydedin

 Şekilleri ekledikten sonra son adım belgeyi kaydetmektir. biz kullanacağız`OoxmlSaveOptions` Kaydetme formatını belirtmek için

```csharp
// Kaydetme seçeneklerini uyumlulukla tanımlayın
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir Word belgesine şekilleri başarılı bir şekilde eklediniz ve değiştirdiniz. Bu eğitimde temel bilgiler yer alıyordu ancak Aspose.Words, şekillerle çalışmak için özel stiller, bağlayıcılar ve grup şekilleri gibi daha birçok gelişmiş özellik sunuyor.

 Daha ayrıntılı bilgi için şu adresi ziyaret edin:[Aspose.Words for .NET belgeleri](https://reference.aspose.com/words/net/).

## SSS'ler

### Farklı şekil türlerini nasıl eklerim?
değiştirebilirsiniz`ShapeType` içinde`InsertShape` Daireler, dikdörtgenler ve oklar gibi farklı türdeki şekilleri ekleme yöntemini kullanın.

### Şekillerin içine metin ekleyebilir miyim?
 Evet, kullanabilirsiniz`builder.Write` Şekilleri ekledikten sonra içine metin ekleme yöntemi.

### Şekillere stil vermek mümkün mü?
 Evet, aşağıdaki gibi özellikleri ayarlayarak şekillere stil verebilirsiniz:`FillColor`, `StrokeColor` , Ve`StrokeWeight`.

### Şekilleri diğer öğelere göre nasıl konumlandırırım?
 Kullanın`RelativeHorizontalPosition`Ve`RelativeVerticalPosition` şekilleri belgedeki diğer öğelere göre konumlandırmak için özellikler.

### Birden fazla şekli birlikte gruplayabilir miyim?
 Evet, Aspose.Words for .NET, şekilleri gruplandırmanıza olanak tanır.`GroupShape` sınıf.
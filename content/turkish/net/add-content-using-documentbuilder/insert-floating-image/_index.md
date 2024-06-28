---
title: Word Belgesine Kayan Görüntü Ekle
linktitle: Word Belgesine Kayan Görüntü Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı adım adım kılavuzla Aspose.Words for .NET kullanarak bir Word belgesine kayan bir görüntünün nasıl ekleneceğini öğrenin. Belgelerinizi geliştirmek için mükemmeldir.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-floating-image/
---
## giriiş

Resimlerin metninizi tamamlayacak şekilde mükemmel şekilde konumlandırıldığı çarpıcı bir rapor veya teklif oluşturduğunuzu hayal edin. Aspose.Words for .NET ile bunu zahmetsizce başarabilirsiniz. Bu kitaplık, belge işleme için güçlü özellikler sunarak geliştiriciler için başvurulacak bir çözüm haline gelir. Bu öğreticide DocumentBuilder sınıfını kullanarak kayan bir görüntü eklemeye odaklanacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz her adımda size yol gösterecektir.

## Önkoşullar

Başlamadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Kütüphaneyi şu adresten indirebilirsiniz:[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2. Visual Studio: .NET geliştirmeyi destekleyen herhangi bir sürüm.
3. Temel C# Bilgisi: C# programlamanın temellerini anlamak faydalı olacaktır.
4. Resim Dosyası: Eklemek istediğiniz logo veya resim gibi bir resim dosyası.

## Ad Alanlarını İçe Aktar

Aspose.Words'ü projenizde kullanmak için gerekli ad alanlarını içe aktarmanız gerekir. Bu, C# dosyanızın üstüne aşağıdaki satırları ekleyerek yapılır:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Bu önkoşullar ve ad alanları yerine getirildikten sonra eğitimimize başlamaya hazırız.

Kayan bir görüntüyü bir Word belgesine ekleme sürecini yönetilebilir adımlara ayıralım. Herhangi bir aksaklık yaşamadan takip edebilmeniz için her adım ayrıntılı olarak açıklanacaktır.

## 1. Adım: Projenizi Kurun

Öncelikle Visual Studio'da yeni bir C# projesi oluşturun. Kolaylık sağlamak için bir Konsol Uygulaması seçebilirsiniz.

1. Visual Studio'yu açın ve yeni bir proje oluşturun.
2. "Konsol Uygulaması (.NET Core)" seçeneğini seçin ve "İleri"ye tıklayın.
3. Projenize bir ad verin ve kaydedileceği konumu seçin. "Oluştur"u tıklayın.
4. Aspose.Words for .NET'i NuGet Paket Yöneticisi aracılığıyla yükleyin. Solution Explorer'da projenize sağ tıklayın, "NuGet Paketlerini Yönetin"i seçin ve "Apose.Words"u arayın. En son sürümü yükleyin.

## Adım 2: Document ve DocumentBuilder'ı başlatın

Artık projeniz ayarlandığına göre Document ve DocumentBuilder nesnelerini başlatalım.

1.  Yeni bir örneğini oluşturun`Document` sınıf:

```csharp
Document doc = new Document();
```

2. Bir DocumentBuilder nesnesini başlatın:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

`Document` nesne Word belgesini temsil eder ve`DocumentBuilder` içeriğin eklenmesine yardımcı olur.

## 3. Adım: Görüntü Yolunu Tanımlayın

Ardından resim dosyanızın yolunu belirtin. Görselinize projenizin dizininden erişilebildiğinden emin olun.

Görüntü dizinini ve görüntü dosyası adını tanımlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` görüntünüzün saklandığı gerçek yolla.

## 4. Adım: Kayan Görüntüyü Ekleme

Her şey ayarlandığında, kayan görüntüyü belgeye ekleyelim.

 Kullan`InsertImage` yöntemi`DocumentBuilder` resmin ekleneceği sınıf:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

Her parametrenin anlamı aşağıda açıklanmıştır:
- `imagePath`Resim dosyanızın yolu.
- `RelativeHorizontalPosition.Margin`: Kenar boşluğuna göre yatay konum.
- `100`: Kenar boşluğundan yatay uzaklık (nokta cinsinden).
- `RelativeVerticalPosition.Margin`: Kenar boşluğuna göre dikey konum.
- `100`: Kenar boşluğundan dikey uzaklık (nokta cinsinden).
- `200`: Görüntünün genişliği (nokta cinsinden).
- `100`: Görüntünün yüksekliği (nokta cinsinden).
- `WrapType.Square`: Görüntünün etrafındaki metin kaydırma stili.

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi istediğiniz konuma kaydedin.

1. Çıkış dosyası yolunu belirtin:

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. Belgeyi kaydedin:

```csharp
doc.Save(outputPath);
```

Kayan görselin bulunduğu Word belgeniz artık hazır!

## Çözüm

Aspose.Words for .NET kullanarak bir Word belgesine kayan bir görüntü eklemek, yönetilebilir adımlara bölündüğünde basit bir süreçtir. Bu kılavuzu izleyerek belgelerinize profesyonel görünümlü görüntüler ekleyerek görsel çekiciliğini artırabilirsiniz. Aspose.Words, ister raporlar, teklifler, ister başka herhangi bir belge türü üzerinde çalışıyor olun, belge manipülasyonunu çocuk oyuncağı haline getiren güçlü bir API sağlar.

## SSS'ler

### Aspose.Words for .NET'i kullanarak birden fazla resim ekleyebilir miyim?

 Evet, aynı işlemi tekrarlayarak birden fazla resim ekleyebilirsiniz.`InsertImage` İstenilen parametrelerle her görüntü için yöntem.

### Resmin konumunu nasıl değiştiririm?

 Ayarlayabilirsiniz`RelativeHorizontalPosition`, `RelativeVerticalPosition`ve görüntüyü gerektiği gibi konumlandırmak için ofset parametreleri.

### Görüntüler için başka hangi sarma türleri mevcuttur?

 Aspose.Words aşağıdakiler gibi çeşitli sarma türlerini destekler:`Inline`, `TopBottom`, `Tight`, `Through`, ve dahası. Belge düzeninize en uygun olanı seçebilirsiniz.

### Farklı resim formatlarını kullanabilir miyim?

Evet, Aspose.Words JPEG, PNG, BMP ve GIF dahil çok çeşitli görüntü formatlarını destekler.

### Aspose.Words for .NET'in ücretsiz deneme sürümünü nasıl edinebilirim?

 adresinden ücretsiz deneme alabilirsiniz.[Ücretsiz deneme sayfasını aspose](https://releases.aspose.com/).
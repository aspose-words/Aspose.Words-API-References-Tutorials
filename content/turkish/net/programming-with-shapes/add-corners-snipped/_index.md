---
title: Kırpılmış Köşeleri Ekle
linktitle: Kırpılmış Köşeleri Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerinize köşelerden kesilmiş şekli nasıl ekleyeceğinizi öğrenin. Bu adım adım kılavuz, belgelerinizi kolayca geliştirebilmenizi sağlar.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/add-corners-snipped/
---
## giriiş

Word belgelerinize özel şekiller eklemek, önemli bilgileri vurgulamanın veya içeriğinize biraz hava katmanın eğlenceli ve görsel olarak çekici bir yolu olabilir. Bu eğitimde, Aspose.Words for .NET'i kullanarak Word belgelerinize "Köşeler Kesilmiş" şekilleri nasıl ekleyebileceğinizi ele alacağız. Bu kılavuz, bu şekilleri zahmetsizce ekleyebilmenizi ve belgelerinizi bir profesyonel gibi özelleştirebilmenizi sağlayarak her adımda size yol gösterecektir.

## Önkoşullar

Koda geçmeden önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Henüz yapmadıysanız, en son sürümü şu adresten indirin:[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Geliştirme ortamınızı ayarlayın. Visual Studio popüler bir seçimdir ancak .NET'i destekleyen herhangi bir IDE'yi kullanabilirsiniz.
3.  Lisans: Yalnızca deneme yapıyorsanız,[ücretsiz deneme](https://releases.aspose.com/) veya bir tane al[geçici lisans](https://purchase.aspose.com/temporary-license/) Tam işlevselliğin kilidini açmak için.
4. Temel C# Anlayışı: C# programlamaya aşinalık, örnekleri takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET ile çalışmaya başlamadan önce gerekli ad alanlarını içe aktarmamız gerekiyor. Bunları C# dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Şimdi "Köşeleri Kesilmiş" şekli ekleme sürecini birden çok adıma ayıralım. Her şeyin sorunsuz çalıştığından emin olmak için bu adımları yakından izleyin.

## Adım 1: Document'ı ve DocumentBuilder'ı başlatın

 Yapmamız gereken ilk şey yeni bir belge oluşturmak ve bir başlangıç değeri oluşturmaktır.`DocumentBuilder` nesne. Bu oluşturucu belgemize içerik eklememize yardımcı olacaktır.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Bu adımda belgemizi ve oluşturucumuzu kurduk. Düşün`DocumentBuilder` Dijital kaleminiz olarak Word belgenize yazmaya ve çizmeye hazır olun.

## Adım 2: Kesilmiş Köşeleri Ekleme

 Daha sonra kullanacağımız`DocumentBuilder` "Köşeler Kesildi" şekli eklemek için. Bu şekil türü Aspose.Words'te önceden tanımlanmıştır ve tek bir kod satırıyla kolayca eklenebilir.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

Burada şeklin tipini ve boyutlarını (50x50) belirtiyoruz. Belgenizin üzerine küçük, mükemmel şekilde kesilmiş bir köşe çıkartması yerleştirdiğinizi hayal edin. 

## 3. Adım: Uyumlulukla Kaydetme Seçeneklerini Tanımlayın

Belgemizi kaydetmeden önce belgemizin belirli standartlara uygun olmasını sağlamak için kaydetme seçeneklerini tanımlamamız gerekir. biz kullanacağız`OoxmlSaveOptions` Bunun için sınıf.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
```

Bu kaydetme seçenekleri, belgemizin uyumluluk ve belge ömrü açısından çok önemli olan ISO/IEC 29500:2008 standardına uygun olmasını sağlar.

## Adım 4: Belgeyi Kaydedin

Son olarak daha önce tanımladığımız kaydetme seçeneklerini kullanarak belgemizi belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

Ve böylece, belgeniz artık gerekli uyumluluk seçenekleriyle kaydedilmiş özel bir "Köşeler Kesilmiş" şekli içeriyor.

## Çözüm

İşte aldın! Aspose.Words for .NET'i kullanarak Word belgelerinize özel şekiller eklemek basittir ve belgelerinizin görsel çekiciliğini büyük ölçüde artırabilir. Bu adımları izleyerek kolayca "Köşeler Kesilmiş" şekli ekleyebilir ve belgenizin gerekli standartları karşıladığından emin olabilirsiniz. Mutlu kodlama!

## SSS'ler

### "Kesilmiş Köşeler" şeklinin boyutunu özelleştirebilir miyim?
Evet, boyutları değiştirerek boyutu ayarlayabilirsiniz.`InsertShape` yöntem.

### Başka türde şekiller eklemek mümkün mü?
 Kesinlikle! Aspose.Words çeşitli şekilleri destekler. Sadece değiştir`ShapeType` istediğiniz şekle getirin.

### Aspose.Words'ü kullanmak için lisansa ihtiyacım var mı?
Ücretsiz deneme sürümünü veya geçici lisansı kullanabilirsiniz ancak sınırsız kullanım için tam lisans gereklidir.

### Şekillere nasıl daha fazla stil uygulayabilirim?
Şekillerin görünümünü ve davranışını özelleştirmek için Aspose.Words tarafından sağlanan ek özellik ve yöntemleri kullanabilirsiniz.

### Aspose.Words diğer formatlarla uyumlu mu?
Evet, Aspose.Words, DOCX, PDF, HTML ve daha fazlasını içeren birden fazla belge formatını destekler.
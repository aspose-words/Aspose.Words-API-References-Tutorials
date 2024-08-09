---
title: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
linktitle: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı, adım adım eğitimde Aspose.Words for .NET ile bir akışı kullanarak bir OLE nesnesini simge olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---
## giriiş

Bu derste Aspose.Words for .NET'in harika bir özelliğini inceleyeceğiz: bir akış kullanarak simge olarak bir OLE (Nesne Bağlama ve Gömme) nesnesi eklemek. İster bir PowerPoint sunumu, ister bir Excel elektronik tablosu veya başka türde bir dosya gömüyor olun, bu kılavuz size bunu tam olarak nasıl yapacağınızı gösterecektir. Başlamaya hazır mısınız? Hadi gidelim!

## Önkoşullar

Koda geçmeden önce ihtiyacınız olacak birkaç şey var:

-  Aspose.Words for .NET: Henüz yapmadıysanız,[indirmek](https://releases.aspose.com/words/net/) ve Aspose.Words for .NET'i yükleyin.
- Geliştirme Ortamı: Visual Studio veya başka herhangi bir C# geliştirme ortamı.
- Giriş Dosyaları: Gömmek istediğiniz dosya (örneğin bir PowerPoint sunumu) ve bir simge görüntüsü.

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Takip etmeyi kolaylaştırmak için süreci adım adım inceleyelim.

## 1. Adım: Yeni Bir Belge Oluşturun

Öncelikle yeni bir belge ve onunla çalışacak bir belge oluşturucu oluşturacağız.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Düşün`Document` boş tuvaliniz olarak ve`DocumentBuilder` boya fırçanız olarak. Başyapıtımızı yaratmaya başlamak için araçlarımızı ayarlıyoruz.

## 2. Adım: Akışı Hazırlayın

Daha sonra gömmek istediğimiz dosyayı içeren bir bellek akışı hazırlamamız gerekiyor. Bu örnekte bir PowerPoint sunusu yerleştireceğiz.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes("Path_to_your_directory/Presentation.pptx")))
{
```

Bu adım boyanızı fırçaya yüklemek gibidir. Dosyamızı gömülmeye hazır hale getiriyoruz.

## Adım 3: OLE Nesnesini Simge Olarak Ekleme

Şimdi OLE nesnesini belgeye eklemek için belge oluşturucuyu kullanacağız. Dosya akışını, dosya türü için ProgID'yi (bu durumda "Paket"), simge görüntüsünün yolunu ve gömülü dosya için bir etiketi belirteceğiz.

```csharp
builder.InsertOleObjectAsIcon(stream, "Package", "Path_to_your_directory/Logo icon.ico", "My embedded file");
}
```

Sihrin gerçekleştiği yer burası! Dosyamızı gömüyor ve belgenin içinde simge olarak gösteriyoruz.

## Adım 4: Belgeyi Kaydedin

Son olarak belgeyi belirtilen yola kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Bu adım, bitmiş tablonuzu bir çerçeveye koyup duvara asmak gibidir. Belgeniz artık kullanıma hazır!

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir OLE nesnesini bir Word belgesine simge olarak başarıyla gömdünüz. Bu güçlü özellik, dinamik ve etkileşimli belgeleri kolaylıkla oluşturmanıza yardımcı olabilir. İster sunumlar, elektronik tablolar veya başka dosyalar gömün, Aspose.Words bunu çocuk oyuncağı haline getirir. Öyleyse devam edin, deneyin ve belgelerinizde yaratabileceği farkı görün!

## SSS'ler

### Bu yöntemi kullanarak farklı dosya türlerini gömebilir miyim?
Evet, Word, Excel, PowerPoint ve daha fazlası dahil olmak üzere OLE tarafından desteklenen herhangi bir dosya türünü gömebilirsiniz.

### Aspose.Words for .NET'i kullanmak için özel bir lisansa ihtiyacım var mı?
 Evet, Aspose.Words for .NET lisans gerektirir. Alabilirsin[ücretsiz deneme](https://releases.aspose.com/) veya bir satın alın[geçici lisans](https://purchase.aspose.com/temporary-license/) test için.

### OLE nesnesi için kullanılan simgeyi özelleştirebilir miyim?
 Kesinlikle! Simgenin yolunu belirterek herhangi bir görüntü dosyasını simge için kullanabilirsiniz.`InsertOleObjectAsIcon` Yöntem.

### Dosya veya simge yolları yanlışsa ne olur?
Yöntem bir istisna atacaktır. Hataları önlemek için dosyalarınızın yollarının doğru olduğundan emin olun.

### Gömülü nesneyi gömmek yerine bağlamak mümkün müdür?
Evet, Aspose.Words, içeriğini gömmeden dosyaya referans veren bağlantılı OLE nesneleri eklemenize olanak tanır.
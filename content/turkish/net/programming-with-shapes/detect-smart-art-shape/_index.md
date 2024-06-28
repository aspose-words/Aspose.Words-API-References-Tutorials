---
title: Akıllı Sanat Şeklini Algıla
linktitle: Akıllı Sanat Şeklini Algıla
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı, adım adım kılavuzla Aspose.Words for .NET kullanarak Word belgelerindeki SmartArt şekillerini nasıl tespit edeceğinizi öğrenin. Belge iş akışınızı otomatikleştirmek için mükemmeldir.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/detect-smart-art-shape/
---

## giriiş

Selam! Hiç Word belgelerinde SmartArt ile programlı olarak çalışmanız gerekti mi? İster raporları otomatikleştiriyor olun, ister dinamik belgeler oluşturuyor olun, ister yalnızca belge işlemeye dalıyor olun, Aspose.Words for .NET size yardımcı olacaktır. Bu eğitimde Aspose.Words for .NET kullanarak Word belgelerindeki SmartArt şekillerinin nasıl algılanacağını inceleyeceğiz. Her adımı ayrıntılı, takip edilmesi kolay bir kılavuzda ele alacağız. Bu makalenin sonunda, herhangi bir Word belgesindeki SmartArt şekillerini zahmetsizce tanımlayabileceksiniz!

## Önkoşullar

Ayrıntılara dalmadan önce her şeyin ayarlandığından emin olalım:

1. Temel C# Bilgisi: C# sözdizimi ve kavramları konusunda rahat olmalısınız.
2.  Aspose.Words for .NET: İndirin[Burada](https://releases.aspose.com/words/net/) . Sadece keşfediyorsanız, bir tane ile başlayabilirsiniz.[ücretsiz deneme](https://releases.aspose.com/).
3. Visual Studio: Güncel sürümlerden herhangi biri çalışmalıdır ancak en son sürüm önerilir.
4. .NET Framework: Sisteminizde kurulu olduğundan emin olun.

başlamaya hazır mısın? Mükemmel! Hemen içeri girelim.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını içe aktarmamız gerekiyor. Bu adım, kullanacağımız sınıflara ve yöntemlere erişim sağladığı için çok önemlidir.

```csharp
using System;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Bu ad alanları, Word belgelerini oluşturmak, değiştirmek ve analiz etmek için gereklidir.

## Adım 1: Belge Dizinini Ayarlama

Öncelikle belgelerimizin saklandığı dizini belirtmemiz gerekiyor. Bu Aspose.Words'ün analiz etmek istediğimiz dosyaları bulmasına yardımcı olur.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgelerinizin gerçek yolu ile.

## Adım 2: Belgeyi Yükleme

Daha sonra algılamak istediğimiz SmartArt şekillerini içeren Word belgesini yükleyeceğiz.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

 Burada bir başlangıç başlatıyoruz`Document` Word dosyamızın yolunu içeren nesne.

## 3. Adım: SmartArt Şekillerini Algılama

Şimdi heyecan verici kısım geliyor; belgedeki SmartArt şekillerini tespit etmek. SmartArt içeren şekillerin sayısını sayacağız.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmartArt);

Console.WriteLine("The document has {0} shapes with SmartArt.", count);
```

 Bu adımda SmartArt içeren şekilleri filtrelemek ve saymak için LINQ kullanıyoruz.`GetChildNodes` yöntem tüm şekilleri alır ve`HasSmartArt` özelliği, bir şeklin SmartArt içerip içermediğini kontrol eder.

## Adım 4: Kodu Çalıştırma

Kodu yazdıktan sonra Visual Studio'da çalıştırın. Konsol, belgede bulunan SmartArt şekillerinin sayısını görüntüleyecektir.

```plaintext
The document has X shapes with SmartArt.
```

"X" harfini belgenizdeki SmartArt şekillerinin gerçek sayısıyla değiştirin.

## Çözüm

İşte buyur! Aspose.Words for .NET kullanarak Word belgelerindeki SmartArt şekillerini nasıl tespit edeceğinizi başarıyla öğrendiniz. Bu eğitim ortamınızı ayarlamayı, belgeleri yüklemeyi, SmartArt şekillerini algılamayı ve kodu çalıştırmayı kapsıyordu. Aspose.Words çok çeşitli özellikler sunar; bu nedenle,[API belgeleri](https://reference.aspose.com/words/net/) tüm potansiyelini ortaya çıkarmak için.

## SSS

### 1. Aspose.Words for .NET nedir?

Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Belgeyle ilgili görevleri otomatikleştirmek için idealdir.

### 2. Aspose.Words for .NET'i ücretsiz kullanabilir miyim?

 Aspose.Words for .NET'i kullanarak deneyebilirsiniz.[ücretsiz deneme](https://releases.aspose.com/). Uzun süreli kullanım için lisans satın almanız gerekir.

### 3. Bir belgedeki diğer şekil türlerini nasıl tespit ederim?

 Diğer özellikleri veya şekil türlerini denetlemek için LINQ sorgusunu değiştirebilirsiniz. Bakın[dokümantasyon](https://reference.aspose.com/words/net/) daha fazla ayrıntı için.

### 4. Aspose.Words for .NET desteğini nasıl alabilirim?

adresini ziyaret ederek destek alabilirsiniz.[Aspose destek forumu](https://forum.aspose.com/c/words/8).

### 5. SmartArt şekillerini programlı olarak değiştirebilir miyim?

 Evet, Aspose.Words, SmartArt şekillerini programlı olarak değiştirmenize olanak sağlar. Kontrol edin[dokümantasyon](https://reference.aspose.com/words/net/) ayrıntılı talimatlar için.
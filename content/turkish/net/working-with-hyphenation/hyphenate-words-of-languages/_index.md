---
title: Dillerin Tireli Kelimeleri
linktitle: Dillerin Tireli Kelimeleri
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak farklı dillerdeki kelimeleri nasıl tireleyeceğinizi öğrenin. Belgenizin okunabilirliğini artırmak için bu ayrıntılı, adım adım kılavuzu izleyin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/hyphenate-words-of-languages/
---
## giriiş

Selam! Hiç uzun, kesintisiz kelimeler içeren bir belgeyi okumayı denediniz mi ve beyninize kramp girdiğini hissettiniz mi? Hepimiz oradaydık. Ama tahmin et ne oldu? Tireleme sizin kurtarıcınızdır! Aspose.Words for .NET ile kelimeleri dil kurallarına göre doğru şekilde tireleyerek belgelerinizin profesyonel görünmesini sağlayabilirsiniz. Bunu sorunsuz bir şekilde nasıl başarabileceğinize bakalım.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET kuruldu. Almadıysanız hemen alın[Burada](https://releases.aspose.com/words/net/).
-  Aspose.Words için geçerli bir lisans. Bir tane satın alabilirsin[Burada](https://purchase.aspose.com/buy) veya geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).
- Temel C# ve .NET framework bilgisi.
- Bir metin düzenleyici veya Visual Studio gibi bir IDE.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu, tireleme için gereken sınıflara ve yöntemlere erişmeye yardımcı olur.

```csharp
using Aspose.Words;
using Aspose.Words.Hyphenation;
```

## 1. Adım: Belgenizi Yükleyin

 Belgenizin bulunduğu dizini belirtmeniz gerekecektir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 3. Adım: Tireleme Sözlüklerini Kaydedin

 Aspose.Words farklı diller için tireleme sözlükleri gerektirir. Sahip olduğunuzdan emin olun`.dic`tirelemek istediğiniz dillere ait dosyalar. Bu sözlükleri kullanarak kaydedin.`Hyphenation.RegisterDictionary` Yöntem.

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

## Adım 4: Belgeyi Kaydedin

Son olarak tireli belgeyi istediğiniz formatta kaydedin. Burada bunu PDF olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

## Çözüm

Ve işte karşınızda! Yalnızca birkaç satır kodla, sözcükleri dile özgü kurallara göre tireleyerek belgelerinizin okunabilirliğini önemli ölçüde artırabilirsiniz. Aspose.Words for .NET bu süreci basit ve verimli hale getirir. Öyleyse devam edin ve okuyucularınıza daha sorunsuz bir okuma deneyimi yaşatın!

## SSS'ler

### Belgelerde tireleme nedir?
Tireleme, metin hizalamasını ve okunabilirliğini geliştirmek için satır sonlarında sözcükleri ayırma işlemidir.

### Farklı diller için tireleme sözlüklerini nereden edinebilirim?
Genellikle dil enstitüleri veya açık kaynaklı projeler tarafından sağlanan tireleme sözlüklerini çevrimiçi olarak bulabilirsiniz.

### Aspose.Words for .NET'i lisans olmadan kullanabilir miyim?
 Evet, ancak lisanssız sürümün sınırlamaları olacaktır. Bir almanız tavsiye edilir[geçici lisans](https://purchase.aspose.com/temporary-license) tüm özellikler için.

### Aspose.Words for .NET, .NET Core ile uyumlu mu?
Evet, Aspose.Words for .NET hem .NET Framework hem de .NET Core'u destekler.

### Tek bir belgede birden fazla dili nasıl işleyebilirim?
Örnekte gösterildiği gibi birden fazla tireleme sözlüğü kaydedebilirsiniz; Aspose.Words bunları buna göre yönetecektir.
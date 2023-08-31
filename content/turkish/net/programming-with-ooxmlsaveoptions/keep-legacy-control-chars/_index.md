---
title: Eski Kontrol Karakterlerini Koruyun
linktitle: Eski Kontrol Karakterlerini Koruyun
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeyi kaydederken eski kontrol karakterlerini nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi kaydederken eski kontrol karakterlerini korumak için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgeyi dönüştürürken veya kaydederken özel kontrol karakterlerini korumanıza olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce Aspose.Words for .NET ile geliştirme ortamınızı kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## Adım 2: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Bu adımda belgeyi aşağıdaki komutu kullanarak yüklüyoruz:`Document` yöntemi ve devralınan kontrol karakterlerini içeren dosyanın yolunu iletmek.

## 3. Adım: OOXML yedekleme seçeneklerini yapılandırma

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

Bu adımda yeni bir OOXML kaydetme seçeneklerini yapılandırıyoruz.`OoxmlSaveOptions`nesne. İstediğiniz kaydetme formatını belirtiyoruz (burada,`FlatOpc` ) ve etkinleştirin`KeepLegacyControlChars` eski kontrol karakterlerini koruma seçeneği.

## Adım 4: Belgeyi eski kontrol karakterleriyle kaydetme

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Bu son adımda, belgeyi kullanarak kaydediyoruz.`Save` yöntemi ve çıktı dosyasına giden yolu iletmek`.docx` uzantı, belirtilen kaydetme seçenekleriyle birlikte.

Artık bir belgeyi kaydederken eski kontrol karakterlerini korumak için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanan Keep Legacy Control Chars için örnek kaynak kodu 
```csharp

//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi kaydederken eski kontrol karakterlerini korumanın işlevselliğini araştırdık. Belgenin doğru biçimlendirilmesi veya görüntülenmesi açısından önemli olabilecek özel karakterlerin nasıl korunacağını öğrendik.

 Eski kontrol karakterlerini korumak, özel kontrol karakterleri gibi daha eski veya belirli özellikleri kullanan belgelerle Sözcük İşleme yaparken özellikle kullanışlıdır. Etkinleştirerek`KeepLegacyControlChars`seçeneğini kullanarak belgeyi kaydederken bu karakterlerin korunmasını sağlarsınız.

Aspose.Words for .NET, belge düzenleme ihtiyaçlarınızı karşılamak için bir dizi esnek ve güçlü yedekleme seçeneği sunar. Uygun seçenekleri kullanarak yedekleme işlemini belgelerinizin belirli özelliklerini koruyacak şekilde özelleştirebilirsiniz.

Belgelerinizdeki eski kontrol karakterlerinin bütünlüğünü ve korunmasını sağlamak için bu işlevselliği Aspose.Words for .NET projelerinize dahil etmekten çekinmeyin.
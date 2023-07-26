---
title: Eski Kontrol Karakterlerini Koru
linktitle: Eski Kontrol Karakterlerini Koru
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeyi kaydederken eski kontrol karakterlerini nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi kaydederken eski kontrol karakterlerini korumak için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgeyi dönüştürürken veya kaydederken özel kontrol karakterlerini korumanıza olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Bu adımda, kullanarak belgeyi yüklüyoruz`Document` yöntemi ve devralınan kontrol karakterlerini içeren dosyanın yolunu geçirme.

## 3. Adım: OOXML yedekleme seçeneklerini yapılandırma

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

Bu adımda, yeni bir kayıt oluşturarak OOXML kaydetme seçeneklerini yapılandırıyoruz.`OoxmlSaveOptions`nesne. İstenen kayıt formatını belirtiyoruz (burada,`FlatOpc` ) ve etkinleştirin`KeepLegacyControlChars` eski kontrol karakterlerini koruma seçeneği.

## 4. Adım: Belgeyi eski kontrol karakterleriyle kaydetme

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Bu son adımda, belgeyi kullanarak kaydediyoruz.`Save` yöntemi ve yolu çıkış dosyasına iletmek`.docx` uzantı, belirtilen kaydetme seçenekleriyle birlikte.

Artık bir belgeyi kaydederken eski kontrol karakterlerini korumak için kaynak kodu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanan Keep Legacy Control Chars için örnek kaynak kodu 
```csharp

//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi kaydederken eski kontrol karakterlerini korumanın işlevselliğini inceledik. Uygun belge formatlaması veya gösterimi için önemli olabilecek özel karakterleri nasıl koruyacağımızı öğrendik.

 Eski kontrol karakterlerini korumak, özellikle özel kontrol karakterleri gibi daha eski veya belirli özellikleri kullanan belgelerle Sözcük İşleme yaparken kullanışlıdır. etkinleştirerek`KeepLegacyControlChars`seçeneği, belgeyi kaydederken bu karakterlerin korunmasını sağlarsınız.

Aspose.Words for .NET, belge düzenleme ihtiyaçlarınızı karşılamak için bir dizi esnek ve güçlü yedekleme seçeneği sunar. Uygun seçenekleri kullanarak, belgelerinizin belirli özelliklerini korumak için yedekleme işlemini özelleştirebilirsiniz.

Belgelerinizdeki eski kontrol karakterlerinin bütünlüğünü ve korunmasını sağlamak için bu işlevselliği Aspose.Words for .NET projelerinize dahil etmekten çekinmeyin.
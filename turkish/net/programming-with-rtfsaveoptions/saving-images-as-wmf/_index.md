---
title: Görüntüleri Wmf Olarak Kaydetme
linktitle: Görüntüleri Wmf Olarak Kaydetme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile RTF'ye dönüştürürken görüntüleri WMF olarak nasıl kaydedeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

Bu öğreticide, Aspose.Words for .NET ile "Görüntüleri RTF kaydetme seçenekleriyle WMF olarak kaydetme" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, belge resimlerini RTF biçimine dönüştürürken Windows Meta Dosyası (WMF) biçiminde kaydetmenize olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Bu adımda, kullanarak belgeyi yüklüyoruz`Document` yöntemi ve yolu yüklenecek DOCX dosyasına geçirme.

## 3. Adım: Yedekleme seçeneklerini yapılandırma

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

Bu adımda, RTF yedekleme seçeneklerini yapılandırıyoruz. yeni bir tane yaratıyoruz`RtfSaveOptions` nesne ve ayarlayın`SaveImagesAsWmf` mülkiyet`true`. Bu, Aspose.Words'e belge resimlerini RTF'ye dönüştürürken WMF olarak kaydetmesini söyler.

## 4. Adım: Belgeyi kaydetme

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 Bu son adımda, ortaya çıkan belgeyi kullanarak RTF formatında kaydediyoruz.`Save` yöntemi ve yolu, belirtilen kaydetme seçenekleriyle birlikte çıktı dosyasına geçirme.

Artık belge resimlerini RTF formatına dönüştürürken WMF formatında kaydetmek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan belge, "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET ile WMF görüntülerini RTF kaydetme seçenekleriyle kaydetme işlevi için örnek kaynak kodu".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Çözüm

Bu eğitimde, Aspose.Words for .NET'te görüntüleri RTF kaydetme seçenekleriyle WMF olarak kaydetmenin işlevselliğini inceledik. RTF formatına dönüştürürken bir belgeden görüntüleri WMF formatında nasıl kaydedeceğimizi öğrendik.

Bu özellik, RTF belgelerinizdeki görüntülerin kalitesini ve çözünürlüğünü korumak istediğinizde kullanışlıdır. Görüntüleri WMF formatında kaydederek görünümlerinin ve keskinliklerinin bozulmamasını sağlayabilirsiniz.

Aspose.Words for .NET, belge işleme ve oluşturma için birçok gelişmiş özellik sunar. Görüntüleri RTF formatına dönüştürürken WMF formatında kaydetmek, size sunduğu birçok güçlü araçtan biridir.
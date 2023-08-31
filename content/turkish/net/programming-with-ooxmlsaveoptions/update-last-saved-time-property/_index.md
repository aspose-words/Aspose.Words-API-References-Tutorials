---
title: Son Kaydedilen Zaman Özelliğini Güncelle
linktitle: Son Kaydedilen Zaman Özelliğini Güncelle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeyi kaydederken Last Saved Time özelliğini otomatik olarak nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi kaydederken son kaydetme süresi özelliğini güncellemek için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, oluşturulan belgenin son kaydetme süresi özelliğini otomatik olarak güncellemenizi sağlar.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Bu adımda, kullanarak belgeyi yüklüyoruz`Document` yöntemi ve yolu yüklenecek DOCX dosyasına geçirme.

## 3. Adım: OOXML yedekleme seçeneklerini yapılandırma

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 Bu adımda, OOXML kaydetme seçeneklerini kullanarak yapılandırıyoruz.`OoxmlSaveOptions` sınıf. Ayarlayarak son kaydetme süresi özelliğinin otomatik olarak güncellenmesini etkinleştiriyoruz.`UpdateLastSavedTimeProperty` ile`true`.

## 4. Adım: Belgeyi güncellenen özellikle kaydedin

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Bu son adımda, belgeyi kullanarak kaydediyoruz.`Save` yöntemi ve yolu çıkış dosyasına iletmek`.docx` uzantı, belirtilen kaydetme seçenekleriyle birlikte.

Artık bir belgeyi kaydederken son kaydetme süresi özelliğini otomatik olarak güncellemek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanarak Son Kaydedilen Zaman Özelliğini Güncellemek için örnek kaynak kodu 

```csharp

//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi kaydederken son kaydetme süresi özelliğini otomatik olarak güncelleme özelliğini inceledik. OOXML kaydetme seçenekleri ile bu özelliği etkinleştirerek, oluşturulan belgede son kaydetme süresi özelliğinin otomatik olarak güncellenmesini sağlayabilirsiniz.

Son kaydetme süresi özelliğinin güncellenmesi, bir belgenin değişikliklerini ve sürümlerini izlemek için yararlı olabilir. Ayrıca, belgenin en son ne zaman kaydedildiğini de takip eder ve bu, çeşitli senaryolarda yararlı olabilir.

Aspose.Words for .NET, esnek ve güçlü yedekleme seçenekleri sunarak Son Yedekleme Zamanı özelliğini otomatik olarak güncellemeyi kolaylaştırır. Oluşturulan belgelerin doğru yedekleme bilgilerine sahip olmasını sağlamak için bu özelliği projelerinize entegre edebilirsiniz.
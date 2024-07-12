---
title: Sıkıştırma Düzeyini Ayarla
linktitle: Sıkıştırma Düzeyini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeyi kaydederken sıkıştırma düzeyini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi kaydederken sıkıştırma düzeyini ayarlamak için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, oluşturulan belgenin sıkıştırma düzeyini kontrol etmenize olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce Aspose.Words for .NET ile geliştirme ortamınızı kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## Adım 2: Belgeyi yükleme

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Bu adımda belgeyi aşağıdaki komutu kullanarak yüklüyoruz:`Document` yöntemi ve yüklenecek DOCX dosyasının yolunu iletme.

## 3. Adım: OOXML yedekleme seçeneklerini yapılandırma

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 Bu adımda, OOXML kaydetme seçeneklerini kullanarak yapılandırıyoruz.`OoxmlSaveOptions` sınıf. Sıkıştırma seviyesini şu şekilde ayarladık:`SuperFast` Daha hızlı sıkıştırma elde etmek için.

## 4. Adım: Belgeyi belirtilen sıkıştırma düzeyiyle kaydedin

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Bu son adımda, belgeyi kullanarak kaydediyoruz.`Save` yöntemi ve çıktı dosyasına giden yolu iletmek`.docx` uzantı, belirtilen kaydetme seçenekleriyle birlikte.

Artık bir belgeyi kaydederken sıkıştırma düzeyini ayarlamak için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan dosya, "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET kullanarak Sıkıştırma Düzeyini Ayarlama için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir belgeyi kaydederken sıkıştırma düzeyini ayarlamanın işlevselliğini araştırdık. Uygun sıkıştırma düzeyini belirterek belge boyutunu ve oluşturma hızını optimize edebilirsiniz.

`OoxmlSaveOptions` sınıfı ayarlayarak sıkıştırma düzeyini kontrol etme esnekliği sağlar.`CompressionLevel` uygun bir değere sahip mülk, örneğin`SuperFast`. Bu, özel ihtiyaçlarınıza göre dosya boyutu ve yedekleme hızı arasında doğru dengeyi kurmanıza olanak tanır.

Özellikle büyük belgelerde, oluşturulan dosyaların boyutunu azaltmanız gerektiğinde sıkıştırmayı kullanmak yararlı olabilir. Bu, belgelerin saklanmasını, paylaşılmasını ve iletilmesini kolaylaştırabilir.

Aspose.Words for .NET, belge manipülasyonu için bir dizi güçlü seçenek ve özellik sunar. Uygun yedekleme seçeneklerini kullanarak belge oluşturma sürecini özelleştirebilir ve uygulamanızın performansını optimize edebilirsiniz.

Belge oluşturma iş akışınızı geliştirmek için Aspose.Words for .NET'in diğer özelliklerini keşfetmekten çekinmeyin.

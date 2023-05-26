---
title: Temp Klasörünü Kullan
linktitle: Temp Klasörünü Kullan
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belgeleri yüklerken geçici bir klasörü nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-loadoptions/use-temp-folder/
---

Bir C# uygulamasında Word belgeleriyle çalışırken, belge işleme sırasında oluşturulan geçici dosyaları depolamak için geçici bir klasör kullanmak gerekebilir. .NET için Aspose.Words kitaplığıyla, LoadOptions yükleme seçeneklerini kullanarak kolayca geçici bir klasör belirleyebilirsiniz. Bu adım adım kılavuzda, LoadOptions yükleme seçenekleri kullanılarak belirtilen geçici bir klasörü kullanarak bir belgeyi yüklemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Yükleme seçeneklerini yapılandırma

İlk adım, belgemiz için yükleme seçeneklerini yapılandırmaktır. Yükleme parametrelerini belirtmek için LoadOptions sınıfını kullanın. Bizim durumumuzda, TempFolder özelliğini istenen geçici klasörün yoluna ayarlamamız gerekiyor. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };
```

Yeni bir LoadOptions nesnesi oluşturuyoruz ve TempFolder özelliğini istediğimiz geçici klasörün yoluna ayarlıyoruz.

## Belgeyi belirtilen geçici klasörü kullanarak yükleyin

Yükleme seçeneklerini yapılandırdığımıza göre, Document sınıfını kullanarak belgeyi yükleyebilir ve yükleme seçeneklerini belirtebiliriz. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Bu örnekte, belirtilen yükleme seçeneklerini kullanarak belgeler dizininde bulunan "Document.docx" belgesini yüklüyoruz.

### Aspose.Words for .NET kullanan "Geçici Klasörü Kullan" işlevine sahip LoadOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "Geçici Klasörü Kullan" özelliği ile yükleme seçeneklerini yapılandırın
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };

// Belirli bir geçici klasörü kullanarak belgeyi yükleyin
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## Çözüm

Bu kılavuzda, Aspose.Words library for .NET kullanılarak belirli bir geçici klasör kullanılarak bir belgenin nasıl yükleneceğini açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Geçici bir klasör kullanmak, belge işleme sırasında oluşturulan geçici dosyaların düzenli ve verimli bir şekilde saklanmasını sağlar.

---
title: Chm'yi Yükle
linktitle: Chm'yi Yükle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile CHM dosyalarını nasıl yükleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-loadoptions/load-chm/
---

Bir C# uygulamasında HTML Yardımı (CHM) dosyalarıyla çalışırken, bunları doğru şekilde yükleyebilmek önemlidir. .NET için Aspose.Words kitaplığı ile uygun yükleme seçeneklerini kullanarak CHM dosyalarını kolayca yükleyebilirsiniz. Bu adım adım kılavuzda, LoadOptions yükleme seçeneklerini kullanarak bir CHM dosyasını yüklemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Yükleme seçeneklerini yapılandırma

İlk adım, CHM dosyamız için yükleme seçeneklerini yapılandırmaktır. Yükleme parametrelerini belirtmek için LoadOptions sınıfını kullanın. Bizim durumumuzda, Kodlama özelliğini CHM dosyaları için uygun kodlamaya, genellikle "windows-1251" olarak ayarlamamız gerekir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

Yeni bir LoadOptions nesnesi oluşturuyoruz ve CHM dosyaları için Encoding özelliğini "windows-1251" kodlamasına ayarlıyoruz.

## CHM dosyası yükleniyor

Artık yükleme seçeneklerini yapılandırdığımıza göre, Document sınıfını kullanarak CHM dosyasını yükleyebilir ve yükleme seçeneklerini belirtebiliriz. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

Bu örnekte, belirtilen yükleme seçeneklerini kullanarak belgeler dizininde bulunan "HTML help.chm" CHM dosyasını yüklüyoruz.

### Aspose.Words for .NET kullanan "Load Chm" işlevine sahip LoadOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "Load Chm" özelliği ile yükleme seçeneklerinin yapılandırılması
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// CHM dosyasını belirtilen seçeneklerle yükleyin
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kütüphanesini kullanarak bir CHM dosyasının nasıl yükleneceğini açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Aspose.Words ile verimli bir şekilde işleyebilmek ve dönüştürebilmek için CHM dosyalarını doğru şekilde yüklemek çok önemlidir.
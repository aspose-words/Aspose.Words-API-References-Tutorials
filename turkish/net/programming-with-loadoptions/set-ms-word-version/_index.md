---
title: Ms Word Sürümünü Ayarla
linktitle: Ms Word Sürümünü Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgeyi belirli bir MS Word sürümüyle nasıl yükleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-loadoptions/set-ms-word-version/
---

Bir C# uygulamasında Word belgeleriyle çalışırken, belge yüklenirken kullanılacak Microsoft Word sürümünün belirtilmesi gerekebilir. .NET için Aspose.Words kitaplığıyla, LoadOptions'ı kullanarak hangi MS Word sürümünün kullanılacağını kolayca ayarlayabilirsiniz. Bu adım adım kılavuzda, LoadOptions yükleme seçeneklerini kullanarak MS Word'ün belirli bir sürümünü içeren bir belgeyi yüklemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Yükleme Seçeneklerini Yapılandırma

İlk adım, belgemiz için yükleme seçeneklerini yapılandırmaktır. Yükleme parametrelerini belirtmek için LoadOptions sınıfını kullanın. Bizim durumumuzda, MswVersion özelliğini MS Word'ün istenen sürümüne ayarlamamız gerekiyor. Örneğin Microsoft Word 2010 sürümünü kullanıyoruz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Yeni bir LoadOptions nesnesi oluşturuyoruz ve MS Word 2010 sürümünü belirtmek için MswVersion özelliğini MsWordVersion.Word2010 olarak ayarlıyoruz.

## Belirtilen MS Word sürümüyle belge yükleme

Yükleme seçeneklerini yapılandırdığımıza göre, Document sınıfını kullanarak belgeyi yükleyebilir ve yükleme seçeneklerini belirtebiliriz. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Bu örnekte, belirtilen yükleme seçeneklerini kullanarak belgeler dizininde bulunan "Document.docx" belgesini yüklüyoruz.

### Aspose.Words for .NET kullanan "Set MS Word Version" işlevine sahip LoadOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "MS Word Versiyonunu Ayarla" özelliği ile yükleme seçeneklerini yapılandırın
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Belgeyi belirtilen MS Word sürümüyle yükleyin
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// belgeyi kaydet
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Çözüm

Bu kılavuzda, MS Word'ün belirli bir sürümünü belirten bir belgenin Aspose.Words .NET kitaplığı kullanılarak nasıl yükleneceğini açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynağını kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Bir belgeyi MS Word'ün belirli bir sürümüyle yüklemek, uygulamanızda belgenin uygun uyumluluğunu ve işlenmesini sağlamanıza olanak tanır.

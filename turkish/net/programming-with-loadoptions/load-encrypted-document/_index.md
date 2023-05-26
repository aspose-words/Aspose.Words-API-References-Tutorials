---
title: Şifrelenmiş Belgeyi Yükle
linktitle: Şifrelenmiş Belgeyi Yükle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile şifrelenmiş belgeleri nasıl yükleyeceğinizi ve kaydedeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-loadoptions/load-encrypted-document/
---

Bir C# uygulamasında şifrelenmiş belgelerle çalışırken, doğru parolayı sağlayarak belgeleri doğru şekilde yükleyebilmek önemlidir. .NET için Aspose.Words kitaplığıyla, uygun yükleme seçeneklerini kullanarak şifrelenmiş belgeleri kolayca yükleyebilirsiniz. Bu adım adım kılavuzda, LoadOptions yükleme seçeneklerini kullanarak şifreli bir belgeyi yüklemek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Şifrelenmiş bir belgeyi yükleme

İlk adım, uygun yükleme seçeneklerini kullanarak şifrelenmiş bir belge yüklemektir. Bizim durumumuzda, belge yolunu ve parolasını belirterek belgeyi yüklemek için Document sınıfını kullanıyoruz. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

Bu örnekte, "password" parolasını kullanarak belgeler dizininde bulunan "Encrypted.docx" belgesini yüklüyoruz.

## Şifrelenmiş bir belgeyi kaydetme

Şifrelenmiş bir belgeyi karşıya yükledikten sonra, çıktı dosyası için yeni bir parola belirleyerek de kaydedebilirsiniz. Örneğimizde, OdtSaveOptions sınıfını belgeyi ODT formatında yeni bir parola ile kaydetmek için kullanıyoruz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

Bu örnekte yeni şifreyi "newpassword" belirleyerek "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt" isimli belgeyi kaydediyoruz.

### Aspose.Words for .NET kullanan "Load Encrypted Document" işlevine sahip LoadOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belirtilen parola ile şifrelenmiş bir belge yükleyin
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

//Şifrelenmiş bir belgeyi yeni bir parola ile kaydedin
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kitaplığı kullanılarak şifrelenmiş belgelerin nasıl yüklenip kaydedileceğini açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Şifrelenmiş belgeleri yüklemek, verilerinizi güvende tutar ve Aspose.Words'te korumalı belgelerle çalışmanıza olanak tanır.
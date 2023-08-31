---
title: Resim Madde İşaretini Kaydetme
linktitle: Resim Madde İşaretini Kaydetme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde görüntü madde işaretlerini kaydetmeyi nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Resim madde işaretleri, Word belgelerinde özel madde işaretleri eklemek için yaygın olarak kullanılan bir özelliktir. Ancak bazı durumlarda Aspose.Words Library for .NET'i kullanarak belgeleri düzenlerken görüntü madde işareti kaydını devre dışı bırakmak gerekebilir. Bu adım adım kılavuzda, DocSaveOptions kaydetme seçeneklerini kullanarak görüntü madde işareti kaydetmeyi devre dışı bırakmak için .NET için Aspose.Words C# kaynak kodunun nasıl kullanılacağını açıklayacağız.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgelerini .NET dahil farklı platformlarda oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kütüphanedir. Metin ekleme, biçimlendirmeyi değiştirme, bölüm ekleme ve çok daha fazlası gibi belgeleri değiştirmek için birçok özellik sunar.

## Adım 1: Belge Dizinini Ayarlama

İlk adım belgelerinizin bulunduğu dizini tanımlamaktır. Tam dizin yolunu belirtmeniz gerekir. Örneğin :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 2: Belgeyi Görüntü Madde İşaretleriyle Yükleme

Daha sonra belgeyi resim madde işaretleriyle yüklemeniz gerekir. Belgeyi bir dosyadan yüklemek için Document sınıfını kullanın. Örneğin :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Bu örnekte belgeyi "Resim madde işaretleri.docx" dosyasından yüklüyoruz.

  belgeler dizininde bulunur.

## 3. Adım: Kayıt seçeneklerini yapılandırın

Şimdi belgemiz için kaydetme seçeneklerini yapılandıralım. Kaydetme ayarlarını belirtmek için DocSaveOptions sınıfını kullanın. Örneğin :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

Bu örnekte, yeni bir DocSaveOptions nesnesi oluşturuyoruz ve resim madde işaretlerinin kaydedilmesini devre dışı bırakmak için SavePictureBullet özelliğini false olarak ayarlıyoruz.

## 4. Adım: "Resim Madde İşaretini Kaydetme" Özelliğini Etkinleştirin

"Resim Madde İşaretini Kaydetme" özelliğini etkinleştirmek için, kaydetme seçeneklerini SavePictureBullet false olarak ayarlanmış şekilde zaten yapılandırdık. Bu, görüntü madde işaretlerinin son belgeye kaydedilmemesini sağlar.

## 5. Adım: Belgeyi kaydedin

Son olarak Document sınıfının Save metodunu kullanarak belgeyi kaydedebilirsiniz. Dosyanın tam yolunu ve istenen dosya adını belirtin. Örneğin :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

"dataDir"i belgelerinizin dizin yolu ile değiştirdiğinizden emin olun.

## Aspose.Words for .NET kullanan "Resim Madde İşaretini Kaydetme" işlevine sahip DocSaveOptions kaydetme seçenekleri için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi görüntü madde işaretleriyle yükleyin
Document doc = new Document(dataDir + "Image bullet points.docx");

// "Resim Madde İşaretini Kaydetme" özelliğiyle kaydetme seçeneklerini yapılandırın
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Belgeyi belirtilen seçeneklerle kaydedin
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kütüphanesini kullanarak görüntü madde işaretlerinin bir belgeye kaydedilmesinin nasıl devre dışı bırakılacağını ele aldık. Verilen adımları takip ederek ve verilen C# kaynak kodunu kullanarak bu işlevselliği C# uygulamanıza kolayca uygulayabilirsiniz. Resim madde işareti kaydetmeyi devre dışı bırakmak, bazı durumlarda resim madde işaretlerini kaydetmeden belge yapısını ve biçimlendirmeyi korumak için yararlı olabilir.
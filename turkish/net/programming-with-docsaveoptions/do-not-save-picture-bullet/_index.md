---
title: Resim Madde İşaretini Kaydetme
linktitle: Resim Madde İşaretini Kaydetme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinde resim madde işaretleri kaydetmeyi nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Resim madde işaretleri, özel madde işaretleri eklemek için Word belgelerinde yaygın olarak kullanılan bir özelliktir. Ancak bazı durumlarda, Aspose.Words Library for .NET kullanılarak belgeler üzerinde değişiklik yapılırken görüntü madde işareti kaydının devre dışı bırakılması gerekebilir. Bu adım adım kılavuzda, DocSaveOptions kaydetme seçeneklerini kullanarak görüntü mermi kaydetmeyi devre dışı bırakmak için .NET için Aspose.Words C# kaynak kodunun nasıl kullanılacağını açıklayacağız.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## 1. Adım: Belgeler Dizinini Ayarlama

İlk adım, belgelerinizin bulunduğu dizini tanımlamaktır. Tam dizin yolunu belirtmelisiniz. Örneğin :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 2. Adım: Belgeyi Resim Madde İşaretleriyle Yükleme

Ardından, belgeyi resim madde işaretleri ile yüklemeniz gerekir. Belgeyi bir dosyadan yüklemek için Document sınıfını kullanın. Örneğin :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Bu örnekte "Image bullet points.docx" dosyasından belgeyi yüklüyoruz.

  belgeler dizininde bulunur.

## 3. Adım: Kayıt seçeneklerini yapılandırın

Şimdi belgemiz için kaydetme seçeneklerini yapılandıralım. Kaydetme ayarlarını belirtmek için DocSaveOptions sınıfını kullanın. Örneğin :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

Bu örnekte, yeni bir DocSaveOptions nesnesi oluşturuyoruz ve resim madde işaretlerini kaydetmeyi devre dışı bırakmak için SavePictureBullet özelliğini false olarak ayarlıyoruz.

## 4. Adım: "Resim Madde İşaretini Kaydetme" Özelliğini Etkinleştirin

"Resim Madde İşaretini Kaydetme" özelliğini etkinleştirmek için, kaydetme seçeneklerini SavePictureBullet false olarak ayarlayarak zaten yapılandırdık. Bu, resim madde işaretlerinin nihai belgeye kaydedilmemesini sağlar.

## 5. Adım: Belgeyi kaydedin

Son olarak, Document sınıfının Save yöntemini kullanarak belgeyi kaydedebilirsiniz. Dosyanın tam yolunu ve istenen dosya adını belirtin. Örneğin :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Belgelerinizin dizin yolu ile "dataDir" değiştirdiğinizden emin olun.

## Aspose.Words for .NET kullanan "Do Not Save Picture Bullet" işleviyle DocSaveOptions kaydetme seçenekleri için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi resim madde işaretleri ile yükleyin
Document doc = new Document(dataDir + "Image bullet points.docx");

// "Resim Madde İşaretini Kaydetme" özelliği ile kaydetme seçeneklerini yapılandırın
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Belgeyi belirtilen seçeneklerle kaydedin
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kütüphanesini kullanarak bir belgede resim madde işaretlerinin nasıl kaydedileceğini ele aldık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Resim madde işareti kaydetmeyi devre dışı bırakmak, bazı durumlarda resim madde işaretlerini kaydetmeden belge yapısını ve biçimlendirmeyi korumak için yararlı olabilir.
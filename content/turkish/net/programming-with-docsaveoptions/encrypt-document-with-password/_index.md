---
title: Belgeyi Parolayla Şifrele
linktitle: Belgeyi Parolayla Şifrele
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak belgeleri parolayla nasıl şifreleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Bir C# uygulamasında dosyalarla Kelime İşleme yaparken belge güvenliği çok önemlidir. .NET için Aspose.Words kütüphanesi ile belgelerinizi bir parola ile şifreleyerek kolayca koruyabilirsiniz. Bu adım adım kılavuzda, DocSaveOptions kaydetme seçeneklerini kullanarak bir belgeyi şifrelemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgelerini .NET dahil farklı platformlarda oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kütüphanedir. Metin ekleme, biçimlendirmeyi değiştirme, bölüm ekleme ve çok daha fazlası gibi belgeleri değiştirmek için birçok özellik sunar.

## Adım 1: Belge dizinini tanımlama

İlk adım, şifrelenmiş belgeyi kaydetmek istediğiniz dizini ayarlamaktır. Tam dizin yolunu belirtmeniz gerekir. Örneğin :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 2: Belge oluşturma ve düzenleme

Daha sonra bir belge oluşturabilir ve ona içerik ekleyebilirsiniz. Belgenizin içeriğini oluşturmak için Aspose.Words tarafından sağlanan DocumentBuilder sınıfını kullanın. Örneğin :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

Bu örnekte, yeni bir boş belge oluşturuyoruz ve ardından DocumentBuilder'ı kullanarak "Merhaba Dünya!" metnini yazıyoruz.

## 3. Adım: Kayıt seçeneklerini yapılandırın

Şimdi belgemiz için kaydetme seçeneklerini yapılandıralım. Kaydetme ayarlarını belirtmek için DocSaveOptions sınıfını kullanın. Örneğin :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

Bu örnekte yeni bir DocSaveOptions nesnesi oluşturup, belgeyi bu parola ile şifrelemek için Password özelliğini "password" olarak ayarlıyoruz.

## Adım 4: "Belgeyi Parolayla Şifrele" Özelliğini Etkinleştirme

Seçenekleri zaten yapılandırdık

"Belgeyi Parolayla Şifrele" özelliğini otomatik olarak etkinleştiren belirtilen parolayla kayıt. Bu, belgenin kaydedildiğinde belirtilen parolayla şifrelenmesini sağlar.

## Adım 5: Belgeyi kaydetme

Son olarak Document sınıfının Save metodunu kullanarak belgeyi kaydedebilirsiniz. Dosyanın tam yolunu ve istenen dosya adını belirtin. Örneğin :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

"dataDir"i belgelerinizin dizin yolu ile değiştirdiğinizden emin olun.

### Aspose.Words for .NET kullanan "Belgeyi Parolayla Şifrele" işlevine sahip DocSaveOptions kaydetme seçenekleri için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma ve düzenleme
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// "Belgeyi Parolayla Şifrele" özelliğiyle kaydetme seçeneklerini yapılandırın
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Belgeyi belirtilen seçeneklerle kaydedin
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Çözüm

Bu kılavuzda, DocSaveOptions kaydetme seçeneklerini kullanarak bir belgeyi parolayla şifrelemek için .NET için Aspose.Words kütüphanesinin nasıl kullanılacağını açıkladık. Verilen adımları takip ederek ve verilen C# kaynak kodunu kullanarak bu işlevselliği C# uygulamanıza kolayca uygulayabilirsiniz. Belgenin bir parola ile şifrelenmesi, belgenin işlenmesi sırasında gizliliğini ve güvenliğini garanti eder.
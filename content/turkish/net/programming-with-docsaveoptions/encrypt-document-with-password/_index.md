---
title: Belgeyi Şifreyle Şifrele
linktitle: Belgeyi Şifreyle Şifrele
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak belgeleri bir parolayla nasıl şifreleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Bir C# uygulamasındaki dosyalarla Sözcük İşleme yaparken belge güvenliği çok önemlidir. .NET için Aspose.Words kitaplığı ile belgelerinizi bir parola ile şifreleyerek kolayca koruyabilirsiniz. Bu adım adım kılavuzda, DocSaveOptions kaydetme seçeneklerini kullanarak bir belgeyi şifrelemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Adım 1: Belge dizinini tanımlama

İlk adım, şifrelenmiş belgeyi kaydetmek istediğiniz dizini ayarlamaktır. Tam dizin yolunu belirtmelisiniz. Örneğin :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 2. Adım: Belge oluşturma ve düzenleme

Ardından bir belge oluşturabilir ve ona içerik ekleyebilirsiniz. Belgenizin içeriğini oluşturmak için Aspose.Words tarafından sağlanan DocumentBuilder sınıfını kullanın. Örneğin :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

Bu örnekte, yeni bir boş belge oluşturuyoruz ve ardından "Merhaba Dünya!" metnini yazmak için DocumentBuilder'ı kullanıyoruz.

## 3. Adım: Kayıt seçeneklerini yapılandırın

Şimdi belgemiz için kaydetme seçeneklerini yapılandıralım. Kaydetme ayarlarını belirtmek için DocSaveOptions sınıfını kullanın. Örneğin :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

Bu örnekte, yeni bir DocSaveOptions nesnesi oluşturuyoruz ve bu parola ile belgeyi şifrelemek için Password özelliğini "password" olarak ayarlıyoruz.

## 4. Adım: "Belgeyi Parolayla Şifrele" Özelliğini Etkinleştirme

Seçenekleri zaten yapılandırdık

"Belgeyi Parolayla Şifrele" özelliğini otomatik olarak etkinleştiren belirtilen parola ile kayıt. Bu, belgenin kaydedildiğinde belirtilen parola ile şifrelenmesini sağlar.

## 5. Adım: Belgeyi kaydetme

Son olarak, Document sınıfının Save yöntemini kullanarak belgeyi kaydedebilirsiniz. Dosyanın tam yolunu ve istenen dosya adını belirtin. Örneğin :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Belgelerinizin dizin yolu ile "dataDir" değiştirdiğinizden emin olun.

### Aspose.Words for .NET kullanan "Dokümanı Parolayla Şifrele" işlevine sahip DocSaveOptions kaydetme seçenekleri için örnek kaynak kodu

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

Bu kılavuzda, DocSaveOptions kaydetme seçeneklerini kullanarak bir belgeyi parolayla şifrelemek için Aspose.Words kitaplığının .NET için nasıl kullanılacağını açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Belgeyi bir parolayla şifrelemek, belgeyi işlerken gizliliğini ve güvenliğini garanti eder.
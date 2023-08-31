---
title: Salt Okunur Kısıtlamasını Kaldır
linktitle: Salt Okunur Kısıtlamasını Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki salt okunur kısıtlamayı nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/remove-read-only-restriction/
---
Bu eğitimde Aspose.Words for .NET salt okunur kısıtlama kaldırma özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesini düzenlenebilir hale getirmek için salt okunur kısıtlamasını kaldırmanıza olanak tanır. Aşağıdaki adımları takip et:

## Adım 1: Belgeyi Oluşturma ve Korumayı Ayarlama

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

WriteProtection nesnesinin SetPassword() özelliğini kullanarak belge için bir parola ayarlayın:

"MyPassword" kısmını belgeyi korumak için kullandığınız gerçek şifreyle değiştirdiğinizden emin olun.

## 2. Adım: Salt okunur kısıtlamasını kaldırın

Salt okunur kısıtlamasını kaldırmak için ReadOnlyRecommended özelliğini false olarak ayarlayın:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## 3. Adım: Sınırsız Koruma Uygulayın

Son olarak, Belge nesnesinin Koruma() yöntemini kullanarak sınırsız koruma uygulayın:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Belgeyi salt okunur kısıtlaması olmadan kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Salt Okunur Kısıtlamasını Kaldırmak için örnek kaynak kodu

Aspose.Words for .NET kullanarak salt okunur kısıtlamayı kaldırmak için tam kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// En fazla 15 karakter uzunluğunda bir şifre girin.
doc.WriteProtection.SetPassword("MyPassword");

//Salt okunur seçeneğini kaldırın.
doc.WriteProtection.ReadOnlyRecommended = false;

// Herhangi bir koruma olmadan yazma korumasını uygulayın.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Bu adımları izleyerek Aspose.Words for .NET ile bir Word belgesindeki salt okunur kısıtlamayı kolayca kaldırabilirsiniz.


## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki salt okunur kısıtlamanın nasıl kaldırılacağını öğrendik. Verilen adımları takip ederek kısıtlamayı kolayca kaldırabilir ve belgeyi tekrar düzenlenebilir hale getirebilirsiniz. Aspose.Words for .NET, belge koruma ve kısıtlamalarını yönetmek için kapsamlı bir dizi özellik sunarak size Word belgelerinizin güvenlik ve düzenleme özellikleri üzerinde esneklik ve kontrol sağlar.

### SSS'ler

#### S: Aspose.Words for .NET'teki salt okunur kısıtlaması nedir?

C: Aspose.Words for .NET'teki salt okunur kısıtlaması, bir Word belgesini salt okunur olarak ayarlamanıza izin vererek kullanıcıların içerikte veya formatta herhangi bir değişiklik yapmasını engelleyen bir özelliği ifade eder. Bu kısıtlama belgenin bütünlüğünün korunmasına yardımcı olur ve belgenin kazara veya kötü niyetle değiştirilmemesini sağlar.

#### S: Aspose.Words for .NET'i kullanarak salt okunur kısıtlamayı nasıl kaldırabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki salt okunur kısıtlamayı kaldırmak için şu adımları takip edebilirsiniz:
1.  Bir örneğini oluşturun`Document` sınıfını kullanın ve belge için bir parola belirleyin.`SetPassword` yöntemi`WriteProtection` nesne.
2.  Yı kur`ReadOnlyRecommended` mülkiyeti`WriteProtection` itiraz etmek`false` Salt okunur öneriyi kaldırmak için.
3.  kullanarak belgeye sınırsız koruma uygulayın.`Protect` yöntemi`Document` ile nesne`NoProtection` koruma türü.
4.  Belgeyi salt okunur kısıtlaması olmadan kaydedin.`Save` yöntemi`Document` nesne.

#### S: Salt okunur kısıtlamasını bir Word belgesinden parola olmadan kaldırabilir miyim?

C: Hayır, doğru şifreyi girmeden bir Word belgesindeki salt okunur kısıtlamasını kaldıramazsınız. Salt okunur kısıtlaması güvenlik amacıyla ayarlanmıştır ve parola olmadan kaldırılması, belgenin bütünlüğünü koruma amacına zarar verecektir.

#### S: Yanlış parolaya sahip bir Word belgesindeki salt okunur kısıtlamayı kaldırabilir miyim?

C: Hayır, yanlış parolaya sahip bir Word belgesindeki salt okunur kısıtlamasını kaldıramazsınız. Salt okunur kısıtlamasını kaldırmak ve belgeyi yeniden düzenlenebilir hale getirmek için doğru parolanın sağlanması gerekir. Bu, yalnızca doğru şifreye sahip yetkili kullanıcıların belgeyi değiştirebilmesini sağlar.

#### S: Aspose.Words for .NET kullanarak diğer belge koruma türlerini kaldırmak mümkün müdür?

C: Evet, Aspose.Words for .NET, parola koruması, form koruması veya belge düzenleme kısıtlamaları gibi diğer belge koruma türlerini kaldırmak için çeşitli yöntemler sunar. Belgeye uygulanan koruma türüne bağlı olarak Aspose.Words tarafından sağlanan ilgili yöntem ve özellikleri kullanarak belirli korumayı kaldırabilir ve belgeyi düzenlenebilir hale getirebilirsiniz.

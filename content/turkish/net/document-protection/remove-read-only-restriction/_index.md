---
title: Salt Okunur Kısıtlamasını Kaldır
linktitle: Salt Okunur Kısıtlamasını Kaldır
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinden salt okunur kısıtlamasını nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/remove-read-only-restriction/
---
Bu öğreticide, Aspose.Words for .NET salt okunur kısıtlama kaldırma özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesini düzenlenebilir hale getirmek için salt okunur kısıtlamasını kaldırmanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi Oluşturma ve Korumayı Ayarlama

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

WriteProtection nesnesinin SetPassword() özelliğini kullanarak belge için bir parola belirleyin:

Belgeyi korumak için kullandığınız gerçek parola ile "Parolam"ı değiştirdiğinizden emin olun.

## 2. Adım: Salt okunur kısıtlamasını kaldırın

Salt okunur kısıtlamasını kaldırmak için ReadOnlyRecommended özelliğini false olarak ayarlayın:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## 3. Adım: Sınırsız Koruma Uygulayın

Son olarak, Document nesnesinin Protect() yöntemini kullanarak sınırsız koruma uygulayın:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Belgeyi salt okunur kısıtlaması olmadan kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Salt Okunur Kısıtlamayı Kaldır için örnek kaynak kodu

Aspose.Words for .NET kullanarak salt okunur kısıtlamasını kaldırmak için eksiksiz kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// En fazla 15 karakter uzunluğunda bir parola girin.
doc.WriteProtection.SetPassword("MyPassword");

//Salt okunur seçeneğini kaldırın.
doc.WriteProtection.ReadOnlyRecommended = false;

// Herhangi bir koruma olmadan yazma koruması uygulayın.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Bu adımları izleyerek bir Word belgesindeki salt okunur kısıtlamasını Aspose.Words for .NET ile kolayca kaldırabilirsiniz.


## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinden salt okunur kısıtlamasının nasıl kaldırılacağını öğrendik. Sağlanan adımları izleyerek kısıtlamayı kolayca kaldırabilir ve belgeyi yeniden düzenlenebilir hale getirebilirsiniz. Aspose.Words for .NET, Word belgelerinizin güvenlik ve düzenleme yetenekleri üzerinde size esneklik ve kontrol sağlayarak, belge korumasını ve kısıtlamalarını yönetmek için kapsamlı bir dizi özellik sunar.

### SSS

#### S: Aspose.Words for .NET'teki salt okunur kısıtlaması nedir?

C: Aspose.Words for .NET'teki salt okunur kısıtlaması, bir Word belgesini salt okunur olarak ayarlamanıza izin vererek kullanıcıların içerikte veya biçimlendirmede herhangi bir değişiklik yapmasını engelleyen bir özelliği ifade eder. Bu kısıtlama, belgenin bütünlüğünün korunmasına yardımcı olur ve yanlışlıkla veya kötü niyetle değiştirilmemesini sağlar.

#### S: Salt okunur kısıtlamasını Aspose.Words for .NET kullanarak nasıl kaldırabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinden salt okunur kısıtlamasını kaldırmak için şu adımları izleyebilirsiniz:
1.  örneğini oluşturun`Document` class ve kullanarak belge için bir parola ayarlayın.`SetPassword` yöntemi`WriteProtection` nesne.
2.  Yı kur`ReadOnlyRecommended` mülkiyeti`WriteProtection` itiraz etmek`false` salt okunur tavsiyesini kaldırmak için.
3.  kullanarak belgeye sınırsız koruma uygulayın.`Protect` yöntemi`Document` ile nesne`NoProtection` koruma türü.
4.  kullanarak belgeyi salt okunur kısıtlaması olmadan kaydedin.`Save` yöntemi`Document` nesne.

#### S: Salt okunur kısıtlamasını bir Word belgesinden parola olmadan kaldırabilir miyim?

C: Hayır, doğru parolayı girmeden salt okunur kısıtlamasını bir Word belgesinden kaldıramazsınız. Salt okunur kısıtlaması, güvenlik amacıyla ayarlanmıştır ve parola olmadan kaldırılması, belgenin bütünlüğünü koruma amacına zarar verir.

#### S: Salt okunur kısıtlamasını yanlış parolayla bir Word belgesinden kaldırabilir miyim?

C: Hayır, salt okunur kısıtlamasını yanlış parolayla bir Word belgesinden kaldıramazsınız. Salt okunur kısıtlamasını kaldırmak ve belgeyi yeniden düzenlenebilir hale getirmek için doğru parola sağlanmalıdır. Bu, yalnızca doğru parolaya sahip yetkili kullanıcıların belgeyi değiştirebilmesini sağlar.

#### S: Aspose.Words for .NET kullanarak diğer belge koruma türlerini kaldırmak mümkün mü?

C: Evet, Aspose.Words for .NET, parola koruması, form koruması veya belge düzenleme kısıtlamaları gibi diğer belge koruma türlerini kaldırmak için çeşitli yöntemler sunar. Belgeye uygulanan korumanın türüne bağlı olarak Aspose.Words tarafından sağlanan karşılık gelen yöntemleri ve özellikleri kullanarak belirli korumayı kaldırabilir ve belgeyi düzenlenebilir hale getirebilirsiniz.

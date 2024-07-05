---
title: Word Belgesinde Salt Okunur Koruması
linktitle: Word Belgesinde Salt Okunur Koruması
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinizdeki salt okunur dosyalarınızı nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/read-only-protection/
---
Bu eğitimde Aspose.Words for .NET'in salt okunur koruma özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, yetkisiz değişiklikleri önlemek için bir Word belgesini salt okunur hale getirmenize olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi Oluşturma ve Korumayı Uygulama

Document sınıfının bir örneğini ve bir DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye içerik yazın
Belgeye içerik yazmak için DocumentBuilder nesnesini kullanın:

```csharp
builder.Write("Open document as read-only");
```

## 3. Adım: Parolayı ayarlayın ve belgeyi salt okunur yapın

WriteProtection nesnesinin SetPassword() özelliğini kullanarak belge için bir parola ayarlayın:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

"MyPassword" kısmını kullanmak istediğiniz gerçek şifreyle değiştirdiğinizden emin olun.

## 4. Adım: Salt okunur belgeyi uygulayın

ReadOnlyRecommended özelliğini true olarak ayarlayarak belgeyi salt okunur yapın:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 5. Adım: Salt okunur korumayı uygulayın ve belgeyi kaydedin

Son olarak, Document nesnesinin Koruma() yöntemini kullanarak salt okunur korumayı uygulayın:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Korumalı belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Salt Okunur Koruması için örnek kaynak kodu

Aspose.Words for .NET kullanarak salt okunur korumanın tam kaynak kodunu burada bulabilirsiniz:

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// En fazla 15 karakter uzunluğunda bir şifre girin.
doc.WriteProtection.SetPassword("MyPassword");

// Belgeyi salt okunur yapın.
doc.WriteProtection.ReadOnlyRecommended = true;

// Yazma korumasını salt okunur olarak uygulayın.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Bu adımları takip ederek belgelerinizi kolayca koruyabilirsiniz

## Çözüm

Bu eğitimde, Aspose.Words for .NET'in, yetkisiz değişiklikleri önlemek için Word belgelerini salt okunur hale getirmenize olanak tanıyan salt okunur koruma özelliğini inceledik. Verilen adımları takip ederek belgelerinize kolayca salt okunur koruma uygulayabilir ve belgelerin güvenliğini artırabilirsiniz. Salt okunur koruma, düzenleme yeteneklerini kısıtlayarak belgenizin içeriğinin bütünlüğünü ve doğruluğunu sağlamaya yardımcı olur. Aspose.Words for .NET, belge korumayı yönetmek için güçlü ve esnek bir API sağlar ve Word belgelerinizi özelleştirmek ve güvence altına almak için çeşitli diğer özellikleri destekler.

### Word belgesinde salt okunur korumayla ilgili SSS

#### S: Aspose.Words for .NET'te salt okunur koruma nedir?

C: Aspose.Words for .NET'teki salt okunur koruma, bir Word belgesini salt okunur hale getirerek yetkisiz değişiklikleri önleyen bir özelliktir. Bir belge salt okunur olarak ayarlandığında kullanıcılar belgeyi açabilir ve görüntüleyebilir ancak içeriğinde herhangi bir değişiklik yapamazlar.

#### S: Aspose.Words for .NET kullanarak bir Word belgesine salt okunur korumayı nasıl uygulayabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesine salt okunur koruma uygulamak için şu adımları takip edebilirsiniz:
1.  Bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  Kullan`DocumentBuilder` Belgeye içerik yazmak için.
3.  kullanarak belge için bir parola ayarlayın.`SetPassword` yöntemi`WriteProtection` nesne.
4.  Yı kur`ReadOnlyRecommended` mülkiyeti`WriteProtection` itiraz etmek`true` belgenin salt okunur olarak açılmasını önermek için.
5.  Salt okunur korumayı şunu kullanarak uygulayın:`Protect` yöntemi`Document` nesneyi belirterek`ProtectionType` gibi`ReadOnly`.
6.  Korumalı belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

#### S: Aspose.Words for .NET kullanarak bir Word belgesinden salt okunur korumayı kaldırabilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak salt okunur korumayı bir Word belgesinden kaldırabilirsiniz. Bunu yapmak için şunları kullanabilirsiniz:`Unprotect` yöntemi`Document` Belgedeki mevcut korumayı kaldıran sınıf.

#### S: Bir Word belgesinde salt okunur koruma için farklı bir parola ayarlayabilir miyim?

 C: Hayır, Aspose.Words for .NET'teki salt okunur koruma, salt okunur koruma için özel olarak ayrı bir şifre belirlemenize izin vermez. Kullanılarak belirlenen şifre`SetPassword` yöntemi`WriteProtection` nesne, hem salt okunur hem de okuma-yazma koruması da dahil olmak üzere genel belge koruması için geçerlidir.

#### S: Kullanıcılar bir Word belgesinde salt okunur korumayı atlayabilir mi?

C: Bir Word belgesindeki salt okunur korumanın amacı, yanlışlıkla veya yetkisiz olarak yapılan değişiklikleri caydırmak ve önlemektir. Belirli bir düzeyde koruma sağlamakla birlikte, yeterli teknik bilgiye veya düzenleme izinlerine sahip kullanıcılar tarafından bypass edilebilmektedir. Ancak salt okunur koruma caydırıcı olur ve belgenin bütünlüğünün korunmasına yardımcı olur.
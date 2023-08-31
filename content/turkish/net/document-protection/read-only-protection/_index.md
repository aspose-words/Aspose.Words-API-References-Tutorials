---
title: Word Belgesinde Salt Okunur Koruma
linktitle: Word Belgesinde Salt Okunur Koruma
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile salt okunur Word belgelerinizi nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/read-only-protection/
---
Bu eğitimde, Aspose.Words for .NET'in salt okunur koruma özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, yetkisiz değişiklik yapılmasını önlemek için bir Word belgesini salt okunur yapmanızı sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belge Oluşturma ve Koruma Uygulama

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

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

## 3. Adım: Parola belirleyin ve belgeyi salt okunur yapın

WriteProtection nesnesinin SetPassword() özelliğini kullanarak belge için bir parola belirleyin:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

"MyPassword" yerine kullanmak istediğiniz gerçek parolayı koyduğunuzdan emin olun.

## 4. Adım: Salt okunur belgeyi uygulayın

ReadOnlyRecommended özelliğini true olarak ayarlayarak belgeyi salt okunur yapın:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 5. Adım: Salt okunur koruma uygulayın ve belgeyi kaydedin

Son olarak, Document nesnesinin Protect() yöntemini kullanarak salt okunur koruma uygulayın:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Korunan belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Salt Okunur Koruma için örnek kaynak kodu

Aspose.Words for .NET kullanarak salt okunur koruma için eksiksiz kaynak kodu burada:

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// En fazla 15 karakter uzunluğunda bir parola girin.
doc.WriteProtection.SetPassword("MyPassword");

// Belgeyi salt okunur yapın.
doc.WriteProtection.ReadOnlyRecommended = true;

// Yazma korumasını salt okunur olarak uygulayın.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Bu adımları izleyerek belgelerinizi kolayca koruyabilirsiniz.

## Çözüm

Bu eğitimde, Aspose.Words for .NET'in, yetkisiz değişiklikleri önlemek için Word belgelerini salt okunur yapmanıza izin veren salt okunur koruma özelliğini inceledik. Sağlanan adımları izleyerek belgelerinize kolayca salt okunur koruma uygulayabilir ve güvenliklerini artırabilirsiniz. Salt okunur koruma, düzenleme yeteneklerini kısıtlayarak belgenizin içeriğinin bütünlüğünü ve doğruluğunu sağlamaya yardımcı olur. Aspose.Words for .NET, belge korumasını yönetmek için güçlü ve esnek bir API sağlar ve Word belgelerinizi özelleştirmek ve güvence altına almak için çeşitli diğer özellikleri destekler.

### Word belgesinde salt okunur koruma için SSS

#### S: Aspose.Words for .NET'te salt okunur koruma nedir?

C: Aspose.Words for .NET'te salt okunur koruma, bir Word belgesini salt okunur yapmanızı sağlayarak yetkisiz değişiklikleri önleyen bir özelliktir. Bir belge salt okunur olarak ayarlandığında, kullanıcılar belgeyi açıp görüntüleyebilir ancak içeriğinde herhangi bir değişiklik yapamazlar.

#### S: Aspose.Words for .NET kullanarak bir Word belgesine salt okunur korumayı nasıl uygulayabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesine salt okunur koruma uygulamak için şu adımları takip edebilirsiniz:
1.  örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  Kullan`DocumentBuilder` belgeye içerik yazmak için.
3.  kullanarak belge için bir parola ayarlayın.`SetPassword` yöntemi`WriteProtection` nesne.
4.  Yı kur`ReadOnlyRecommended` mülkiyeti`WriteProtection` itiraz etmek`true` belgeyi salt okunur olarak açmayı önermek için.
5.  kullanarak salt okunur koruma uygulayın.`Protect` yöntemi`Document` nesne, belirterek`ProtectionType` gibi`ReadOnly`.
6.  kullanarak korunan belgeyi kaydedin.`Save` yöntemi`Document` nesne.

#### S: Aspose.Words for .NET kullanarak bir Word belgesinden salt okunur korumasını kaldırabilir miyim?

C: Evet, Aspose.Words for .NET kullanarak bir Word belgesinden salt okunur korumayı kaldırabilirsiniz. Bunu yapmak için,`Unprotect` yöntemi`Document` belgeden mevcut korumayı kaldıran sınıf.

#### S: Bir Word belgesinde salt okunur koruma için farklı bir parola belirleyebilir miyim?

 C: Hayır, Aspose.Words for .NET'teki salt okunur koruma, salt okunur koruma için özel olarak ayrı bir parola belirlemenize izin vermiyor. kullanılarak ayarlanan parola`SetPassword` yöntemi`WriteProtection` nesne, hem salt okunur hem de okuma-yazma koruması dahil olmak üzere genel belge koruması için geçerlidir.

#### S: Kullanıcılar bir Word belgesinde salt okunur korumayı atlayabilir mi?

Y: Bir Word belgesindeki salt okunur korumanın amacı, kazara veya yetkisiz değişikliklerden caydırmak ve önlemektir. Bir düzeyde koruma sağlamakla birlikte, yeterli teknik bilgiye veya düzenleme izinlerine sahip kullanıcılar tarafından atlanabilir. Ancak salt okunur koruma, caydırıcı bir işlev görür ve belgenin bütünlüğünün korunmasına yardımcı olur.
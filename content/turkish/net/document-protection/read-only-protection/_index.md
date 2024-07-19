---
title: Word Belgesinde Salt Okunur Koruması
linktitle: Word Belgesinde Salt Okunur Koruması
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak salt okunur koruma uygulayarak Word belgelerinizi nasıl koruyacağınızı öğrenin. Adım adım kılavuzumuzu takip edin.
type: docs
weight: 10
url: /tr/net/document-protection/read-only-protection/
---
## giriiş

Word belgelerini yönetmeye gelince, içeriklerini korumak için onları salt okunur hale getirmeniz gereken zamanlar vardır. Yanlışlıkla düzenleme riski olmadan önemli bilgilerin paylaşılması veya yasal belgelerin bütünlüğünün sağlanması için olsun, salt okunur koruma değerli bir özelliktir. Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesine salt okunur korumanın nasıl uygulanacağını inceleyeceğiz. Kolayca takip edebilmenizi sağlamak için her adımda size ayrıntılı ve ilgi çekici bir şekilde yol göstereceğiz.

## Önkoşullar

Kodun ayrıntılarına girmeden önce yerine getirmeniz gereken birkaç önkoşul vardır:

1.  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: .NET'in yüklü olduğu bir geliştirme ortamı kurun. Visual Studio iyi bir seçimdir.
3. Temel C# Anlayışı: Bu eğitimde, C# programlama konusunda temel bir anlayışa sahip olduğunuz varsayılmaktadır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarının içe aktarıldığından emin olalım. Bu, Aspose.Words for .NET'ten ihtiyacımız olan sınıflara ve yöntemlere erişmemizi sağladığı için çok önemlidir.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1. Adım: Belgeyi Ayarlayın

Bu adımda yeni bir belge ve belge oluşturucu oluşturacağız. Bu, operasyonlarımızın temelini oluşturur.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgeye bir miktar metin yazın.
builder.Write("Open document as read-only");
```

Açıklama:

- Belgenin kaydedileceği dizin yolunu tanımlayarak başlıyoruz.
-  Yeni bir`Document` nesne yaratılır ve`DocumentBuilder` onunla ilişkilidir.
- Oluşturucuyu kullanarak belgeye basit bir metin satırı ekliyoruz.

## Adım 2: Yazma Koruması Parolasını Ayarlayın

Daha sonra yazma koruması için bir şifre belirlememiz gerekiyor. Bu şifre en fazla 15 karakter uzunluğunda olabilir.

```csharp
//En fazla 15 karakter uzunluğunda bir şifre girin.
doc.WriteProtection.SetPassword("MyPassword");
```

Açıklama:

- `SetPassword` yöntem çağrılır`WriteProtection` belgenin özelliği.
- Korumayı kaldırmak için gerekli olacak bir şifre (bu durumda MyPassword) sağlıyoruz.

## 3. Adım: Salt Okunur Öneriyi Etkinleştirin

Bu adımda belgeyi salt okunur önerilir hale getiriyoruz. Bu, belge açıldığında kullanıcıdan onu salt okunur modda açmasının isteneceği anlamına gelir.

```csharp
// Belgeyi önerilen salt okunur hale getirin.
doc.WriteProtection.ReadOnlyRecommended = true;
```

Açıklama:

- `ReadOnlyRecommended` özellik şu şekilde ayarlandı:`true`.
- Bu, kullanıcılardan belgeyi salt okunur modda açmalarını ister ancak öneriyi göz ardı etmeyi de seçebilirler.

## 4. Adım: Salt Okunur Korumasını Uygulayın

Son olarak belgeye salt okunur korumayı uyguluyoruz. Bu adım korumayı güçlendirir.

```csharp
// Yazma korumasını salt okunur olarak uygulayın.
doc.Protect(ProtectionType.ReadOnly);
```

Açıklama:

- `Protect` belgede yöntem çağrılır`ProtectionType.ReadOnly` argüman olarak.
- Bu yöntem, salt okunur korumayı uygulayarak belgede parola olmadan değişiklik yapılmasını engeller.

## Adım 5: Belgeyi Kaydedin

Son adım, belgeyi uygulanan koruma ayarlarıyla kaydetmektir.

```csharp
// Korumalı belgeyi kaydedin.
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Açıklama:

- `Save` Belgede dosyanın yolunu ve adını belirten yöntem çağrılır.
- Belge salt okunur korumayla birlikte kaydedilir.

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak başarıyla salt okunur korumalı bir Word belgesi oluşturdunuz. Bu özellik, belgenizin içeriğinin bozulmadan ve değiştirilmeden kalmasını sağlayarak ekstra bir güvenlik katmanı sağlar. İster hassas bilgileri ister yasal belgeleri paylaşıyor olun, salt okunur koruma, belge yönetimi cephanenizde bulunması gereken bir araçtır.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgelerini C# veya diğer .NET dillerini kullanarak programlı olarak oluşturmasına, değiştirmesine, dönüştürmesine ve korumasına olanak tanıyan güçlü bir kitaplıktır.

### Bir belgeden salt okunur korumayı kaldırabilir miyim?
 Evet, salt okunur korumayı şunu kullanarak kaldırabilirsiniz:`Unprotect` yöntem ve doğru şifrenin sağlanması.

### Belgede belirlenen parola şifrelenmiş mi?
Evet, Aspose.Words, korunan belgenin güvenliğini sağlamak için şifreyi şifreler.

### Aspose.Words for .NET'i kullanarak diğer koruma türlerini uygulayabilir miyim?
Evet, Aspose.Words for .NET, yalnızca yorumlara izin verme, form doldurma veya değişiklikleri izleme dahil olmak üzere çeşitli koruma türlerini destekler.

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Aspose sürümler sayfası](https://releases.aspose.com/).
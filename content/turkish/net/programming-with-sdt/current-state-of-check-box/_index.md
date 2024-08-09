---
title: Onay Kutusunun Mevcut Durumu
linktitle: Onay Kutusunun Mevcut Durumu
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerindeki onay kutularını nasıl yöneteceğinizi öğrenin. Bu kılavuz, onay kutularının programlı olarak ayarlanmasını, güncellenmesini ve kaydedilmesini kapsar.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/current-state-of-check-box/
---
## giriiş

Bu eğitimde, Word belgelerindeki onay kutularıyla çalışma sürecini anlatacağız. Bir onay kutusuna nasıl erişileceğini, durumunu nasıl belirleyeceğimizi ve buna göre nasıl güncelleyeceğimizi ele alacağız. İster kontrol edilebilir seçenekler gerektiren bir form geliştiriyor olun ister belge değişikliklerini otomatikleştiriyor olun, bu kılavuz size sağlam bir temel sağlayacaktır.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET Library: Aspose.Words kütüphanesinin kurulu olduğundan emin olun. Henüz yapmadıysanız adresinden indirebilirsiniz.[Web sitesi](https://releases.aspose.com/words/net/).

2. Visual Studio: Kodunuzu derlemek ve çalıştırmak için Visual Studio gibi bir .NET geliştirme ortamı gerekli olacaktır.

3. Temel C# Bilgisi: C# programlamaya aşinalık, verilen örnekleri anlamanıza ve takip etmenize yardımcı olacaktır.

4. Onay Kutuları İçeren Word Belgesi: Bu eğitim için onay kutusu form alanlarını içeren bir Word belgesine ihtiyacınız olacak. Bu belgeyi, onay kutularının programlı olarak nasıl değiştirileceğini göstermek için kullanacağız.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET'i kullanmaya başlamak için gerekli ad alanlarını içe aktarmanız gerekir. C# dosyanızın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
```

Bu ad alanları Aspose.Words API'sine erişmenize ve onunla çalışmanıza ve onay kutuları da dahil olmak üzere yapılandırılmış belge etiketlerini yönetmenize olanak tanır.

## 1. Adım: Belge Yolunu Ayarlama

 Öncelikle Word belgenizin yolunu belirtmeniz gerekir. Aspose.Words'ün işlemleri gerçekleştirmek için dosyayı arayacağı yer burasıdır. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin saklandığı gerçek yolla.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleme

 Daha sonra, Word belgesini bir örneğine yükleyin.`Document` sınıf. Bu sınıf, Word belgenizi kod halinde temsil eder ve onu işlemek için çeşitli yöntemler sağlar.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
```

 Burada,`"Structured document tags.docx"` Word dosyanızın adıyla değiştirilmelidir.

## 3. Adım: Onay Kutusu Form Alanına Erişme

Belirli bir onay kutusuna erişmek için onu belgeden almanız gerekir. Aspose.Words onay kutularını yapılandırılmış belge etiketleri olarak ele alır. Aşağıdaki kod, belgedeki ilk yapılandırılmış belge etiketini alır ve bunun bir onay kutusu olup olmadığını kontrol eder.

```csharp
//Belgeden ilk içerik kontrolünü alın.
StructuredDocumentTag sdtCheckBox =
    (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 4. Adım: Onay Kutusu Durumunu Kontrol Etme ve Güncelleme

 Bir kez sahip olduğunuzda`StructuredDocumentTag` örneğin türünü kontrol edebilir ve durumunu güncelleyebilirsiniz. Bu örnek, onay kutusunun gerçekten bir onay kutusu olup olmadığını işaretlenecek şekilde ayarlar.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
    sdtCheckBox.Checked = true;
```

## Adım 5: Belgeyi Kaydetme

Son olarak değiştirilen belgeyi yeni bir dosyaya kaydedin. Bu, orijinal belgeyi korumanıza ve güncellenmiş sürümle çalışmanıza olanak tanır.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

 Bu örnekte,`"WorkingWithSdt.CurrentStateOfCheckBox.docx"` değiştirilen belgenin kaydedileceği dosyanın adıdır.

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak Word belgelerindeki onay kutusu form alanlarının nasıl değiştirileceğini ele aldık. Belge yolunu nasıl ayarlayacağımızı, belgeyi nasıl yükleyeceğimizi, onay kutularına nasıl erişeceğimizi, durumlarını nasıl güncelleyeceğimizi ve değişiklikleri nasıl kaydedeceğimizi araştırdık. Bu becerilerle artık programlı olarak daha etkileşimli ve dinamik Word belgeleri oluşturabilirsiniz.

## SSS'ler

### Aspose.Words for .NET ile ne tür belge öğelerini işleyebilirim?
Aspose.Words for .NET, paragraflar, tablolar, resimler, üstbilgiler, altbilgiler ve onay kutuları gibi yapılandırılmış belge etiketleri dahil olmak üzere çeşitli belge öğelerini değiştirmenize olanak tanır.

### Bir belgede birden fazla onay kutusunu nasıl işleyebilirim?
Birden fazla onay kutusunu yönetmek için, yapılandırılmış belge etiketleri koleksiyonunda dolaşıp her birini kontrol ederek bunun bir onay kutusu olup olmadığını belirlersiniz.

### Aspose.Words for .NET'i bir Word belgesinde yeni onay kutuları oluşturmak için kullanabilir miyim?
 Evet, şu türden yapılandırılmış belge etiketleri ekleyerek yeni onay kutuları oluşturabilirsiniz:`SdtType.Checkbox` belgenize.

### Bir belgeden onay kutusunun durumunu okumak mümkün müdür?
 Kesinlikle. Şuraya erişerek bir onay kutusunun durumunu okuyabilirsiniz:`Checked` mülkiyeti`StructuredDocumentTag` eğer türdense`SdtType.Checkbox`.

### Aspose.Words for .NET için nasıl geçici lisans alabilirim?
 Geçici lisansı adresinden alabilirsiniz.[Satın alma sayfasını atayın](https://purchase.aspose.com/temporary-license/), kütüphanenin tüm işlevselliğini değerlendirmenize olanak tanır.
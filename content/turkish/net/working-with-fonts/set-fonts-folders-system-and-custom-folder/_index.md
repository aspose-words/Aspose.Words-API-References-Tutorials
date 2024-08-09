---
title: Yazı Tipleri Klasör Sistemini ve Özel Klasörü Ayarlama
linktitle: Yazı Tipleri Klasör Sistemini ve Özel Klasörü Ayarlama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde sistem ve özel yazı tipi klasörlerini nasıl ayarlayacağınızı öğrenin ve belgelerinizin farklı ortamlarda doğru şekilde görüntülenmesini sağlayın.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## giriiş

Benzersiz bir yazı tipi stiline sahip bir belge hazırladığınızı, ancak yazı tiplerinin başka bir makinede düzgün görüntülenmediğini fark ettiğinizi hayal edin. Sinir bozucu, değil mi? Yazı tipi klasörlerini yapılandırmanın devreye girdiği yer burasıdır. Aspose.Words for .NET ile belgelerinizin her zaman istediğiniz gibi görünmesini sağlamak için sistem ve özel yazı tipi klasörleri tanımlayabilirsiniz. Bunu nasıl başarabileceğinize bakalım.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET Library: Henüz yapmadıysanız indirin[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio benzeri bir IDE.
- Temel C# Bilgisi: C#'a aşinalık, kod örneklerini takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle projenize gerekli ad alanlarını içe aktarın:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Şimdi süreci basit adımlara ayıralım.

## 1. Adım: Belgeyi Yükleyin

 Başlamak için Word belgenizi Aspose.Words'e yükleyin`Document` nesne. Bu belge, yazı tipi klasörlerini ayarlamak istediğiniz belge olacaktır.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Adım 2: Yazı Tipi Ayarlarını Başlatın

 Yeni bir örneğini oluştur`FontSettings`. Bu nesne yazı tipi kaynaklarını yönetmenize olanak tanır.

```csharp
FontSettings fontSettings = new FontSettings();
```

## 3. Adım: Sistem Yazı Tipi Kaynaklarını Alın

Varsayılan sistem yazı tipi kaynaklarını alın. Bir Windows makinesinde bu genellikle "Windows\Fonts"u içerir.\"dizini.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## 4. Adım: Özel Yazı Tipi Klasörü Ekleyin

Ek yazı tiplerinizi içeren özel bir klasör ekleyin. Sistem yazı tipleri dizininde yüklü olmayan belirli yazı tipleriniz varsa bu kullanışlıdır.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## 5. Adım: Yazı Tipi Kaynaklarını Güncelleyin

 Yazı tipi kaynakları listesini tekrar bir diziye dönüştürün ve`FontSettings` nesne.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Adım 6: Yazı Tipi Ayarlarını Belgeye Uygulayın

 Son olarak yapılandırılmış olanı uygulayın`FontSettings` belgenize ekleyin ve PDF gibi istediğiniz formatta kaydedin.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek, ister sistem yazı tipleri, ister belirli bir dizinde saklanan özel yazı tipleri olsun, Word belgelerinizin doğru yazı tiplerini kullandığından emin olabilirsiniz. Bu kurulum, farklı ortamlarda belgenizin görünümünün bütünlüğünü korumaya yardımcı olur.

## SSS'ler

### Hem sistem hem de özel klasörlerde bir yazı tipi eksikse ne olur?

Aspose.Words, eksik yazı tipinin yerine varsayılan bir yazı tipi kullanacak ve belgenin okunabilir kalmasını sağlayacaktır.

### Birden fazla özel yazı tipi klasörü ekleyebilir miyim?

 Evet, oluşturma işlemini tekrarlayarak birden fazla özel yazı tipi klasörü ekleyebilirsiniz.`FolderFontSource` nesneleri ve bunları yazı tipi kaynakları listesine ekleme.

### Özel yazı tipi klasörleri için ağ yollarını kullanmak mümkün mü?

 Evet, bir ağ yolu belirleyebilirsiniz.`FolderFontSource` yapıcı.

### Aspose.Words belgeleri kaydetmek için hangi dosya formatlarını destekliyor?

Aspose.Words, DOCX, PDF, HTML ve daha fazlası dahil olmak üzere çeşitli formatları destekler.

### Yazı tipi değiştirme bildirimlerini nasıl halledebilirim?

 Yazı tipi değiştirme bildirimlerini kullanarak yönetebilirsiniz.`FontSettings` sınıfın`FontSubstitutionWarning`etkinlik.
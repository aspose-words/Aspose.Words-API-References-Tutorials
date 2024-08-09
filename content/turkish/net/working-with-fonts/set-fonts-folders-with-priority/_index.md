---
title: Yazı Tipi Klasörlerini Öncelikli Olarak Ayarla
linktitle: Yazı Tipi Klasörlerini Öncelikli Olarak Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde yazı tipi klasörlerini öncelikli olarak nasıl ayarlayacağınızı öğrenin. Kılavuzumuz belgelerinizin her zaman mükemmel şekilde işlenmesini sağlar.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-with-priority/
---
## giriiş

Belge işleme dünyasında, özel yazı tipi klasörleri ayarlamak, belgelerinizin nerede görüntülenirse görüntülensin mükemmel şekilde görüntülenmesini sağlamada büyük fark yaratabilir. Bugün Aspose.Words for .NET'i kullanarak Word belgelerinizde yazı tipi klasörlerini öncelikli olarak nasıl ayarlayabileceğinizi ele alacağız. Bu kapsamlı kılavuz, süreci mümkün olduğunca sorunsuz hale getirerek her adımda size yol gösterecektir.

## Önkoşullar

Başlamadan önce ihtiyacımız olan her şeye sahip olduğumuzdan emin olalım. İşte hızlı bir kontrol listesi:

-  Aspose.Words for .NET: Bu kütüphanenin kurulu olması gerekmektedir. Henüz sahip değilseniz, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio gibi çalışan bir .NET geliştirme ortamına sahip olduğunuzdan emin olun.
-  Belge Dizini: Belgeleriniz için bir dizininizin olduğundan emin olun. Örneklerimiz için kullanacağız`"YOUR DOCUMENT DIRECTORY"` bu yol için yer tutucu olarak.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor. Bu ad alanları Aspose.Words tarafından sağlanan sınıflara ve yöntemlere erişim için gereklidir.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Şimdi yazı tipi klasörlerini öncelikli olarak ayarlamak için her adımı ayrı ayrı inceleyelim.

## 1. Adım: Yazı Tipi Kaynaklarınızı Ayarlayın

Başlamak için yazı tipi kaynaklarını tanımlamak isteyeceksiniz. Burası Aspose.Words'e yazı tiplerini nerede arayacağınızı söyleyeceğiniz yerdir. Birden fazla yazı tipi klasörü belirtebilir ve hatta bunların önceliklerini ayarlayabilirsiniz.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

Bu örnekte iki yazı tipi kaynağı ayarlıyoruz:
- SystemFontSource: Sisteminizde yüklü olan tüm yazı tiplerini içeren varsayılan yazı tipi kaynağıdır.
-  FolderFontSource: Bu, şu adreste bulunan özel bir yazı tipi klasörüdür:`C:\\MyFonts\\` .`true` parametresi bu klasörün yinelemeli olarak taranması gerektiğini belirtir ve`1` önceliğini belirler.

## 2. Adım: Belgenizi Yükleyin

Ardından, çalışmak istediğiniz belgeyi yükleyin. Belgenin belirttiğiniz dizinde bulunduğundan emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu kod satırı adlı bir belgeyi yükler.`Rendering.docx` belge dizininizden.

## 3. Adım: Belgenizi Yeni Yazı Tipi Ayarlarıyla Kaydedin

Son olarak belgenizi kaydedin. Belgeyi kaydettiğinizde Aspose.Words belirttiğiniz yazı tipi ayarlarını kullanacaktır.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 Bu, belgeyi belge dizininize şu adla PDF olarak kaydeder:`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak öncelikli yazı tipi klasörlerini başarıyla oluşturdunuz. Özel yazı tipi klasörleri ve öncelikleri belirleyerek belgelerinizin nerede görüntülenirse görüntülensin tutarlı bir şekilde görüntülenmesini sağlayabilirsiniz. Bu, özellikle belirli yazı tiplerinin varsayılan olarak yüklenmediği ortamlarda kullanışlıdır.

## SSS'ler

### Neden özel yazı tipi klasörleri ayarlamam gerekiyor?
Özel yazı tipi klasörleri ayarlamak, görüntülendikleri sistemde yüklü olmayan yazı tiplerini kullansalar bile belgelerinizin doğru şekilde oluşturulmasını sağlar.

### Birden fazla özel yazı tipi klasörü ayarlayabilir miyim?
Evet, birden fazla yazı tipi klasörü belirleyebilirsiniz. Aspose.Words her klasör için önceliği ayarlamanıza olanak tanıyarak en önemli yazı tiplerinin ilk önce bulunmasını sağlar.

### Belirtilen tüm kaynaklarda bir yazı tipi eksikse ne olur?
Belirtilen tüm kaynaklarda bir yazı tipi eksikse Aspose.Words, belgenin hala okunabilir olmasını sağlamak için bir yedek yazı tipi kullanacaktır.

### Sistem yazı tiplerinin önceliğini değiştirebilir miyim?
Sistem yazı tipleri her zaman varsayılan olarak dahil edilir, ancak bunların önceliklerini özel yazı tipi klasörlerinize göre ayarlayabilirsiniz.

### Özel yazı tipi klasörleri için ağ yollarını kullanmak mümkün mü?
Evet, ağ yollarını özel yazı tipi klasörleri olarak belirleyerek yazı tipi kaynaklarını bir ağ konumunda merkezileştirmenize olanak tanıyabilirsiniz.
---
title: Dipnot ve Son Not Konumunu Ayarlama
linktitle: Dipnot ve Son Not Konumunu Ayarlama
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı adım adım kılavuzla Aspose.Words for .NET kullanarak Word belgelerinde dipnot ve sonnot konumlarını nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---
## giriiş

Word belgeleriyle çalışıyorsanız ve dipnotları ve sonnotları etkili bir şekilde yönetmeniz gerekiyorsa Aspose.Words for .NET, başvuracağınız kitaplıktır. Bu eğitim, Aspose.Words for .NET'i kullanarak bir Word belgesinde dipnot ve sonnot konumlarını ayarlama konusunda size yol gösterecektir. Takip edilmesini ve uygulanmasını kolaylaştırmak için her adımı parçalara ayıracağız.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET Kütüphanesi: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
- Visual Studio: Herhangi bir güncel sürüm düzgün çalışacaktır.
- Temel C# Bilgisi: Temelleri anlamak, kolayca takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle C# projenize gerekli ad alanlarını içe aktarın:

```csharp
using System;
using Aspose.Words;
```

## Adım 1: Word Belgesini Yükleyin

Başlamak için Word belgenizi Aspose.Words Belgesi nesnesine yüklemeniz gerekir. Bu, belgenin içeriğini değiştirmenize olanak tanır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Bu kodda değiştirin`"YOUR DOCUMENT DIRECTORY"`belgenizin bulunduğu gerçek yolla.

## Adım 2: Dipnot Konumunu Ayarlayın

Daha sonra dipnotların konumunu ayarlayacaksınız. Aspose.Words for .NET, dipnotları sayfanın altına veya metnin altına yerleştirmenize olanak tanır.

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
```

 Burada dipnotları metnin altında görünecek şekilde ayarladık. Bunları sayfanın alt kısmında tercih ederseniz, şunu kullanın:`FootnotePosition.BottomOfPage`.

## 3. Adım: Son Not Konumunu Ayarlayın

Benzer şekilde son notların konumunu da ayarlayabilirsiniz. Son notlar bölümün sonuna veya belgenin sonuna yerleştirilebilir.

```csharp
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

 Bu örnekte, her bölümün sonuna son notlar yerleştirilmiştir. Bunları belgenin sonuna yerleştirmek için şunu kullanın:`EndnotePosition.EndOfDocument`.

## Adım 4: Belgeyi Kaydedin

Son olarak değişiklikleri uygulamak için belgeyi kaydedin. Çıktı belgesi için doğru dosya yolunu ve adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Bu satır, değiştirilen belgeyi belirttiğiniz dizine kaydeder.

## Çözüm

Adımları öğrendikten sonra Aspose.Words for .NET'i kullanarak Word belgelerinde dipnot ve sonnot konumlarını ayarlamak çok kolaydır. Bu kılavuzu izleyerek belgelerinizi ihtiyaçlarınıza uyacak şekilde özelleştirebilir, dipnotların ve son notların tam olarak istediğiniz yere konumlandırılmasını sağlayabilirsiniz.

## SSS'ler

### Ayrı ayrı dipnotlar veya son notlar için farklı konumlar ayarlayabilir miyim?

Hayır, Aspose.Words for .NET bir belgedeki tüm dipnotların ve sonnotların konumunu eşit şekilde ayarlar.

### Aspose.Words for .NET, Word belgelerinin tüm sürümleriyle uyumlu mu?

Evet, Aspose.Words for .NET, DOC, DOCX, RTF ve daha fazlasını içeren çok çeşitli Word belge formatlarını destekler.

### Aspose.Words for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?

Aspose.Words for .NET, .NET uygulamaları için tasarlanmıştır, ancak onu C#, VB.NET vb. gibi .NET destekli herhangi bir dille kullanabilirsiniz.

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?

 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Words for .NET için daha ayrıntılı belgeleri nerede bulabilirim?

 Detaylı dokümantasyon mevcut[Burada](https://reference.aspose.com/words/net/).
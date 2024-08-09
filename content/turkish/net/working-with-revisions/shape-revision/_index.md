---
title: Şekil Revizyonu
linktitle: Şekil Revizyonu
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı kılavuzla Aspose.Words for .NET kullanarak Word belgelerindeki şekil revizyonlarını nasıl gerçekleştireceğinizi öğrenin. Değişiklikleri izleme, şekil ekleme ve daha birçok konuda uzmanlaşın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/shape-revision/
---
## giriiş

Word belgelerini programlı olarak düzenlemek, özellikle şekillerin işlenmesi söz konusu olduğunda göz korkutucu bir görev olabilir. İster rapor oluşturuyor olun, ister şablon tasarlıyor olun, ister yalnızca belge oluşturmayı otomatikleştiriyor olun, şekil revizyonlarını takip etme ve yönetme yeteneği çok önemlidir. Aspose.Words for .NET, bu süreci sorunsuz ve verimli kılmak için güçlü bir API sunuyor. Bu eğitimde, belgelerinizi kolaylıkla yönetebilmeniz için gerekli araçlara ve bilgiye sahip olmanızı sağlayacak şekilde Word belgelerindeki şekilleri düzeltmenin ayrıntılarına gireceğiz.

## Önkoşullar

Koda dalmadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: Aspose.Words kütüphanesinin kurulu olduğundan emin olun. Yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio gibi bir geliştirme ortamı kurmuş olmanız gerekir.
- Temel C# Anlayışı: C# programlama diline aşinalık ve nesne yönelimli programlamanın temel kavramları.
- Word Belgesi: Üzerinde çalışabileceğiniz bir Word belgesi veya eğitim sırasında bir tane oluşturabilirsiniz.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bunlar bize Word belgelerini ve şekillerini işlemek için gereken sınıflara ve yöntemlere erişim sağlayacaktır.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 1. Adım: Belge Dizininizi Ayarlama

Şekillerle çalışmaya başlamadan önce belge dizinimizin yolunu tanımlamamız gerekiyor. Değiştirilen belgelerimizi buraya kaydedeceğiz.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge Oluşturma

Şekilleri ekleyip değiştireceğimiz yeni bir Word belgesi oluşturalım.

```csharp
Document doc = new Document();
```

## Adım 3: Satır İçi Şekil Ekleme

Revizyonları izlemeden belgemize satır içi bir şekil ekleyerek başlayacağız. Satır içi şekil, metinle birlikte akan şekildir.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 4. Adım: Düzeltmeleri İzlemeye Başlama

Dokümanımızdaki değişiklikleri takip etmek için revizyon takibini etkinleştirmemiz gerekmektedir. Bu, şekillerde yapılan değişiklikleri tanımlamak için gereklidir.

```csharp
doc.StartTrackRevisions("John Doe");
```

## Adım 5: Düzeltmelerle Başka Bir Şekil Ekleme

Artık revizyon izleme etkinleştirildiğine göre başka bir şekil ekleyelim. Bu sefer herhangi bir değişiklik takip edilecek.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Adım 6: Şekilleri Alma ve Değiştirme

Belgedeki tüm şekilleri alabilir ve gerektiği gibi değiştirebiliriz. Burada şekilleri alıp ilkini kaldıracağız.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## Adım 7: Belgeyi Kaydetme

Değişikliklerimizi yaptıktan sonra belgeyi kaydetmemiz gerekiyor. Bu, tüm revizyonların ve değişikliklerin saklanmasını sağlar.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## Adım 8: Şekil Taşıma Revizyonlarını İşleme

Bir şekil taşındığında Aspose.Words bunu revizyon olarak izler. Bu, şeklin iki örneğinin olacağı anlamına gelir: biri orijinal konumunda, diğeri yeni konumunda.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak Word belgelerindeki şekil revizyonlarını nasıl gerçekleştireceğinizi başarıyla öğrendiniz. İster belge şablonlarını yönetiyor olun, ister raporları otomatikleştiriyor olun, ister sadece değişiklikleri takip ediyor olun, bu beceriler çok değerlidir. Bu adım adım kılavuzu takip ederek yalnızca temel konularda uzmanlaşmakla kalmadınız, aynı zamanda daha gelişmiş belge işleme teknikleri hakkında da fikir sahibi oldunuz.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin C# kullanarak Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır.

### Bir Word belgesindeki diğer öğelerde yapılan değişiklikleri izleyebilir miyim?
Evet, Aspose.Words for .NET; metin, tablolar ve daha fazlası dahil olmak üzere çeşitli öğelerde yapılan değişikliklerin izlenmesini destekler.

### Aspose.Words for .NET'in ücretsiz deneme sürümünü nasıl edinebilirim?
 Aspose.Words for .NET'in ücretsiz deneme sürümünü edinebilirsiniz[Burada](https://releases.aspose.com/).

### Revizyonları programlı olarak kabul etmek veya reddetmek mümkün mü?
Evet, Aspose.Words for .NET, revizyonları programlı olarak kabul etmek veya reddetmek için yöntemler sağlar.

### Aspose.Words for .NET'i C#'ın yanı sıra diğer .NET dilleriyle de kullanabilir miyim?
Kesinlikle! Aspose.Words for .NET, VB.NET ve F# da dahil olmak üzere herhangi bir .NET diliyle kullanılabilir.
---
title: Word Belgesinde Toc Sekmesi Duraklarını Değiştirme
linktitle: Word Belgesinde Toc Sekmesi Duraklarını Değiştirme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki TOC sekme duraklarını nasıl değiştireceğinizi öğrenin. Bu adım adım kılavuz, profesyonel görünümlü bir İçindekiler oluşturmanıza yardımcı olacaktır.
type: docs
weight: 10
url: /tr/net/programming-with-table-of-content/change-toc-tab-stops/
---
## giriiş

Word belgelerinizdeki İçindekiler Tablosunu (TOC) nasıl canlandıracağınızı hiç merak ettiniz mi? Belki de bu profesyonel dokunuş için bu sekme duraklarının mükemmel şekilde hizalanmasını istiyorsunuz. Doğru yerdesiniz! Bugün Aspose.Words for .NET'i kullanarak TOC sekme duraklarını nasıl değiştirebileceğinizi derinlemesine inceliyoruz. Burada kalın ve TOC'nizin şık ve düzenli görünmesini sağlayacak tüm bilgi birikimiyle ayrılacağınıza söz veriyorum.

## Önkoşullar

Başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Yapabilirsin[buradan indir](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir C# uyumlu IDE.
3. Bir Word Belgesi: Özellikle, içindekiler tablosunu içeren belge.

Bunların hepsini anladın mı? Mükemmel! Hadi yuvarlanalım.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Bu, bir projeye başlamadan önce aletlerinizi paketlemeye benzer.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Bu süreci basit, sindirilebilir adımlara ayıralım. Belgeyi yükleme, İçindekiler sekmesi duraklarını değiştirme ve güncellenen belgeyi kaydetme işlemlerini gerçekleştireceğiz.

## 1. Adım: Belgeyi Yükleyin

Neden? Değiştirmek istediğimiz TOC'yi içeren Word belgesine erişmemiz gerekiyor.

Nasıl? İşte başlamanıza yardımcı olacak basit bir kod pasajı:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// İçindekiler tablosunu içeren belgeyi yükleyin
Document doc = new Document(dataDir + "Table of contents.docx");
```

Belgenizin bir pastaya benzediğini ve biraz krema eklemek üzere olduğumuzu hayal edin. İlk adım pastayı kutudan çıkarmak.

## Adım 2: İçindekiler Paragraflarını Tanımlayın

Neden? İçindekiler Tablosunu oluşturan paragrafları tam olarak belirlememiz gerekiyor. 

Nasıl? Paragraflar arasında dolaşın ve stillerini kontrol edin:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // İçindekiler paragrafı bulundu
    }
}
```

Bunu, arkadaşlarınızı bulmak için bir kalabalığı taramak gibi düşünün. Burada, TOC girişleri olarak stilize edilen paragrafları arıyoruz.

## 3. Adım: Sekme Duraklarını Değiştirin

Neden? Sihir yapılan yer burasıdır. Sekme duraklarını değiştirmek, İçindekiler Tablonuza daha temiz bir görünüm kazandırır.

Nasıl? Mevcut sekme durağını kaldırın ve değiştirilmiş bir konuma yenisini ekleyin:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

Bu, oturma odanızdaki mobilyaları tam istediğiniz gibi olana kadar ayarlamaya benziyor. Mükemmellik için bu sekme duraklarını ayarlıyoruz.

## Adım 4: Değiştirilen Belgeyi Kaydedin

Neden? Tüm sıkı çalışmanızın kaydedildiğinden ve görüntülenebildiğinden veya paylaşılabildiğinden emin olmak için.

Nasıl? Orijinali olduğu gibi korumak için belgeyi yeni bir adla kaydedin:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Ve işte! İçindekiler Tablonuzda artık sekme durakları tam olarak istediğiniz yerde bulunuyor.

## Çözüm

Aspose.Words for .NET kullanarak bir Word belgesindeki TOC sekme duraklarını değiştirmek, belgeyi parçalara ayırdığınızda çok kolaydır. Belgenizi yükleyerek, içindekiler paragraflarını tanımlayarak, sekme duraklarını değiştirerek ve belgeyi kaydederek şık ve profesyonel bir görünüm elde edebilirsiniz. Unutmayın, alıştırma mükemmelleştirir, bu nedenle tam olarak istediğiniz düzeni elde etmek için farklı sekme durağı konumlarını denemeye devam edin.

## SSS'ler

### Farklı TOC düzeyleri için sekme duraklarını ayrı ayrı değiştirebilir miyim?
Evet yapabilirsin! Sadece her bir TOC seviyesini (Toc1, Toc2, vb.) kontrol edin ve buna göre ayarlayın.

### Belgemde birden fazla İçindekiler varsa ne olur?
Kod, İçindekiler stilindeki tüm paragrafları tarar, böylece belgede bulunan tüm İçindekiler'i değiştirir.

### Bir TOC girişine birden fazla sekme durağı eklemek mümkün mü?
 Kesinlikle! ayarlayarak gerektiği kadar sekme durağı ekleyebilirsiniz.`para.ParagraphFormat.TabStops` Toplamak.

### Sekme durağı hizalamasını ve kılavuz stilini değiştirebilir miyim?
Evet, yeni bir sekme durağı eklerken farklı hizalamalar ve lider stilleri belirtebilirsiniz.

### Aspose.Words for .NET'i kullanmak için lisansa ihtiyacım var mı?
 Evet, Aspose.Words for .NET'i deneme süresinin ötesinde kullanmak için geçerli bir lisansa ihtiyacınız var. Alabilirsin[geçici lisans](https://purchase.aspose.com/temporary-license/) veya[al bir tane](https://purchase.aspose.com/buy).
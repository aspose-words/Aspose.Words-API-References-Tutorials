---
title: Word Belgesinde Toc Sekmesi Duraklarını Değiştirme
linktitle: Word Belgesinde Toc Sekmesi Duraklarını Değiştirme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içindekiler sekmelerini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmaya, düzenlemeye ve işlemeye yönelik güçlü bir kitaplıktır. Aspose.Words'ün sunduğu işlevler arasında, bir Word belgesinin içindekiler tablosunda kullanılan sekmeleri değiştirme olanağı da vardır. Bu kılavuzda, bir belgenin içindekiler tablosundaki sekmeleri değiştirmek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgeleriyle Kelime İşlemeyi kolay ve verimli hale getiren popüler bir kütüphanedir. İçindekiler sekmelerini değiştirmek de dahil olmak üzere, Word belgelerini oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar.

## İçindekiler tablosunu içeren belgeyi yükleme

İlk adım, değiştirmek istediğiniz içindekiler tablosunu içeren Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Bu örnekte, belgeler dizininde bulunan "İçindekiler tablosu.docx" belgesini yüklüyoruz.

## İçindekiler tablosundaki sekmeleri değiştirme

Belge yüklendikten sonra belgenin her paragrafını inceliyoruz ve İçindekiler Tablosu (TOC) sonuç stillerini kullanarak biçimlendirilip biçimlendirilmediğini kontrol ediyoruz. Eğer öyleyse, sayfa numaralarını hizalamak için kullanılan sekmeleri değiştiririz. İşte nasıl:

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

Bu örnekte, belgedeki her paragrafta döngü oluşturmak için bir döngü kullanıyoruz. Daha sonra paragrafın İçindekiler Tablosu Sonucu (TOC) stilleri kullanılarak biçimlendirilip biçimlendirilmediğini kontrol ederiz. Öyleyse, bu paragrafta kullanılan ilk sekmeye erişiriz ve eski sekmeyi kaldırarak ve değiştirilmiş konuma sahip yeni bir sekme ekleyerek onu değiştiririz.

## Değiştirilen belgeyi kaydet

İçindekiler tablosundaki sekmelerde gerekli değişiklikleri yaptıktan sonra, değiştirilen belgeyi Document sınıfının Kaydet yöntemini kullanarak kaydedebilirsiniz. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Bu örnekte değiştirilen belgeyi "WorkingWithTableOfContent.ChangeTocTabStops.docx" olarak kaydediyoruz.

### Aspose.Words for .NET ile "İçindekiler Sekmelerini Düzenle" özelliği için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// İçindekiler tablosunu içeren belgeyi yükleyin
Document doc = new Document(dataDir + "Table of contents.docx");

// İçindekiler tablosunun sekmelerini değiştirin
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

// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Çözüm

Bu kılavuzda, sağlanan C# kaynak kodunu kullanarak bir Word belgesinin içindekiler tablosundaki sekmeleri değiştirmek için Aspose.Words for .NET'in nasıl kullanılacağını ele aldık. Verilen adımları takip ederek C# uygulamanızda Word belgelerinizdeki içindekiler sekmelerini kolaylıkla özelleştirebilirsiniz. Aspose.Words, belgelerinizin stilleri ve formatlarıyla çalışmak için muazzam bir esneklik ve güç sunarak çekici ve profesyonel Word belgeleri oluşturmanıza olanak tanır.

### Word belgesindeki sekme duraklarını değiştirmeyle ilgili SSS

#### S: Aspose.Words for .NET'teki "Word Belgesindeki Toc Sekme Duraklarını Değiştir" işlevinin amacı nedir?

C: Aspose.Words for .NET'teki "Word Belgesindeki Sekme Duraklarını Değiştir" işlevi, bir Word belgesinin içindekiler tablosunda kullanılan sekme duraklarını değiştirmenize olanak tanır. İçindekiler tablosundaki sayfa numaralarının ve karşılık gelen başlıkların hizalamasını ve konumlandırılmasını özelleştirmenizi sağlar.

#### S: Aspose.Words for .NET nedir?

C: Aspose.Words for .NET, .NET uygulamalarında Word belgeleriyle Kelime İşleme için tasarlanmış güçlü bir kütüphanedir. C# veya diğer .NET dillerini kullanarak Word belgelerini programlı olarak oluşturmak, düzenlemek, değiştirmek ve dönüştürmek için kapsamlı özellikler sağlar.

#### S: Aspose.Words for .NET kullanarak içindekiler tablosu içeren bir Word belgesini nasıl yüklerim?

 C: Aspose.Words for .NET'i kullanarak içindekiler tablosu içeren bir Word belgesini yüklemek için`Document` sınıf ve onun yapıcısı. Belgenin dosya yolunu sağlayarak onu bir klasöre yükleyebilirsiniz.`Document` nesne. İşte bir örnek:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Bu kod parçacığı, belirtilen dizinde bulunan "İçindekiler tablosu.docx" belgesini yükler.

#### S: İçindekiler tablosunda kullanılan sekmeleri Aspose.Words for .NET kullanarak nasıl değiştirebilirim?

 C: Belge yüklendikten sonra belgenin her paragrafını yineleyebilir ve İçindekiler Tablosu (TOC) sonuç stillerini kullanarak biçimlendirilip biçimlendirilmediğini kontrol edebilirsiniz. Bir paragraf İçindekiler stili olarak biçimlendirilmişse sayfa numaralarını hizalamak için kullanılan sekmeleri değiştirebilirsiniz. Aspose.Words for .NET'te aşağıdakilere erişebilirsiniz:`ParagraphFormat` Sekme duraklarını almak ve değiştirmek için her paragrafın özelliği. İşte bir örnek:

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

Bu kodda döngü, belgedeki her paragraf boyunca yinelenir. Bir paragrafın içindekiler stili varsa, o paragrafta kullanılan ilk sekme durağına erişir, onu kaldırır ve değiştirilmiş konuma sahip yeni bir sekme durağı ekler.

#### S: Aspose.Words for .NET'i kullanarak içindekiler tablosundaki birden fazla seviyeye ait sekmeleri değiştirebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak içindekiler tablosundaki birden fazla seviyeye ait sekmeleri değiştirebilirsiniz. Her paragrafı yineleyerek ve İçindekiler stilini kontrol ederek, her seviyenin sekmelerini ayrı ayrı değiştirebilirsiniz. İçindekiler tablosunun istediğiniz seviyesine erişebilir ve sekme duraklarını buna göre ayarlayabilirsiniz.

#### S: Aspose.Words for .NET kullanarak içindekiler tablosundaki sekmeleri değiştirdikten sonra değiştirilen belgeyi nasıl kaydederim?

 C: İçindekiler bölümündeki sekmelerde gerekli değişiklikleri yaptıktan sonra, değiştirilen belgeyi aşağıdaki düğmeyi kullanarak kaydedebilirsiniz:`Save` yöntemi`Document` sınıf. Çıktı belgesi için istenen dosya yolunu ve adını parametre olarak sağlayın.`Save` yöntem. İşte bir örnek:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Bu kod, değiştirilen belgeyi "WorkingWithTableOfContent.ChangeTocTabStops.docx" olarak kaydeder.

#### S: Aspose.Words for .NET'i kullanarak içindekiler tablosunun diğer yönlerini özelleştirebilir miyim?

C: Evet, Aspose.Words for .NET ile içindekiler tablosunun çeşitli yönlerini özelleştirebilirsiniz. Sekmeleri değiştirmenin yanı sıra, içindekiler tablosu girişlerinin ve sayfa numaralarının yazı tipi stillerini, boyutunu, hizalamasını ve diğer biçimlendirme özelliklerini değiştirebilirsiniz. Ayrıca ilgili başlıkların girintisini, aralığını ve formatını da ayarlayabilirsiniz.

#### Q:. Aspose.Words for .NET kullanarak içindekiler tablosunun sekme hizalamasını ve lider karakterlerini değiştirebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak içindekiler tablosunun sekme hizalamasını ve lider karakterlerini değiştirebilirsiniz. Sekme duraklarına erişerek ve bunların hizalama ve lider özelliklerini ayarlayarak, içindekiler tablosundaki sayfa numaralarının ve karşılık gelen başlıkların hizalamasını ve görsel görünümünü kontrol edebilirsiniz.

#### S: Aspose.Words for .NET, Word belgelerinde diğer stillerin ve formatların değiştirilmesini destekliyor mu?

C: Evet, Aspose.Words for .NET, Word belgelerindeki çeşitli stilleri ve formatları değiştirmek için kapsamlı destek sağlar. Paragraflar, başlıklar, tablolar, listeler ve daha fazlası gibi farklı öğelerin stillerini değiştirmenize olanak tanır. İhtiyaçlarınıza göre yazı tiplerini, renkleri, hizalamayı, girintiyi, aralığı ve diğer biçimlendirme özelliklerini değiştirebilirsiniz.

#### S: Mevcut bir Word belgesindeki içindekiler tablosundaki sekmeleri Aspose.Words for .NET kullanarak değiştirebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak mevcut bir Word belgesindeki içindekiler tablosundaki sekmeleri değiştirebilirsiniz. Belgeyi yükleyerek, paragraflar arasında yineleyerek ve sekme duraklarında gerekli değişiklikleri yaparak içindekiler tablosundaki sekmeleri güncelleyebilirsiniz. Son olarak değişiklikleri uygulamak için belgeyi kaydedin.
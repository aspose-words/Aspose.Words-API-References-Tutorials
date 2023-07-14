---
title: Word Belgesinde Toc Sekme Duraklarını Değiştirme
linktitle: Word Belgesinde Toc Sekme Duraklarını Değiştirme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içindekiler tablosu sekmelerini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmak, düzenlemek ve değiştirmek için güçlü bir kitaplıktır. Aspose.Words tarafından sunulan işlevler arasında, bir Word belgesinin içindekiler tablosunda kullanılan sekmeleri değiştirme olasılığı vardır. Bu kılavuzda, bir belgenin içindekiler tablosundaki sekmeleri değiştirmek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, Word belgeleriyle Kelime İşlemeyi kolay ve verimli hale getiren popüler bir kütüphanedir. İçindekiler sekmelerini değiştirmek de dahil olmak üzere Word belgeleri oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar.

## İçindekiler tablosunu içeren belgeyi yükleme

İlk adım, değiştirmek istediğiniz içindekiler tablosunu içeren Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Bu örnekte, belgeler dizininde bulunan "İçindekiler.docx" belgesini yüklüyoruz.

## İçindekiler tablosundaki sekmeleri değiştirme

Belge yüklendikten sonra, belgenin her paragrafını inceliyoruz ve İçindekiler Tablosu (TOC) sonuç stilleri kullanılarak biçimlendirilip biçimlendirilmediğini kontrol ediyoruz. Öyleyse, sayfa numaralarını hizalamak için kullanılan sekmeleri değiştiririz. İşte nasıl:

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

Bu örnekte, belgedeki her paragrafta dolaşmak için bir döngü kullanıyoruz. Ardından, paragrafın İçindekiler Tablosu Sonuç (TOC) stilleri kullanılarak biçimlendirilip biçimlendirilmediğini kontrol ederiz. Öyleyse, bu paragrafta kullanılan ilk sekmeye erişir ve eski sekmeyi kaldırarak ve değiştirilmiş bir konuma sahip yeni bir sekme ekleyerek değiştiririz.

## Değiştirilen belgeyi kaydet

İçindekiler tablosundaki sekmelerde gerekli değişiklikleri yaptıktan sonra, değiştirilen belgeyi Document sınıfının Save yöntemini kullanarak kaydedebilirsiniz. İşte bir örnek :

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

// İçindekiler tablosunun sekmelerini değiştirme
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

Bu kılavuzda, sağlanan C# kaynak kodunu kullanarak bir Word belgesinin içindekiler tablosundaki sekmeleri değiştirmek için Aspose.Words for .NET'in nasıl kullanılacağını ele aldık. Sağlanan adımları izleyerek, C# uygulamanızdaki Word belgelerinizdeki içindekiler sekmelerini kolayca özelleştirebilirsiniz. Aspose.Words, çekici ve profesyonel Word belgeleri oluşturmanıza izin vererek, belgelerinizin stilleri ve biçimlendirmesiyle çalışmak için muazzam bir esneklik ve güç sunar.

### Word belgesinde toc sekmesi duraklarını değiştirmek için SSS

#### S: Aspose.Words for .NET'teki "Word Belgesinde Toc Sekme Duraklarını Değiştir" işlevinin amacı nedir?

A: Aspose.Words for .NET'teki "Word Belgesinde Toc Sekme Duraklarını Değiştir" işlevi, bir Word belgesinin içindekiler tablosunda kullanılan sekme duraklarını değiştirmenize olanak tanır. İçindekiler tablosundaki sayfa numaralarının ve karşılık gelen başlıkların hizalamasını ve konumunu özelleştirmenizi sağlar.

#### S: Aspose.Words for .NET nedir?

Y: Aspose.Words for .NET, .NET uygulamalarında Word belgeleriyle Kelime İşleme için tasarlanmış güçlü bir kitaplıktır. C# veya diğer .NET dillerini kullanarak programlı olarak Word belgeleri oluşturmak, düzenlemek, işlemek ve dönüştürmek için kapsamlı özellikler sağlar.

#### S: İçindekiler tablosu içeren bir Word belgesini Aspose.Words for .NET kullanarak nasıl yüklerim?

 Y: Aspose.Words for .NET kullanarak içindekiler tablosu içeren bir Word belgesini yüklemek için`Document` sınıf ve yapıcısı. Belgenin dosya yolunu sağlayarak, onu bir dosyaya yükleyebilirsiniz.`Document` nesne. İşte bir örnek:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Bu kod parçacığı, belirtilen dizinde bulunan "İçindekiler Tablosu.docx" belgesini yükler.

#### S: İçindekiler tablosunda kullanılan sekmeleri Aspose.Words for .NET kullanarak nasıl değiştirebilirim?

 Y: Belge yüklendikten sonra, belgenin her bir paragrafını tekrarlayabilir ve İçindekiler Tablosu (TOC) sonuç stilleri kullanılarak biçimlendirilip biçimlendirilmediğini kontrol edebilirsiniz. Bir paragraf içindekiler stili olarak biçimlendirilmişse, sayfa numaralarını hizalamak için kullanılan sekmeleri değiştirebilirsiniz. Aspose.Words for .NET'te şunlara erişebilirsiniz:`ParagraphFormat` sekme duraklarını almak ve değiştirmek için her paragrafın özelliği. İşte bir örnek:

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

Bu kodda, döngü belgedeki her paragrafta yinelenir. Bir paragrafın İçindekiler stili varsa, o paragrafta kullanılan ilk sekme durağına erişir, onu kaldırır ve değiştirilmiş bir konuma sahip yeni bir sekme durağı ekler.

#### S: Aspose.Words for .NET'i kullanarak içindekiler tablosundaki birden çok düzey için sekmeleri değiştirebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak içindekiler tablosunda birden çok düzey için sekmeleri değiştirebilirsiniz. Her paragrafı yineleyerek ve İçindekiler stilini kontrol ederek, her seviye için sekmeleri ayrı ayrı değiştirebilirsiniz. İçindekiler tablosunun istediğiniz seviyesine erişebilir ve sekme duraklarını buna göre ayarlayabilirsiniz.

#### S: Aspose.Words for .NET kullanarak içindekiler tablosundaki sekmeleri değiştirdikten sonra değiştirilen belgeyi nasıl kaydedebilirim?

 A: İçindekiler tablosundaki sekmelerde gerekli değişiklikleri yaptıktan sonra, değiştirilen belgeyi kullanarak kaydedebilirsiniz.`Save` yöntemi`Document` sınıf. Çıktı belgesi için istenen dosya yolunu ve adını parametre olarak sağlayın.`Save` yöntem. İşte bir örnek:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Bu kod, değiştirilen belgeyi "WorkingWithTableOfContent.ChangeTocTabStops.docx" olarak kaydeder.

#### S: İçindekiler tablosunun diğer özelliklerini Aspose.Words for .NET kullanarak özelleştirebilir miyim?

C: Evet, Aspose.Words for .NET ile içindekiler tablosunun çeşitli yönlerini özelleştirebilirsiniz. Sekmeleri değiştirmenin dışında, içindekiler tablosu girişlerinin ve sayfa numaralarının yazı tipi stillerini, boyutunu, hizalamasını ve diğer biçimlendirme özelliklerini değiştirebilirsiniz. Ek olarak, karşılık gelen başlıkların girintisini, aralığını ve biçimlendirmesini ayarlayabilirsiniz.

#### Q:. Aspose.Words for .NET kullanarak içindekiler için sekme hizalamasını ve lider karakterleri değiştirebilir miyim?

C: Evet, içindekiler için sekme hizalamasını ve lider karakterleri Aspose.Words for .NET'i kullanarak değiştirebilirsiniz. Sekme duraklarına erişip hizalama ve lider özelliklerini ayarlayarak, içindekiler tablosunda sayfa numaralarının ve karşılık gelen başlıkların hizalamasını ve görsel görünümünü kontrol edebilirsiniz.

#### S: Aspose.Words for .NET, Word belgelerinde diğer stilleri ve biçimlendirmeyi değiştirmeyi destekliyor mu?

C: Evet, Aspose.Words for .NET, Word belgelerinde çeşitli stilleri ve biçimlendirmeyi değiştirmek için kapsamlı destek sağlar. Paragraflar, başlıklar, tablolar, listeler ve daha fazlası gibi farklı öğelerin stillerini değiştirmenize olanak tanır. Gereksinimlerinize göre yazı tiplerini, renkleri, hizalamayı, girintiyi, aralığı ve diğer biçimlendirme özelliklerini değiştirebilirsiniz.

#### S: Aspose.Words for .NET kullanarak mevcut bir Word belgesindeki içindekiler tablosundaki sekmeleri değiştirebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak mevcut bir Word belgesindeki içindekiler tablosundaki sekmeleri değiştirebilirsiniz. Belgeyi yükleyerek, paragrafları yineleyerek ve sekme duraklarında gerekli değişiklikleri yaparak içindekiler tablosundaki sekmeleri güncelleyebilirsiniz. Son olarak, değişiklikleri uygulamak için belgeyi kaydedin.
---
title: Toc Sekme Duraklarını Değiştir
linktitle: Toc Sekme Duraklarını Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içindekiler tablosu sekmelerini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmak, düzenlemek ve değiştirmek için güçlü bir kitaplıktır. Aspose.Words tarafından sunulan işlevler arasında, bir Word belgesinin içindekiler tablosunda kullanılan sekmeleri değiştirme olasılığı vardır. Bu kılavuzda, bir belgenin içindekiler tablosundaki sekmeleri değiştirmek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, Word belgeleriyle çalışmayı kolay ve verimli hale getiren popüler bir kitaplıktır. İçindekiler sekmelerini değiştirmek de dahil olmak üzere Word belgeleri oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar.

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
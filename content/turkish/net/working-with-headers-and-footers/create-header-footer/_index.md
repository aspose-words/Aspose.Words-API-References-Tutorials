---
title: Üstbilgi Altbilgisi Oluştur
linktitle: Üstbilgi Altbilgisi Oluştur
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerine üstbilgi ve altbilgileri nasıl ekleyeceğinizi ve özelleştireceğinizi öğrenin. Bu adım adım kılavuz, profesyonel belge biçimlendirmeyi sağlar.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/create-header-footer/
---

Belgelerinize üstbilgi ve altbilgi eklemek, belgelerinizin profesyonelliğini ve okunabilirliğini artırabilir. Aspose.Words for .NET ile Word belgeleriniz için kolayca üstbilgi ve altbilgi oluşturabilir ve özelleştirebilirsiniz. Bu eğitimde, bu özellikleri sorunsuz bir şekilde uygulayabilmenizi sağlamak için süreç boyunca size adım adım yol göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET: Buradan indirip yükleyin.[İndirme: {link](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Kodunuzu yazmak ve çalıştırmak için Visual Studio gibi.
- Temel C# Bilgisi: C# ve .NET çerçevesinin anlaşılması.
- Örnek Belge: Üstbilgileri ve altbilgileri uygulamak veya öğreticide gösterildiği gibi yeni bir tane oluşturmak için örnek bir belge.

## Ad Alanlarını İçe Aktar

Aspose.Words sınıflarına ve yöntemlerine erişmek için öncelikle gerekli ad alanlarını içe aktarmanız gerekir.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## Adım 1: Belge Dizinini Tanımlayın

Belgenizin kaydedileceği dizini tanımlayın. Bu, yolu etkili bir şekilde yönetmenize yardımcı olur.

```csharp
// Belgeler dizininin yolu
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## Adım 2: Yeni Bir Belge Oluşturun

 Yeni bir belge oluşturun ve`DocumentBuilder` İçerik eklenmesini kolaylaştırmak için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Sayfa Yapısını Yapılandırın

İlk sayfanın farklı bir üstbilgiye/altbilgiye sahip olup olmayacağı da dahil olmak üzere sayfa ayarlarını yapın.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## Adım 4: İlk Sayfaya Başlık Ekleme

İlk sayfanın başlık bölümüne gidin ve başlık metnini yapılandırın.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## Adım 5: Birincil Başlık Ekleme

Birincil başlık bölümüne gidin ve bir resim ve metin ekleyin.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Başlığa bir resim ekleyin
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## Adım 6: Birincil Altbilgi Ekleme

Birincil altbilgi bölümüne gidin ve altbilgi içeriğini biçimlendirmek için bir tablo oluşturun.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Sayfa numaralandırması ekle
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();
```

## 7. Adım: İçerik ve Sayfa Sonu Ekleme

Belgenin sonuna gidin, sayfa sonu ekleyin ve farklı sayfa ayarlarıyla yeni bir bölüm oluşturun.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## Adım 8: Önceki Bölümden Üstbilgileri ve Altbilgileri Kopyalayın

Önceki bir bölümdeki üstbilgileri ve altbilgileri yeniden kullanmak istiyorsanız bunları kopyalayın ve gerekli değişiklikleri uygulayın.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## Çözüm

Bu adımları izleyerek Aspose.Words for .NET'i kullanarak Word belgelerinize etkili bir şekilde üstbilgi ve altbilgi ekleyebilir ve özelleştirebilirsiniz. Bu, belgenizin görünümünü ve profesyonelliğini geliştirerek onu daha okunabilir ve ilgi çekici hale getirir.

## SSS

### S1: Aspose.Words for .NET nedir?

Aspose.Words for .NET, geliştiricilerin .NET uygulamaları içerisinde Word belgelerini programlı olarak oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan bir kütüphanedir.

### S2: Üstbilgiye veya altbilgiye resim ekleyebilir miyim?

 Evet, üst bilgi veya alt bilgiye kolayca resim ekleyebilirsiniz.`DocumentBuilder.InsertImage` yöntem.

### S3: İlk sayfa için farklı üstbilgileri ve altbilgileri nasıl ayarlarım?

 İlk sayfa için farklı üstbilgiler ve altbilgiler ayarlayabilirsiniz.`DifferentFirstPageHeaderFooter` mülkiyeti`PageSetup` sınıf.

### S4: Aspose.Words hakkında daha fazla belgeyi nerede bulabilirim?

 Hakkında kapsamlı belgeler bulabilirsiniz.[Aspose.Words API dokümantasyon sayfası](https://reference.aspose.com/words/net/).

### S5: Aspose.Words için destek mevcut mu?

 Evet, Aspose kendi aracılığıyla destek sunuyor[destek Forumu](https://forum.aspose.com/c/words/8).

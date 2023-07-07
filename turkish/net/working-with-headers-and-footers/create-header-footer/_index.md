---
title: Üst Bilgi Alt Bilgi Oluştur
linktitle: Üst Bilgi Alt Bilgi Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinizde üst bilgileri ve alt bilgileri nasıl oluşturacağınızı öğrenin. Her sayfa için üst bilgileri ve alt bilgileri özelleştirin.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/create-header-footer/
---

Aspose.Words for .NET işlevselliğini kullanarak üst bilgiler ve alt bilgiler oluşturmak için aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz. Bu kodu kullanmadan önce Aspose.Words kütüphanesini projenize dahil ettiğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Düzenlenen belgenin kaydedileceği belgeler dizininizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: Bir belge ve bir belge oluşturucu oluşturun

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada bir örneğini oluşturuyoruz`Document` sınıf ve örneğinin bir örneği`DocumentBuilder` belgeyi manipüle etmemize ve öğeler eklememize izin verecek sınıf.

## 3. Adım: Sayfa parametrelerini ve ilk başlığı ayarlayın

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// İlk sayfanın üstbilgilerinin/altbilgilerinin diğer sayfalardan farklı olmasını isteyip istemediğimizi belirtin.
// Belirtmek için PageSetup.OddAndEvenPagesHeaderFooter özelliğini de kullanabilirsiniz.
// tek ve çift sayfalar için farklı üst bilgiler/alt bilgiler.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Başlık mesafesi dahil sayfa parametrelerini ayarlıyoruz ve ardından ana başlığa geçiyoruz (`HeaderPrimary`). Metin eklemek ve başlığı biçimlendirmek için belge oluşturucuyu kullanıyoruz.

## 4. Adım: Ana başlığa bir resim ve metin ekleyin

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Ana başlığın sol üst köşesine bir resim eklemek için belge oluşturucuyu kullanıyoruz, ardından sağa hizalanmış bir metin ekliyoruz.

## 5. Adım: Ana altbilgiye bir tablo ekleyin

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

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

builder.MoveToDocumentEnd();
```

## 6. Adım: Yeni bir sayfa ekleyin ve üst bilgileri/alt bilgileri ayarlayın

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Bu bölüm, ilk sayfa için farklı bir üstbilgi/altbilgiye ihtiyaç duymaz, belgede yalnızca bir başlık sayfasına ihtiyacımız vardır,
// ve bu sayfanın üstbilgisi/altbilgisi önceki bölümde tanımlanmıştır.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Bu bölüm, önceki bölümün üstbilgilerini/altbilgilerini varsayılan olarak görüntüler, bu bağlantıyı kesmek için currentSection.HeadersFooters.LinkToPrevious(false) öğesini çağırın,
// yeni bölüm için sayfa genişliği farklıdır, bu nedenle alt bilgi tablosu için farklı hücre genişlikleri ayarlamamız gerekir.
currentSection.HeadersFooters.LinkToPrevious(false);

//Bu bölüm için zaten var olan üst bilgileri/alt bilgileri kullanmak istiyorsak,
// ancak birkaç küçük değişiklikle üstbilgileri/altbilgileri kopyalamak mantıklı olabilir
// önceki bölümden ve gerekli değişiklikleri istediğimiz yere uygulayın.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// belgeyi kaydet
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Birincil üstbilgilerin/altbilgilerin görüneceği yeni bir sayfa oluşturmak için bir sayfa sonu ve bir bölüm sonu ekliyoruz. Yeni bölüm için parametreleri ayarlıyoruz, ardından`CopyHeadersFootersFromPreviousSection` Önceki bölümden üstbilgileri/altbilgileri kopyalama yöntemi. Son olarak ana altbilgi tablosu için uygun hücre genişliklerini ayarlayıp belgeyi kaydediyoruz.

### Aspose.Words for .NET ile üst bilgiler ve alt bilgiler oluşturmak için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// İlk sayfanın üstbilgilerinin/altbilgilerinin diğer sayfalardan farklı olmasını isteyip istemediğimizi belirtin.
// Belirtmek için PageSetup.OddAndEvenPagesHeaderFooter özelliğini de kullanabilirsiniz.
// tek ve çift sayfalar için farklı üst bilgiler/alt bilgiler.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Başlığın üst/sol köşesine konumlandırılmış bir görüntü ekleyin.
// Sayfanın üst/sol kenarlarından uzaklık 10 punto olarak ayarlanmıştır.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//Satırdaki metnin bir bölümünü (sayfa numaralandırmalı) yapmak için iki hücreli bir tablo kullanıyoruz.
// Sola hizalanacak ve metnin diğer kısmı (telif hakkı ile) sağa hizalanacak.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Geçerli sayfa numarasını ve birçok sayfayı otomatik olarak hesaplamak için PAGE ve NUMPAGES alanlarını kullanır.
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

builder.MoveToDocumentEnd();

// Birincil üstbilgilerin/altbilgilerin görüleceği ikinci bir sayfa oluşturmak için bir sayfa sonu yapın.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Bu bölüm farklı bir ilk sayfa üstbilgisine/altbilgisine ihtiyaç duymaz, belgede yalnızca bir başlık sayfasına ihtiyacımız vardır,
// ve bu sayfanın üstbilgisi/altbilgisi önceki bölümde tanımlanmıştır.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Bu bölüm, önceki bölümden üstbilgileri/altbilgileri görüntüler
// varsayılan olarak bu sayfa genişliğini iptal etmek için currentSection.HeadersFooters.LinkToPrevious(false) öğesini çağırın
// yeni bölüm için farklıdır ve bu nedenle altbilgi tablosu için farklı hücre genişlikleri ayarlamamız gerekir.
currentSection.HeadersFooters.LinkToPrevious(false);

// Bu bölüm için zaten var olan üst bilgi/alt bilgi setini kullanmak istiyorsak.
// Ancak bazı küçük değişikliklerle, üstbilgileri/altbilgileri kopyalamak uygun olabilir.
//önceki bölümden ve istediğimiz yerde gerekli değişiklikleri uygulayın.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### SSS

#### S: Aspose.Words'te belgeme nasıl başlık ekleyebilirim?

 A: Aspose.Words'te belgenize bir başlık eklemek için`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` yöntem. Bu yöntem, belgenizin ilk bölümüne bir birincil başlık ekler.

#### S: Aspose.Words'te belgeme nasıl alt bilgi ekleyebilirim?

 A: Aspose.Words'te belgenize bir alt bilgi eklemek için`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)` yöntem. Bu yöntem, belgenizin ilk bölümüne bir birincil altbilgi ekler.

#### S: Aspose.Words'te üstbilgime veya altbilgime nasıl metin ekleyebilirim?

 C: Aspose.Words'te üstbilginize veya altbilginize metin eklemek için`HeaderFooter.Paragraphs` üstbilgi veya altbilginin paragraf koleksiyonunu almak için özelliğini kullanın, ardından metninizi içeren bir paragrafı bu koleksiyona ekleyin.`ParagraphCollection.Add` yöntem.

#### S: Aspose.Words'te üstbilgi veya altbilgi içeriğini resimler ve sayfa numaralarıyla özelleştirebilir miyim?

C: Evet, Aspose.Words'te üstbilgi veya altbilgi içeriğini resimler ve sayfa numaralarıyla özelleştirebilirsiniz. gibi nesneleri kullanabilirsiniz.`Shape` gibi resimler ve nesneler eklemek için`Field` üstbilginize veya altbilginize sayfa numaraları eklemek için.

#### S: Üst bilgimdeki veya alt bilgimdeki metnin yazı tipini, boyutunu ve rengini Aspose.Words'ta değiştirebilir miyim?

 C: Evet, Aspose.Words'te üst bilgi veya alt bilginizdeki metnin yazı tipini, boyutunu ve rengini değiştirebilirsiniz. gibi metin biçimlendirme özelliklerine erişebilirsiniz.`Font` yazı tipini değiştirmek için,`Size` boyutunu ayarlamak için ve`Color` Metin rengini ayarlamak için.
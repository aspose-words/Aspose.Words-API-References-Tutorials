---
title: Üstbilgi Altbilgisi Oluştur
linktitle: Üstbilgi Altbilgisi Oluştur
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinizde üstbilgi ve altbilgileri nasıl oluşturacağınızı öğrenin. Her sayfa için üstbilgileri ve altbilgileri özelleştirin.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/create-header-footer/
---

Aspose.Words for .NET işlevini kullanarak üstbilgiler ve altbilgiler oluşturmak için aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuzu burada bulabilirsiniz. Bu kodu kullanmadan önce projenize Aspose.Words kütüphanesini eklediğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Düzenlenen belgenin kaydedileceği belge dizininize giden doğru yolu belirttiğinizden emin olun.

## Adım 2: Bir belge ve belge oluşturucu oluşturun

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada bir örneğini oluşturuyoruz`Document` sınıf ve bir örnek`DocumentBuilder` belgeyi değiştirmemize ve öğeler eklememize izin verecek sınıf.

## 3. Adım: Sayfa parametrelerini ve ilk başlığı ayarlayın

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// İlk sayfanın üstbilgilerinin/altbilgilerinin diğer sayfalardan farklı olmasını isteyip istemediğimizi belirtin.
// Ayrıca belirtmek için PageSetup.OddAndEvenPagesHeaderFooter özelliğini de kullanabilirsiniz.
// tek ve çift sayfalar için farklı üstbilgiler/altbilgiler.
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

Başlık mesafesi de dahil olmak üzere sayfa parametrelerini ayarlıyoruz ve ardından ana başlığa geçiyoruz (`HeaderPrimary`). Metin eklemek ve başlığı biçimlendirmek için belge oluşturucuyu kullanıyoruz.

## 4. Adım: Ana başlığa bir resim ve metin ekleyin

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Ana başlığın sol üst köşesine bir resim eklemek için belge oluşturucuyu kullanıyoruz, ardından sağa hizalanmış bir metin ekliyoruz.

## Adım 5: Ana altbilgiye bir tablo ekleyin

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

## 6. Adım: Yeni bir sayfa ekleyin ve üstbilgileri/altbilgileri ayarlayın

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Bu bölümün ilk sayfa için farklı bir üstbilgi/altbilgiye ihtiyacı yoktur, belgede yalnızca bir başlık sayfasına ihtiyacımız vardır,
// ve bu sayfanın üstbilgisi/altbilgisi önceki bölümde zaten tanımlanmıştı.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Bu bölüm varsayılan olarak önceki bölümün üstbilgilerini/altbilgilerini görüntüler; bu bağlantıyı kesmek için currentSection.HeadersFooters.LinkToPrecious(false) çağrısını yapın,
// yeni bölüm için sayfa genişliği farklıdır, dolayısıyla alt bilgi tablosu için farklı hücre genişlikleri ayarlamamız gerekir.
currentSection.HeadersFooters.LinkToPrevious(false);

//Bu bölüm için zaten mevcut üstbilgileri/altbilgileri kullanmak istiyorsak,
// ancak birkaç küçük değişiklikle üstbilgileri/altbilgileri kopyalamak mantıklı olabilir
// önceki bölümden ve gerekli değişiklikleri istediğimiz yere uygulayın.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Birincil üstbilgilerin/altbilgilerin görünebileceği yeni bir sayfa oluşturmak için bir sayfa sonu ve bir bölüm sonu ekliyoruz. Yeni bölümün parametrelerini ayarlıyoruz, ardından`CopyHeadersFootersFromPreviousSection` Önceki bölümdeki üstbilgileri/altbilgileri kopyalama yöntemi. Son olarak ana altbilgi tablosu için uygun hücre genişliklerini ayarlayıp belgeyi kaydediyoruz.

### Aspose.Words for .NET ile üstbilgi ve altbilgi oluşturmak için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// İlk sayfanın üstbilgilerinin/altbilgilerinin diğer sayfalardan farklı olmasını isteyip istemediğimizi belirtin.
// Ayrıca belirtmek için PageSetup.OddAndEvenPagesHeaderFooter özelliğini de kullanabilirsiniz.
// tek ve çift sayfalar için farklı üstbilgiler/altbilgiler.
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

// Üstbilginin üst/sol köşesine konumlandırılmış bir resim ekleyin.
// Sayfanın üst/sol kenarlarına olan mesafe 10 noktaya ayarlanmıştır.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//Satırdaki metnin bir bölümünü (sayfa numaralandırmayla) yapmak için iki hücreli bir tablo kullanıyoruz.
// Sola hizalanacak ve metnin diğer kısmı (telif hakkıyla birlikte) sağa hizalanacak.
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

// Birincil üstbilgilerin/altbilgilerin görüneceği ikinci bir sayfa oluşturmak için sayfa sonu yapın.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Bu bölümün farklı bir ilk sayfa üstbilgisine/altbilgisine ihtiyacı yoktur, belgede yalnızca bir başlık sayfasına ihtiyacımız vardır.
// ve bu sayfanın üstbilgisi/altbilgisi önceki bölümde zaten tanımlanmıştı.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Bu bölümde önceki bölümdeki üstbilgiler/altbilgiler görüntülenir
// Bu sayfa genişliğini iptal etmek için varsayılan olarak currentSection.HeadersFooters.LinkToPrecious(false) öğesini çağırın
// yeni bölüm için farklıdır ve bu nedenle altbilgi tablosu için farklı hücre genişlikleri ayarlamamız gerekir.
currentSection.HeadersFooters.LinkToPrevious(false);

// Bu bölüm için zaten var olan üstbilgi/altbilgi setini kullanmak istiyorsak.
// Ancak bazı küçük değişikliklerle üstbilgileri/altbilgileri kopyalamak uygun olabilir
//önceki bölümden ve gerekli değişiklikleri istediğimiz yere uygulayın.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### SSS'ler

#### S: Aspose.Words'teki belgeme nasıl başlık ekleyebilirim?

 C: Aspose.Words'te belgenize başlık eklemek için`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` yöntem. Bu yöntem, belgenizin ilk bölümüne birincil başlık ekler.

#### S: Aspose.Words'te belgeme nasıl altbilgi ekleyebilirim?

 C: Aspose.Words'te belgenize altbilgi eklemek için`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)` yöntem. Bu yöntem, belgenizin ilk bölümüne birincil altbilgi ekler.

#### S: Aspose.Words'te üst bilgi veya alt bilgime nasıl metin ekleyebilirim?

 C: Aspose.Words'te üstbilginize veya altbilginize metin eklemek için`HeaderFooter.Paragraphs` Üstbilgi veya altbilginin paragraf koleksiyonunu almak için özelliği kullanın, ardından metninizi içeren bir paragrafı bu koleksiyona ekleyin.`ParagraphCollection.Add` yöntem.

#### S: Aspose.Words'te üstbilgi veya altbilgi içeriğini görseller ve sayfa numaralarıyla özelleştirebilir miyim?

C: Evet, Aspose.Words'te üstbilgi veya altbilgi içeriğini resimler ve sayfa numaralarıyla özelleştirebilirsiniz. Gibi nesneleri kullanabilirsiniz`Shape` gibi resimler ve nesneler eklemek için`Field` Üstbilginize veya altbilginize sayfa numaraları eklemek için.

#### S: Aspose.Words'te üst bilgim veya alt bilgimdeki metnin yazı tipini, boyutunu ve rengini değiştirebilir miyim?

 C: Evet, Aspose.Words'te üst bilginizdeki veya alt bilginizdeki metnin yazı tipini, boyutunu ve rengini değiştirebilirsiniz. Aşağıdaki gibi metin biçimlendirme özelliklerine erişebilirsiniz:`Font` yazı tipini değiştirmek için,`Size` Boyutu ayarlamak için ve`Color` Metin rengini ayarlamak için.
---
title: Doğrudan Tablo Ekle
linktitle: Doğrudan Tablo Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile doğrudan bir Word belgesine tablo eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/insert-table-directly/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine doğrudan tablo eklemeyi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinize program aracılığıyla doğrudan tablo ekleyebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belge ve Tabloyu Oluşturma
Dizi ile Sözcük İşlemeyi başlatmak için yeni bir belge oluşturmamız ve diziyi başlatmamız gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document doc = new Document();

//Diziyi oluştur
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Diziyi oluşturma
Ardından, satırlar ve hücreler ekleyerek tabloyu oluşturacağız. Aşağıdaki kodu örnek olarak kullanın:

```csharp
// İlk satırı oluştur
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// İlk hücreyi oluştur
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Satırdaki ikinci hücre için hücreyi çoğalt
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Burada şununla bir satır oluşturuyoruz:`AllowBreakAcrossPages` özellik ayarlandı`true` satırlar arasında sayfa kırılmasına izin vermek için. Daha sonra renkli bir arka plana, sabit genişliğe ve belirtilen metin içeriğine sahip bir hücre oluşturuyoruz. Daha sonra sıradaki ikinci hücreyi oluşturmak için bu hücreyi çoğaltıyoruz.

## 4. Adım: Tabloyu Otomatik Sığdır
Doğru şekilde biçimlendirmek için tabloya otomatik ayarlamalar uygulayabiliriz. Aşağıdaki kodu kullanın:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Bu kod satırı, sabit sütun genişliklerine dayalı bir otomatik sığdırma uygular.

## 5. Adım:

  değiştirilmiş belge
Son olarak, değiştirilen belgeyi tablo doğrudan eklenmiş olarak kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Doğrudan Tablo Ekle için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Tablo nesnesini oluşturarak başlıyoruz. Belge nesnesini iletmemiz gerektiğini unutmayın.
	//her düğümün yapıcısına. Bunun nedeni, oluşturduğumuz her düğümün ait olması gerektiğidir.
	// bazı belgelere.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Burada bizim için satırları ve hücreleri oluşturmak için SureMinimum'u çağırabiliriz. Bu yöntem kullanılır
	// belirtilen düğümün geçerli olduğundan emin olmak için. Bu durumda, geçerli bir tablo en az bir Satır ve bir hücreye sahip olmalıdır.
	// Bunun yerine satır ve tabloyu kendimiz oluşturacağız.
	// Bir algoritma içinde bir tablo oluşturuyor olsaydık, bunu yapmanın en iyi yolu bu olurdu.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Artık herhangi bir otomatik sığdırma ayarını uygulayabiliriz.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Daha sonra tablodaki diğer hücreler ve satırlar için işlemi tekrar ederdik.
	// Mevcut hücreleri ve satırları klonlayarak da işleri hızlandırabiliriz.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak doğrudan bir Word belgesine tablo eklemeyi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, program aracılığıyla doğrudan Word belgelerinize tablolar ekleyebilirsiniz. Bu özellik, özel ihtiyaçlarınıza göre tablolar oluşturmanıza ve özelleştirmenize olanak tanır.
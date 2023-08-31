---
title: Tabloyu Doğrudan Ekle
linktitle: Tabloyu Doğrudan Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir tabloyu doğrudan bir Word belgesine nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/insert-table-directly/
---

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesine doğrudan tablo eklemeyi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda tabloları program aracılığıyla doğrudan Word belgelerinize ekleyebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi ve Tabloyu Oluşturma
Diziyle Kelime İşlemeyi başlatmak için yeni bir belge oluşturmamız ve diziyi başlatmamız gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document doc = new Document();

//Diziyi oluştur
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Diziyi oluşturma
Daha sonra satırları ve hücreleri ekleyerek tabloyu oluşturacağız. Örnek olarak aşağıdaki kodu kullanın:

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

// Satırdaki ikinci hücre için hücreyi çoğaltın
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Burada şununla bir satır oluşturuyoruz:`AllowBreakAcrossPages` özellik şu şekilde ayarlandı:`true` satırlar arasında sayfa bölünmesine izin vermek için. Daha sonra renkli arka plana, sabit genişliğe ve belirtilen metin içeriğine sahip bir hücre oluştururuz. Daha sonra satırdaki ikinci hücreyi oluşturmak için bu hücreyi kopyalıyoruz.

## Adım 4: Tabloyu Otomatik Sığdır
Tabloyu doğru biçimlendirmek için otomatik ayarlamalar uygulayabiliriz. Aşağıdaki kodu kullanın:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Bu kod satırı, sabit sütun genişliklerine göre otomatik sığdırma uygular.

## Adım 5: Kaydedilmesi

  değiştirilmiş belge
Son olarak, değiştirilen belgeyi doğrudan tablo eklenmiş şekilde kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Tabloyu Doğrudan Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Tablo nesnesini oluşturarak başlıyoruz. Belge nesnesini aktarmamız gerektiğini unutmayın
	//her düğümün yapıcısına. Bunun nedeni, yarattığımız her düğümün ait olması gerektiğidir.
	// bazı belgelere.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Burada bizim için satırları ve hücreleri oluşturmak için ProvidingMinimum'u çağırabiliriz. Bu yöntem kullanılıyor
	// Belirtilen düğümün geçerli olduğundan emin olmak için. Bu durumda geçerli bir tablonun en az bir Satır ve bir hücreye sahip olması gerekir.
	// Bunun yerine sırayı ve tabloyu kendimiz oluşturmayı ele alacağız.
	// Bir algoritmanın içinde bir tablo oluşturuyor olsaydık, bunu yapmanın en iyi yolu bu olurdu.
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
	// Daha sonra işlemi tablodaki diğer hücreler ve satırlar için tekrarlayacağız.
	// Mevcut hücreleri ve satırları klonlayarak da işleri hızlandırabiliriz.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesine doğrudan tablo eklemeyi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, tabloları program aracılığıyla doğrudan Word belgelerinize ekleyebilirsiniz. Bu özellik, tabloları özel ihtiyaçlarınıza göre oluşturmanıza ve özelleştirmenize olanak tanır.
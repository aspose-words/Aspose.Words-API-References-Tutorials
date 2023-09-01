---
title: Biçimlendirilmiş Tablo
linktitle: Biçimlendirilmiş Tablo
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde biçimlendirilmiş bir tablonun nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/formatted-table/
---

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde biçimlendirilmiş bir tablonun nasıl oluşturulacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizde programlı olarak özel biçimlendirmeye sahip tablolar oluşturabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi oluşturma ve belge oluşturucuyu başlatma
Biçimlendirilmiş tabloyu oluşturmaya başlamak için yeni bir belge oluşturmamız ve belge oluşturucuyu başlatmamız gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi oluşturun ve belge oluşturucuyu başlatın
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 3: Biçimlendirilmiş Tabloyu Oluşturma
Daha sonra, belge oluşturucunun sağladığı yöntemleri kullanarak biçimlendirilmiş tabloyu oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
// Dizi yapımına başla
Table table = builder. StartTable();

// Tablo başlığı satırının oluşturulması
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Dizi gövdesinin yapısı
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Dizi yapımının sonu
builder. EndTable();
```

 Burada tabloyu adım adım oluşturmak için belge oluşturucuyu kullanıyoruz. arayarak başlıyoruz`StartTable()` tabloyu başlatmak için. Sonra kullanırız`InsertCell()` hücreleri eklemek için ve`Write()` Her hücreye içerik eklemek için Tablo satırlarının, hücrelerin ve metnin formatını tanımlamak için farklı formatlama özelliklerini de kullanırız.

## 4. Adım: Belgeyi kaydedin
Son olarak biçimlendirilmiş tabloyu içeren belgeyi kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanılarak Biçimlendirilmiş Tablo için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Tablo geniş formatlama, tabloda en az bir satır mevcut olduktan sonra uygulanmalıdır.
	table.LeftIndent = 20.0;
	// Yüksekliği ayarlayın ve başlık satırı için yükseklik kuralını tanımlayın.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Bu hücrenin genişliğini bir önceki hücreden devralındığı için belirtmemize gerek yok.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Yüksekliği sıfırlayın ve tablo gövdesi için farklı bir yükseklik kuralı tanımlayın.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Yazı tipi biçimlendirmesini sıfırlayın.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde biçimlendirilmiş bir tablonun nasıl oluşturulacağını öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizde programlı olarak belirli biçimlendirmeye sahip özel tablolar oluşturabilirsiniz. Bu özellik, verilerinizi görsel olarak çekici ve düzenli bir şekilde sunmanıza ve yapılandırmanıza olanak tanır.
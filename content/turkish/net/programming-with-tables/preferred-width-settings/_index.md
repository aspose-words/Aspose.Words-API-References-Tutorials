---
title: Tercih Edilen Genişlik Ayarları
linktitle: Tercih Edilen Genişlik Ayarları
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde tercih edilen tablo hücresi genişliklerini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/preferred-width-settings/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde tablo hücreleri için tercih edilen genişlik ayarlarının nasıl yapılacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablo hücreleriniz için tercih edilen farklı genişlikleri belirtebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi oluşturma ve belge oluşturucuyu başlatma
Belge ve belge oluşturucuyla Sözcük İşleme'yi başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document doc = new Document();

// Belge oluşturucuyu başlat
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Tabloyu tercih edilen genişliklerde oluşturma
Daha sonra, farklı tercih edilen genişliklere sahip üç hücreden oluşan bir tablo oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
// Tablonun başlangıcı
builder. StartTable();

// Mutlak boyutta bir hücre ekleme
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Göreceli boyutta bir hücre ekleme (yüzde olarak)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Otomatik boyutlu bir hücre ekleme
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Tablonun sonu
builder. EndTable();
```

Burada üç hücreli bir tablo oluşturmak için belge oluşturucuyu kullanıyoruz. İlk hücrenin tercih edilen genişliği 40 noktadır, ikinci hücrenin tercih edilen genişliği masa genişliğinin %20'sidir ve üçüncü hücrenin otomatik olarak ayarlanan tercih edilen genişliği vardır.

  mevcut alana bağlı olarak.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak değiştirilen belgeyi, tablo hücreleri için tanımlanan tercih edilen genişlik ayarlarıyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanılarak Tercih Edilen Genişlik Ayarları için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Farklı tercih edilen genişliklere sahip üç hücreden oluşan bir tablo satırı ekleyin.
	builder.StartTable();
	// Mutlak boyutlu bir hücre ekleyin.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Göreceli (yüzde) boyutlu bir hücre ekleyin.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Otomatik boyutlu bir hücre ekleyin.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde tablo hücreleri için tercih edilen genişlik ayarlarının nasıl yapılacağını öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, tablo hücre genişliklerinizi Word belgelerinizdeki özel ihtiyaçlarınıza göre özelleştirebilirsiniz.
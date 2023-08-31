---
title: Sonraki Sayfalarda Satırları Tekrarla
linktitle: Sonraki Sayfalarda Satırları Tekrarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki sonraki sayfalarda tablo satırlarının nasıl tekrarlanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinin sonraki sayfalarında bir tablonun satırlarını nasıl tekrarlayacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablonuzun sonraki sayfalarında tekrarlanacak satırları belirtebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi oluşturma ve belge oluşturucuyu başlatma
Belge ve belge oluşturucu ile Sözcük İşleme'yi başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document doc = new Document();

// Belge oluşturucuyu başlat
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Tabloyu tekrarlanan satırlarla oluşturma
Ardından, sonraki sayfalarda yinelenen satırlar içeren bir tablo oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
// tablonun başlangıcı
builder. StartTable();

// İlk satır parametrelerinin konfigürasyonu (başlık satırları)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// İlk satırın ilk hücresini ekle
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// İlk satırın ikinci hücresini ekle
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Aşağıdaki satırların parametrelerini yapılandırın
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Hücreleri aşağıdaki satırlara eklemek için döngü yapın
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// tablonun sonu
builder. EndTable();
```

 Burada, iki başlık satırı ve birden çok veri satırı içeren bir tablo oluşturmak için belge oluşturucuyu kullanıyoruz. bu`RowFormat.HeadingFormat`parametreler, sonraki sayfalarda tekrarlanması gereken başlık satırlarını işaretlemek için kullanılır.

## 4. Adım: Değiştirilen belgeyi kaydetme
Sonunda ABD

  değiştirilen belgeyi, tablonun sonraki sayfalarında tekrarlanan başlık satırları ile kaydetmeniz gerekir. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Sonraki Sayfalarda Satırları Tekrarlamak için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir tablonun satırlarını bir Word belgesinin sonraki sayfalarında nasıl tekrarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizde özel ihtiyaçlarınıza göre hangi satırların tekrarlanacağını belirleyebilirsiniz.
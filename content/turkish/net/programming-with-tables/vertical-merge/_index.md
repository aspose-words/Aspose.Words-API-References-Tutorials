---
title: Dikey Birleştirme
linktitle: Dikey Birleştirme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki tablodaki hücreleri dikey olarak nasıl birleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/vertical-merge/
---

Bu derste, Aspose.Words for .NET kullanarak bir Word belgesindeki tablodaki hücrelerin dikey olarak nasıl birleştirileceğini öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerindeki tablolarınızdaki hücreleri dikey olarak birleştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme
Belgeyle Sözcük İşleme'yi başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 3: Hücreleri Dikey Birleştirme
Daha sonra tablodaki hücreleri dikey olarak birleştireceğiz. Aşağıdaki kodu kullanın:

```csharp
// Hücre ekle
builder. InsertCell();

// Dikey birleştirmeyi ilk hücreye uygula
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Başka bir hücre ekle
builder. InsertCell();

// Hücreye dikey birleştirme uygulama
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Hücre ekle
builder. InsertCell();

// Önceki hücreye dikey birleştirmeyi uygula
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Başka bir hücre ekle
builder. InsertCell();

// Hücreye dikey birleştirme uygulama
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Tablonun oluşturulmasını sonlandır
builder. EndTable();
```

Bu kodda, hücreleri bir tabloya eklemek için DocumentBuilder yapıcısını kullanıyoruz. CellFormat.VerticalMerge özelliğini kullanarak hücrelere dikey birleştirme uyguluyoruz. İlk hücre birleştirme için CellMerge.First'i, önceki hücreyle birleştirmek için CellMerge.Precious'ı ve dikey birleştirme olmaması için CellMerge.None'u kullanıyoruz.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi birleştirilmiş hücrelerle kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanılarak Dikey Birleştirme için örnek kaynak kodu 
```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Bu hücre yukarıdaki hücreye dikey olarak birleştirilmiştir ve boş olmalıdır.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki tablodaki hücreleri dikey olarak birleştirmeyi öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak tablolarınızdaki Dikey hücreleri kolayca birleştirebilirsiniz.
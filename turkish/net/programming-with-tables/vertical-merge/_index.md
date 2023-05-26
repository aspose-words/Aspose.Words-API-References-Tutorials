---
title: Dikey Birleştirme
linktitle: Dikey Birleştirme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablodaki hücreleri dikey olarak birleştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/vertical-merge/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablodaki hücreleri dikey olarak birleştirmeyi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablolarınızdaki hücreleri dikey olarak birleştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme
Belgeyle çalışmaya başlamak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Dikey Hücreleri Birleştirme
Daha sonra tablodaki hücreleri dikey olarak birleştireceğiz. Aşağıdaki kodu kullanın:

```csharp
// hücre ekle
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

// hücre ekle
builder. InsertCell();

// Dikey birleştirmeyi önceki hücreyle uygula
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Başka bir hücre ekle
builder. InsertCell();

// Hücreye dikey birleştirme uygulama
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Tablonun oluşturulmasını sonlandırın
builder. EndTable();
```

Bu kodda, bir tabloya hücre eklemek için DocumentBuilder yapıcısını kullanıyoruz. CellFormat.VerticalMerge özelliğini kullanarak hücrelere dikey birleştirme uyguluyoruz. İlk hücre birleştirme için CellMerge.First, önceki hücreyle birleştirme için CellMerge.Previous ve dikey birleştirme olmaması için CellMerge.None kullanıyoruz.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi birleştirilmiş hücrelerle kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Vertical Merge için örnek kaynak kodu 
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
	// Bu hücre, yukarıdaki hücreye dikey olarak birleştirilmiştir ve boş olmalıdır.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablodaki hücreleri dikey olarak birleştirmeyi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak tablolarınızdaki Dikey hücreleri kolayca birleştirebilirsiniz.
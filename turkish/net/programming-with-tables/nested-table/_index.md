---
title: İç İçe Tablo
linktitle: İç İçe Tablo
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde iç içe tablo oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/nested-table/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde iç içe tablo oluşturmayı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizde programlı olarak iç içe tablolar oluşturabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi oluşturma ve belge oluşturucuyu başlatma
Belge ve belge oluşturucuyla çalışmaya başlamak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma
Document doc = new Document();

// Belge oluşturucuyu başlat
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: İç İçe Tabloyu Oluşturma
Ardından, dış tabloya hücreler ekleyerek ve ilk hücrenin içinde yeni bir tablo oluşturarak yuvalanmış tabloyu oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
// Dış tablonun ilk hücresini ekle
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Dış tablonun ikinci hücresini ekle
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Dış tablonun sonlandırılması
builder. EndTable();

// Dış tablonun ilk hücresine git
builder.MoveTo(cell.FirstParagraph);

// İç tabloyu oluştur
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// İç tablonun sonu
builder. EndTable();
```

Burada dış tabloya hücre ve içerik eklemek için belge oluşturucuyu kullanıyoruz. Ardından, belge oluşturucu imlecini dış tablonun ilk hücresine hareket ettiriyoruz ve içine hücreler ve içerik ekleyerek yeni bir tablo oluşturuyoruz.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak değiştirilen belgeyi iç içe tablo ile kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Nested Table için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Bu çağrı, ilk tablo içinde iç içe geçmiş bir tablo oluşturmak için önemlidir.
	// Bu çağrı olmadan, aşağıya eklenen hücreler dış tabloya eklenir.
	builder.EndTable();
	// Dış tablonun ilk hücresine git.
	builder.MoveTo(cell.FirstParagraph);
	// İç tabloyu oluşturun.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde iç içe tablo oluşturmayı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, programlı olarak Word belgelerinizde özel ihtiyaçlarınıza göre iç içe geçmiş tablolar oluşturabilirsiniz.

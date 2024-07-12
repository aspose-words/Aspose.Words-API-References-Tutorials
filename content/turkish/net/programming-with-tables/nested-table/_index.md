---
title: İç İçe Tablo
linktitle: İç İçe Tablo
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde nasıl iç içe tablo oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/nested-table/
---

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde iç içe tablonun nasıl oluşturulacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizde programlı olarak iç içe tablolar oluşturabileceksiniz.

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

## Adım 3: İç İçe Tabloyu Oluşturma
Daha sonra, dış tabloya hücreler yerleştirerek ve ilk hücrenin içinde yeni bir tablo oluşturarak iç içe geçmiş tabloyu oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
// Dış tablonun ilk hücresini ekleyin
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Dış tablonun ikinci hücresini ekleyin
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Dış tablonun sonlandırılması
builder. EndTable();

// Dış tablonun ilk hücresine git
builder.MoveTo(cell.FirstParagraph);

// İç masayı oluşturun
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// İç tablonun sonu
builder. EndTable();
```

Burada dış tabloya hücre ve içerik eklemek için belge oluşturucuyu kullanıyoruz. Daha sonra belge oluşturucunun imlecini dış tablonun ilk hücresine hareket ettiriyoruz ve içine hücreler ve içerik ekleyerek yeni bir tablo oluşturuyoruz.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak değiştirilen belgeyi iç içe geçmiş tabloyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

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
	// Bu çağrı, ilk tablonun içinde iç içe bir tablo oluşturmak için önemlidir.
	//Bu çağrı olmadan aşağıya eklenen hücreler dış tabloya eklenecektir.
	builder.EndTable();
	// Dış tablonun ilk hücresine gidin.
	builder.MoveTo(cell.FirstParagraph);
	// İç masayı oluşturun.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde iç içe tablonun nasıl oluşturulacağını öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, program aracılığıyla Word belgelerinizde özel ihtiyaçlarınıza göre iç içe geçmiş tablolar oluşturabilirsiniz.

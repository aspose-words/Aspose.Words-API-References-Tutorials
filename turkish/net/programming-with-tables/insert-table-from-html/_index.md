---
title: Html'den Tablo Ekle
linktitle: Html'den Tablo Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile HTML'den bir Word belgesine tablo eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/insert-table-from-html/
---

Bu öğreticide, Aspose.Words for .NET kullanarak HTML'den bir Word belgesine tablo eklemeyi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, HTML'den Word belgelerinize programlı olarak tablolar ekleyebileceksiniz.

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

## 3. Adım: Tabloyu HTML'den ekleme
Ardından, HTML kodunu kullanarak tabloyu belgeye ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Burada kullandığımız`InsertHtml` tabloyu içeren HTML'yi eklemek için belge oluşturucunun yöntemi. Belirtilen HTML, iki satır ve her satırda iki hücre içeren bir tablo oluşturur. HTML kodunu ihtiyaçlarınıza göre değiştirerek tablonun içeriğini özelleştirebilirsiniz.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi HTML'den eklenen tablo ile kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Html'den Tablo Ekle için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// AutoFitSettings'in HTML'den eklenen tablolara uygulanmadığını unutmayın.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak HTML'den bir Word belgesine tablo eklemeyi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, HTML'den Word belgelerinize programlı olarak tablolar ekleyebilirsiniz. Bu özellik, tablo verilerini HTML kaynaklarından Word belgelerinize dönüştürmenize ve içe aktarmanıza olanak tanır.

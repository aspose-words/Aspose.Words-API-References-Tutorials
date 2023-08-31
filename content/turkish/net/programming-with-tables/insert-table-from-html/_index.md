---
title: Html'den Tablo Ekle
linktitle: Html'den Tablo Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile HTML'den Word belgesine nasıl tablo ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/insert-table-from-html/
---

Bu eğitimde Aspose.Words for .NET kullanarak HTML'den bir Word belgesine nasıl tablo ekleyeceğimizi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda HTML'den tabloları Word belgelerinize programlı olarak ekleyebileceksiniz.

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

## 3. Adım: Tabloyu HTML'den ekleme
Daha sonra tabloyu HTML kodunu kullanarak belgeye ekleyeceğiz. Aşağıdaki kodu kullanın:

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

 Burada şunu kullanıyoruz:`InsertHtml` Tabloyu içeren HTML'yi eklemek için belge oluşturucunun yöntemi. Belirtilen HTML, iki satır ve her satırda iki hücre içeren bir tablo oluşturur. HTML kodunu ihtiyaçlarınıza göre değiştirerek tablonun içeriğini özelleştirebilirsiniz.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi HTML'den eklenen tabloyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Html'den Tablo Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
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
Bu eğitimde Aspose.Words for .NET kullanarak HTML'den bir Word belgesine nasıl tablo ekleneceğini öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, HTML'den tabloları program aracılığıyla Word belgelerinize ekleyebilirsiniz. Bu özellik, HTML kaynaklarından tablo verilerini Word belgelerinize dönüştürmenize ve içe aktarmanıza olanak tanır.

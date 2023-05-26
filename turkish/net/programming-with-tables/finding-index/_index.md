---
title: Bulma Endeksi
linktitle: Bulma Endeksi
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde tablo, satır ve hücre dizinlerini nasıl bulacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/finding-index/
---

Bu öğreticide, bir Word belgesindeki tablo, satır ve hücre dizinlerini bulmak için Aspose.Words for .NET'i nasıl kullanacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu öğreticinin sonunda, Word belgelerinizdeki dizi öğelerinin dizinlerini programlı olarak bulabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme ve tabloya erişme
Tabloyla çalışmaya başlamak için onu içeren belgeyi yüklememiz ve tabloya erişmemiz gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//belgeyi yükle
Document doc = new Document(dataDir + "Tables.docx");

// Diziye erişim
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Tablo, Satır ve Hücre Dizini Bulun
Ardından, Aspose.Words for .NET tarafından sağlanan yöntemleri kullanarak dizideki tablo, satır ve hücre dizinlerini bulacağız. Aşağıdaki kodu kullanın:

```csharp
// Tablo dizinini bulun
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
int tableIndex = allTables.IndexOf(table);
Console.WriteLine("\nTable index is " + tableIndex);

// Satır dizinini bulun
int rowIndex = table.IndexOf(table.LastRow);
Console.WriteLine("\nLine index is " + rowIndex);

// Hücre indeksini bulun
Row row = table. LastRow;
int cellIndex = row.IndexOf(row.Cells[4]);
Console.WriteLine("\nCell index is " + cellIndex);
```

 Burada kullandığımız`GetChildNodes` belgedeki tüm tabloları alma yöntemi. Sonra kullanırız`IndexOf` tüm tabloların koleksiyonunda belirli tablonun dizinini bulmak için. Benzer şekilde, kullandığımız`IndexOf` tablodaki son satırın dizinini bulmak için ve`IndexOf` belirli bir hücrenin dizinini bulmak için bir satırın içinde.

### Aspose.Words for .NET kullanarak Dizin Bulmak için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
	int tableIndex = allTables.IndexOf(table);
	Console.WriteLine("\nTable index is " + tableIndex);
	int rowIndex = table.IndexOf(table.LastRow);
	Console.WriteLine("\nRow index is " + rowIndex);
	Row row = table.LastRow;
	int cellIndex = row.IndexOf(row.Cells[4]);
	Console.WriteLine("\nCell index is " + cellIndex);
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki tablo, satır ve hücre dizinlerini nasıl bulacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki dizi öğelerinin tam konumlarını program aracılığıyla bulabilir ve tanımlayabilirsiniz. Bu özellik, özel ihtiyaçlarınıza uyacak şekilde dizi öğelerini tam olarak değiştirmenize ve bunlarla etkileşim kurmanıza olanak tanır.
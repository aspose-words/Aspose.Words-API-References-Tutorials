---
title: Dizin Bulma
linktitle: Dizin Bulma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde tablo, satır ve hücre indekslerini nasıl bulacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/finding-index/
---

Bu derste, bir Word belgesindeki tablo, satır ve hücrenin indekslerini bulmak için Aspose.Words for .NET'i nasıl kullanacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki dizi öğelerinin dizinlerini programlı olarak bulabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tabloya erişme
Kelime İşleme'yi tabloyla başlatmak için onu içeren belgeyi yüklememiz ve ona erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Tables.docx");

// Diziye erişim
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 3: Tablo, Satır ve Hücre Dizinini Bulun
Daha sonra Aspose.Words for .NET tarafından sağlanan yöntemleri kullanarak dizideki tablo, satır ve hücre indekslerini bulacağız. Aşağıdaki kodu kullanın:

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

 Burada şunu kullanıyoruz:`GetChildNodes` belgedeki tüm tabloları alma yöntemi. Sonra kullanırız`IndexOf` Tüm tabloların koleksiyonunda belirli bir tablonun dizinini bulmak için. Benzer şekilde kullanıyoruz`IndexOf` Tablodaki son satırın indeksini bulmak için ve`IndexOf` Belirli bir hücrenin dizinini bulmak için bir satırın içinde.

### Aspose.Words for .NET kullanarak Dizin Bulma için örnek kaynak kodu 

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
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki tablo, satır ve hücrenin indekslerini nasıl bulacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki dizi öğelerinin tam konumlarını program aracılığıyla bulabilir ve tanımlayabilirsiniz. Bu özellik, dizi öğelerini özel ihtiyaçlarınıza uyacak şekilde hassas bir şekilde değiştirmenize ve bunlarla etkileşime girmenize olanak tanır.
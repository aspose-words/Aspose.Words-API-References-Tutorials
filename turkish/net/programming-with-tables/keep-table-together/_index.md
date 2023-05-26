---
title: Masayı Birlikte Tutun
linktitle: Masayı Birlikte Tutun
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde bir tabloyu nasıl bir arada tutacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/keep-table-together/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde bir tabloyu nasıl bir arada tutacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, bir tabloyu Word belgelerinizde birden çok sayfaya bölünmeden olduğu gibi tutabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme ve tabloyu alma
Tablo ile çalışmaya başlamak için belgeyi yüklememiz ve bir arada tutmak istediğimiz tabloyu getirmemiz gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//belgeyi yükle
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// tabloyu al
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: "KeepWithNext" seçeneğini etkinleştirin
Tabloyu bir arada tutmak ve birden fazla sayfaya bölünmesini önlemek için tablonun son satırının son paragrafları hariç tablodaki her paragraf için "KeepWithNext" seçeneğini etkinleştirmemiz gerekir. Aşağıdaki kodu kullanın:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Burada tablodaki her bir hücreyi dolaşıyoruz ve tablodaki son satırın son paragrafları dışında hücredeki her paragraf için "KeepWithNext" seçeneğini etkinleştiriyoruz.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi tabloyu bir arada tutarak kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Keep Table Together için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Bir sayfada kırılmasını önlemek için tablodaki her paragraf için KeepWithNext'i etkinleştirmemiz gerekiyor,
	// tablonun son satırındaki son paragraflar hariç.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde bir tabloyu nasıl bir arada tutacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak bir tabloyu sağlam tutabilir ve belgelerinizdeki birden çok sayfaya bölünmesini önleyebilirsiniz. Bu özellik, belgelerinizdeki tablolarınızın görünümü ve düzeni üzerinde size daha fazla kontrol sağlar.
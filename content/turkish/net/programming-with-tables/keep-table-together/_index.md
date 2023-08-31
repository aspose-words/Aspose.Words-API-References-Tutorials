---
title: Masayı Bir Arada Tutun
linktitle: Masayı Bir Arada Tutun
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde bir tabloyu nasıl bir arada tutacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/keep-table-together/
---

Bu derste Aspose.Words for .NET kullanarak bir Word belgesinde bir tabloyu nasıl bir arada tutacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, bir tabloyu Word belgelerinizde birden fazla sayfaya bölünmeden olduğu gibi tutabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tabloyu alma
Kelime İşleme'yi tabloyla başlatmak için belgeyi yüklememiz ve bir arada tutmak istediğimiz tabloyu getirmemiz gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Masayı geri al
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: "KeepWithNext" seçeneğini etkinleştirin
Tabloyu bir arada tutmak ve birden fazla sayfaya bölünmesini önlemek için, tablonun son satırının son paragrafları hariç, tablodaki her paragraf için "KeepWithNext" seçeneğini etkinleştirmemiz gerekir. Aşağıdaki kodu kullanın:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Burada tablodaki her hücrede döngü yapıyoruz ve tablodaki son satırın son paragrafları hariç hücredeki her paragraf için "KeepWithNext" seçeneğini etkinleştiriyoruz.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi tablo bir arada tutulacak şekilde kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Keep Table Together için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Tablodaki her paragrafın sayfa boyunca dağılmasını önlemek için KeepWithNext'i etkinleştirmemiz gerekir.
	// Tablonun son satırındaki son paragraflar hariç.
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
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde bir tabloyu nasıl bir arada tutacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, bir tabloyu olduğu gibi koruyabilir ve belgelerinizde birden çok sayfaya bölünmesini önleyebilirsiniz. Bu özellik, belgelerinizdeki tablolarınızın görünümü ve düzeni üzerinde size daha fazla kontrol sağlar.
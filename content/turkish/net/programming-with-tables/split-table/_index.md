---
title: Bölünmüş Tablo
linktitle: Bölünmüş Tablo
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki tabloyu nasıl böleceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/split-table/
---

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki bir tabloyu nasıl böleceğimizi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki belirli bir satırdan bir tabloyu bölebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme
Belgeyle Sözcük İşleme'yi başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Tables.docx");
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## 3. Adım: Masayı bölme
Daha sonra tabloyu belirli bir satırdan böleceğiz. Aşağıdaki kodu kullanın:

```csharp
// İlk tabloyu al
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Masanın bölüneceği hattın belirlenmesi
Row row = firstTable.Rows[2];

// Bölünmüş tablo için yeni bir kapsayıcı oluşturun
Table table = (Table)firstTable.Clone(false);

// Kabı orijinal tablonun arkasına yerleştirin
firstTable.ParentNode.InsertAfter(table, firstTable);

// Tablolar arasındaki mesafeyi korumak için ara paragraf ekleyin
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Satırları orijinal tablodan bölünmüş tabloya taşıma
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Burada belgeyi, belge düğümünden ilk tabloyu almak için kullanırız. Daha sonra tabloyu bölmek istediğimiz satırı belirliyoruz, bu örnekte üçüncü satırdır (indeks 2). Daha sonra orijinal tabloyu kopyalayarak yeni bir kap oluşturuyoruz ve bunu orijinal tablonun arkasına ekliyoruz. Ayrıca iki tablo arasındaki mesafeyi korumak için bir tampon paragraf da ekliyoruz. Daha sonra belirtilen satıra ulaşana kadar satırları orijinal tablodan bölünmüş tabloya do-while döngüsü kullanarak taşırız.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak kaydetmemiz gerekiyor

  bölünmüş tabloyla değiştirilmiş belge. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Bölünmüş Tablo için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Tabloyu üçüncü satıra (dahil) böleceğiz.
Row row = firstTable.Rows[2];
// Bölünmüş tablo için yeni bir kapsayıcı oluşturun.
Table table = (Table) firstTable.Clone(false);
// Kabı orijinalin arkasına yerleştirin.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Tabloların ayrı kalmasını sağlamak için bir ara paragraf ekleyin.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki tabloyu nasıl böleceğimizi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki tabloları belirli bir satırdan kolayca bölebilirsiniz.
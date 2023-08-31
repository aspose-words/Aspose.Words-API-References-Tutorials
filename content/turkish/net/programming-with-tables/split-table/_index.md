---
title: Bölünmüş Tablo
linktitle: Bölünmüş Tablo
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki tabloyu nasıl böleceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/split-table/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablonun nasıl bölüneceğini öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki bir tabloyu belirli bir satırdan ayırabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme
Sözcük İşlemeyi belgeyle başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Tables.docx");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## 3. Adım: Masayı bölme
Daha sonra tabloyu belirli bir satırdan ayıracağız. Aşağıdaki kodu kullanın:

```csharp
// İlk tabloyu al
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Tablonun bölüneceği satırın belirlenmesi
Row row = firstTable.Rows[2];

// Bölünmüş tablo için yeni bir kapsayıcı oluşturun
Table table = (Table)firstTable.Clone(false);

// Orijinal tablodan sonra kapsayıcıyı yerleştirin
firstTable.ParentNode.InsertAfter(table, firstTable);

// Tablolar arasındaki mesafeyi korumak için bir tampon paragraf ekleyin
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Satırları orijinal tablodan bölünmüş tabloya taşıma
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Burada, belge düğümünden ilk tabloyu almak için belgeyi kullanıyoruz. Daha sonra tabloyu bölmek istediğimiz satırı belirliyoruz, bu örnekte üçüncü satırdır (dizin 2). Daha sonra orijinal tabloyu klonlayarak yeni bir kapsayıcı oluşturuyoruz ve ardından bunu orijinal tablonun arkasına yerleştiriyoruz. İki tablo arasındaki mesafeyi korumak için bir tampon paragraf da ekliyoruz. Ardından, belirtilen satıra ulaşana kadar bir do-while döngüsü kullanarak satırları orijinal tablodan bölünmüş tabloya taşırız.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, kaydetmemiz gerekiyor

  bölünmüş tablo ile değiştirilen belge. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Bölünmüş Tablo için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Üçüncü sıradaki (dahil) tabloyu böleceğiz.
Row row = firstTable.Rows[2];
// Bölünmüş tablo için yeni bir kapsayıcı oluşturun.
Table table = (Table) firstTable.Clone(false);
// Kabı orijinalden sonra yerleştirin.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Tabloların ayrı kalmasını sağlamak için bir tampon paragraf ekleyin.
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
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki tabloyu nasıl böleceğimizi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki belirli bir satırdan tabloları kolayca ayırabilirsiniz.
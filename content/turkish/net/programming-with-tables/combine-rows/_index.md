---
title: Satırları Birleştir
linktitle: Satırları Birleştir
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki tablo satırlarını nasıl birleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/combine-rows/
---

Bu öğreticide, bir Word belgesindeki tablo satırlarını birleştirmek için Aspose.Words for .NET'i nasıl kullanacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablo satırlarını programlı olarak değiştirebilecek ve birleştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tablolara erişme
Sözcük İşleme'yi tablolarla başlatmak için, onları içeren belgeyi yüklememiz ve bunlara erişmemiz gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Tables.docx");

// Tablolara erişim
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Tablo satırlarını birleştirme
Daha sonra ikinci tablonun satırlarını birinci tablonun sonuna birleştireceğiz. Aşağıdaki kodu kullanın:

```csharp
// Tablo satırlarının kombinasyonu
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Burada bir`while` ikinci dizinin tüm satırlarını yinelemek ve bunları kullanarak ilk dizinin sonuna eklemek için döngü`Add` yöntem. Ardından, ikinci tabloyu kullanarak belgeden kaldırıyoruz.`Remove` yöntem.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilmiş belgeyi birleştirilmiş tablo satırlarıyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Combine Rows için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// İkinci tablodaki satırlar birinci tablonun sonuna eklenir.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Geçerli tablodaki tüm satırları sonraki tablolara ekle
	// farklı hücre sayısı ve genişlikleri ile tek bir tabloda birleştirilebilir.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki tablo satırlarını nasıl birleştireceğimizi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki tablo satırlarını programlı olarak değiştirebilirsiniz. Bu özellik, verilerinizi bir tabloda verimli bir şekilde birleştirmenize ve düzenlemenize olanak tanır.
---
title: Komple Tabloyu Klonla
linktitle: Komple Tabloyu Klonla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir tablonun tamamını bir Word belgesine nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/clone-complete-table/
---

Bu eğitimde Aspose.Words for .NET'i kullanarak bir tablonun tamamını bir Word belgesine kopyalamayı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda tabloları program aracılığıyla Word belgelerinize kopyalayabileceksiniz.

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

## Adım 3: Tam Dizi Klonu
Daha sonra tablonun tamamını kopyalayıp belgeye orijinalin arkasına ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Diziyi klonlayın
Table tableClone = (Table)table.Clone(true);

//Klonlanmış tabloyu belgeye orijinalin arkasına ekleyin
table.ParentNode.InsertAfter(tableClone, table);

// İki tablo arasına boş bir paragraf ekleyin
// Aksi takdirde, kayıt sırasında tek bir belgede birleştirileceklerdir (bunun nedeni belge doğrulamadır)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Burada şunu kullanıyoruz:`Clone` Dizinin tam bir kopyasını oluşturma yöntemi. Sonra kullanırız`InsertAfter` Klonlanmış tabloyu belgeye orijinal tablodan sonra eklemek için. Ayrıca kaydederken birleşmelerini önlemek için iki tablonun arasına boş bir paragraf ekliyoruz.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi kopyalanan tabloyla birlikte kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.
  
### Aspose.Words for .NET kullanarak Tam Tablo Klonlama için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Tabloyu kopyalayın ve belgeye orijinalin arkasına ekleyin.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// İki tablo arasına boş bir paragraf ekleyin,
	// Aksi takdirde, kaydedildikten sonra tek bir belgede birleştirileceklerdir, bunun belge doğrulamayla ilgisi vardır.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir tablonun tamamını bir Word belgesine nasıl kopyalayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, Word belgelerinizdeki tabloları programlı olarak kopyalayabilirsiniz. Bu özellik, özel ihtiyaçlarınıza uyacak şekilde diziler üzerinde gelişmiş manipülasyonlar gerçekleştirmenize olanak tanır.
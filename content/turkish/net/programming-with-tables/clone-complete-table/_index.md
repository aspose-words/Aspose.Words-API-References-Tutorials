---
title: Komple Tabloyu Klonla
linktitle: Komple Tabloyu Klonla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir tablonun tamamını bir Word belgesine nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/clone-complete-table/
---

Bu eğitimde, Aspose.Words for .NET'in tüm tabloyu bir Word belgesine klonlamak için nasıl kullanılacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, tabloları programlı olarak Word belgelerinize kopyalayabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme ve tabloya erişme
Tablo ile Sözcük İşleme başlatmak için tabloyu içeren belgeyi yüklememiz ve tabloya erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Tables.docx");

// Diziye erişim
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Tam Dizi Klonu
Ardından, tüm tabloyu klonlayacağız ve orijinalinden sonra belgeye ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Diziyi klonla
Table tableClone = (Table)table.Clone(true);

// Klonlanmış tabloyu orijinal tablodan sonra belgeye yerleştirin
table.ParentNode.InsertAfter(tableClone, table);

// İki tablo arasına boş bir paragraf ekleyin
// Aksi takdirde, kayıtta bir araya getirileceklerdir (bunun nedeni belge doğrulamasıdır)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Burada biz kullanıyoruz`Clone` dizinin tam bir kopyasını oluşturma yöntemi. Sonra kullanırız`InsertAfter` klonlanmış tabloyu orijinal tablodan sonra belgeye eklemek için. Ayrıca kaydederken birleşmelerini önlemek için iki tablo arasına boş bir paragraf ekliyoruz.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi klonlanmış tabloyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.
  
### Aspose.Words for .NET kullanan Clone Complete Table için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Tabloyu kopyalayın ve orijinalden sonra belgeye ekleyin.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// İki tablo arasına boş bir paragraf ekleyin,
	// veya kaydettikten sonra bir araya getirilecekler, bunun belge doğrulaması ile ilgisi var.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir tablonun tamamını bir Word belgesine nasıl kopyalayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki tabloları programlı olarak kopyalayabilirsiniz. Bu özellik, özel ihtiyaçlarınıza uyacak şekilde diziler üzerinde gelişmiş manipülasyonlar gerçekleştirmenizi sağlar.
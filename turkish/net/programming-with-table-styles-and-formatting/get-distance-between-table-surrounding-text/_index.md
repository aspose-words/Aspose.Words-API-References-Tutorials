---
title: Metni Çevreleyen Tablo Arasındaki Mesafeyi Alın
linktitle: Metni Çevreleyen Tablo Arasındaki Mesafeyi Alın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki metin ve tablo arasındaki mesafeyi bulmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir tablodaki çevreleyen metin arasındaki mesafeyi elde etmek için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizdeki bir tablo ile onu çevreleyen metin arasındaki çeşitli mesafelere nasıl erişeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Word belgenizin bulunduğu yer burasıdır. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Mevcut belgeyi yükleyin
 Ardından, mevcut Word belgesini bir örneğine yüklemeniz gerekir.`Document` sınıf.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. Adım: Tablo ile çevresindeki metin arasındaki mesafeyi bulun
 Tablo ile çevreleyen metin arasındaki mesafeyi elde etmek için, tabloyu kullanarak belgedeki tabloya erişmemiz gerekir.`GetChild()` yöntem ve`NodeType.Table` mülk. Dizi özelliklerini kullanarak farklı mesafeleri görüntüleyebiliriz.`DistanceTop`, `DistanceBottom`, `DistanceRight` Ve`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Aspose.Words for .NET kullanarak Tablo Çevreleyen Metin Arasındaki Mesafeyi Al için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir tablodaki çevreleyen metin arasındaki mesafeyi nasıl bulacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, Word belgelerinizdeki bir tablo ile çevresindeki metin arasındaki çeşitli mesafelere kolayca erişebilirsiniz. Aspose.Words, belgelerinizdeki tabloları değiştirmek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, tablolarınızın düzenini metne göre analiz edebilir ve belirli ihtiyaçları karşılayabilirsiniz.
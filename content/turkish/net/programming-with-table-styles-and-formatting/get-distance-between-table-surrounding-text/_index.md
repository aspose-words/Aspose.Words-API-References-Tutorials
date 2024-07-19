---
title: Tablo Çevreleyen Metin Arasındaki Mesafeyi Alın
linktitle: Tablo Çevreleyen Metin Arasındaki Mesafeyi Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde metin ile tablo arasındaki mesafeyi hesaplamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

Bu eğitimde, Aspose.Words for .NET'i kullanarak bir tablodaki çevreleyen metinler arasındaki mesafeyi hesaplamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizdeki bir tablo ile onu çevreleyen metin arasındaki çeşitli mesafelere nasıl erişeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Burası Word belgenizin bulunduğu yerdir. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Mevcut belgeyi yükleyin
 Daha sonra mevcut Word belgesini bir örneğine yüklemeniz gerekir.`Document` sınıf.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. Adım: Tablo ile onu çevreleyen metin arasındaki mesafeyi öğrenin
 Tablo ile onu çevreleyen metin arasındaki mesafeyi elde etmek için belgedeki tabloya aşağıdaki komutu kullanarak erişmemiz gerekir:`GetChild()` yöntem ve`NodeType.Table` mülk. Daha sonra dizi özelliklerini kullanarak farklı mesafeleri görüntüleyebiliriz.`DistanceTop`, `DistanceBottom`, `DistanceRight`Ve`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Aspose.Words for .NET kullanarak Tablo Çevreleyen Metin Arasındaki Mesafeyi Alma için örnek kaynak kodu 

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
Bu eğitimde Aspose.Words for .NET'i kullanarak bir tablodaki çevreleyen metinler arasındaki mesafeyi nasıl elde edeceğimizi öğrendik. Bu adım adım kılavuzu izleyerek Word belgelerinizde bir tablo ile onu çevreleyen metin arasındaki çeşitli mesafelere kolayca erişebilirsiniz. Aspose.Words, belgelerinizdeki tabloları düzenlemek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle tablolarınızın düzenini metne göre analiz edebilir ve belirli ihtiyaçları karşılayabilirsiniz.
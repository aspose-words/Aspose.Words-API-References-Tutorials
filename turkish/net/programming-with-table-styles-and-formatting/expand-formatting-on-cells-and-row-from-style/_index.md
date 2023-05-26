---
title: Hücrelerde ve Stilden Satırda Biçimlendirmeyi Genişletin
linktitle: Hücrelerde ve Stilden Satırda Biçimlendirmeyi Genişletin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir tablo stilinden biçimlendirmeyi hücrelere ve satırlara genişletmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Bu eğitimde, Aspose.Words for .NET kullanarak biçimlendirmeyi bir stilden hücrelere ve satırlara genişletmek için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizdeki belirli hücrelere ve satırlara tablo stili formatlamayı nasıl uygulayacağınızı öğreneceksiniz.


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

## 3. Adım: İlk tablonun ilk hücresine gidin
 Başlamak için, belgedeki ilk tablonun ilk hücresine gitmemiz gerekiyor. biz kullanıyoruz`GetChild()` Ve`FirstRow.FirstCell` ilk hücreye referans alma yöntemleri.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## 4. Adım: İlk Hücre Biçimlendirmesini Göster
Tablonun stillerini genişletmeden önce, hücrenin mevcut arka plan rengini gösteriyoruz. Geçerli biçimlendirme tablonun stilinde saklandığından, bu boş olmalıdır.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## 5. Adım: Tablo Stillerini Doğrudan Biçimlendirmeye Genişletin
 Şimdi belge stillerini kullanarak biçimlendirmeyi yönlendirmek için tablo stillerini genişletiyoruz.`ExpandTableStylesToDirectFormatting()` yöntem.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## 6. Adım: Stil genişletmeden sonra hücre biçimlendirmesini gösterin
Şimdi tablo stillerini genişlettikten sonra hücrenin arka plan rengini gösteriyoruz. Tablo stilinden mavi bir zemin rengi uygulanmalıdır.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Aspose.Words for .NET kullanarak Hücrelerde ve Satırdan Stilde Biçimlendirmeyi Genişletmek için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Belgedeki ilk tablonun ilk hücresini alın.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Önce hücre gölgelendirmesinin rengini yazdırın.
	// Geçerli gölgeleme tablo stilinde saklandığından bu boş olmalıdır.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Şimdi tablo stillerini genişlettikten sonra hücre gölgelendirmesini yazdırın.
	// Tablo stilinden mavi zemin desen rengi uygulanmış olmalıdır.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir tablo stilinden hücrelere ve satırlara formatlamayı nasıl genişleteceğimizi öğrendik. Bu adım adım kılavuzu izleyerek, tablo stili biçimlendirmesini Word belgelerinizdeki belirli hücrelere ve satırlara kolayca uygulayabilirsiniz. Aspose.Words, belgelerinizdeki tabloları değiştirmek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, Word belgelerinizin düzenini ve sunumunu daha da özelleştirebilirsiniz.
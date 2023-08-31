---
title: Hücrelerdeki Biçimlendirmeyi Genişletin ve Stilden Satırlayın
linktitle: Hücrelerdeki Biçimlendirmeyi Genişletin ve Stilden Satırlayın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak formatlamayı tablo stilinden hücrelere ve satırlara genişletmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Bu eğitimde, Aspose.Words for .NET kullanarak formatlamayı bir stilden hücrelere ve satırlara genişletmek için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.Words for .NET kullanarak tablo stili formatlamayı Word belgelerinizdeki belirli hücrelere ve satırlara nasıl uygulayacağınızı öğreneceksiniz.


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

## Adım 3: İlk tablonun ilk hücresine gidin
 Başlamak için belgedeki ilk tablonun ilk hücresine gitmemiz gerekiyor. biz kullanıyoruz`GetChild()` Ve`FirstRow.FirstCell` İlk hücreye referans alma yöntemleri.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Adım 4: İlk Hücre Biçimlendirmesini Göster
Tablonun stillerini genişletmeden önce hücrenin mevcut arka plan rengini görüntülüyoruz. Geçerli biçimlendirme tablonun stilinde saklandığından bu boş olmalıdır.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Adım 5: Tablo Stillerini Doğrudan Biçimlendirmeye Genişletin
 Şimdi belgenin stilini kullanarak tablo stillerini doğrudan biçimlendirmeye genişletiyoruz.`ExpandTableStylesToDirectFormatting()` yöntem.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## 6. Adım: Stil genişletmeden sonra hücre biçimlendirmesini gösterin
Artık tablo stillerini genişlettikten sonra hücrenin arka plan rengini görüntülüyoruz. Tablo stilinden mavi arka plan rengi uygulanmalıdır.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Aspose.Words for .NET kullanarak Hücrelerde ve Stilden Satırda Formatlamayı Genişletme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Belgedeki ilk tablonun ilk hücresini alın.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// İlk önce hücre gölgelemesinin rengini yazdırın.
	// Geçerli gölgeleme tablo stilinde saklandığından bu boş olmalıdır.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Şimdi tablo stillerini genişlettikten sonra hücre gölgelendirmesini yazdırın.
	// Tablo stilinden mavi arka plan deseni rengi uygulanmalıydı.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Çözüm
Bu eğitimde Aspose.Words for .NET'i kullanarak tablo stilinden formatlamayı hücrelere ve satırlara nasıl genişleteceğimizi öğrendik. Bu adım adım kılavuzu izleyerek tablo stili biçimlendirmesini Word belgelerinizdeki belirli hücrelere ve satırlara kolayca uygulayabilirsiniz. Aspose.Words, belgelerinizdeki tabloları düzenlemek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle Word belgelerinizin düzenini ve sunumunu daha da özelleştirebilirsiniz.
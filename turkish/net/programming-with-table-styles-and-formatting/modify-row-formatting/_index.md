---
title: Satır Biçimlendirmesini Değiştir
linktitle: Satır Biçimlendirmesini Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak tablo satırı biçimlendirmesini değiştirmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir tablo satırının biçimlendirmesini değiştirmek için adım adım size yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizdeki bir tablo satırının kenarlıklarını, yüksekliğini ve satır sonunu nasıl değiştireceğinizi öğreneceksiniz.

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

## 3. Adım: Değiştirmek için satıra erişin
 Bir tablo satırının biçimlendirmesini değiştirmek için tablodaki belirli satıra gitmemiz gerekir. biz kullanıyoruz`GetChild()` Ve`FirstRow` tablonun ilk satırına referans alma yöntemleri.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## 4. Adım: Satır biçimlendirmesini değiştirin
 Şimdi, özelliklerini kullanarak satır biçimlendirmesini değiştirebiliriz.`RowFormat` sınıf. Örneğin, satır kenarlarını kaldırabilir, otomatik yüksekliği ayarlayabilir ve satır kesmeye izin verebiliriz.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Aspose.Words for .NET kullanarak Modify Row Formatting için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Tablodaki ilk satırı alın.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir tablo satırının biçimlendirmesini nasıl değiştireceğimizi öğrendik. Bu adım adım kılavuzu izleyerek, Word belgelerinizdeki tablolarınızdaki satırların kenarlıklarını, yüksekliğini ve satır sonlarını kolayca ayarlayabilirsiniz. Aspose.Words, belgelerinizdeki tabloları değiştirmek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, tablolarınızın görsel düzenini özel ihtiyaçlarınıza göre özelleştirebilirsiniz.
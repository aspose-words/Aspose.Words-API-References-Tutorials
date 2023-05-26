---
title: Kenarlıklı Tablo Oluştur
linktitle: Kenarlıklı Tablo Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak kenarlıklı bir tablo oluşturmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

Bu öğreticide, Aspose.Words for .NET kullanarak kenarlıklı bir tablo oluşturma sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizde özel kenarlıklara sahip bir tabloyu nasıl oluşturacağınızı öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Word belgenizin saklandığı yer burasıdır. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Mevcut belgeyi yükleyin
 Ardından, mevcut Word belgesini bir örneğine yüklemeniz gerekir.`Document` sınıf.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. Adım: Tabloya erişin ve mevcut sınırları kaldırın
 Kenarlıklı tabloyu oluşturmaya başlamak için belgedeki tabloya gitmeli ve mevcut kenarlıkları kaldırmalıyız. bu`ClearBorders()` yöntem tablodaki tüm sınırları kaldırır.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## 4. Adım: Tablo Kenarlıklarını Ayarlayın
 Artık tablo kenarlıklarını kullanarak ayarlayabiliriz.`SetBorders()` yöntem. Bu örnekte 1,5 punto kalınlığında yeşil renkli bir bordür kullanıyoruz.

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## 5. Adım: Değiştirilen belgeyi kaydedin
Son olarak, değiştirilen belgeyi bir dosyaya kaydediyoruz. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak özel çerçeveli bir tablo oluşturdunuz.

### Aspose.Words for .NET kullanarak Build Table With Borders için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Tablodaki mevcut tüm sınırları temizleyin.
	table.ClearBorders();
	// Tablonun etrafına ve içine yeşil bir kenarlık koyun.
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak kenarlıklı bir tablo oluşturmayı öğrendik. Bu adım adım kılavuzu izleyerek, Word belgelerinizde tablo kenarlıklarınızı kolayca özelleştirebilirsiniz. Aspose.Words, belgelerinizdeki tabloları değiştirmek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, Word belgelerinizin görsel sunumunu geliştirebilir ve belirli ihtiyaçları karşılayabilirsiniz.
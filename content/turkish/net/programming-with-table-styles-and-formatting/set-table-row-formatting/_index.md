---
title: Tablo Satır Biçimlendirmesini Ayarla
linktitle: Tablo Satır Biçimlendirmesini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak tablo satırı formatını ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

Bu eğitimde, Aspose.Words for .NET'i kullanarak tablo satır formatını ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.Words for .NET'i kullanarak Word belgelerinizdeki bir tablo satırının yüksekliğini ve dolgularını nasıl ayarlayacağınızı öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş Word belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Daha sonra, yeni bir örneğini oluşturmanız gerekir.`Document` sınıf ve bu belge için bir belge oluşturucu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Yeni bir tablo başlatın ve hücre ekleyin
Tabloyu oluşturmaya başlamak için şunu kullanıyoruz:`StartTable()` belge yapıcısının yöntemini kullanarak tabloya bir hücre ekliyoruz.`InsertCell()` yöntem.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 4. Adım: Satır formatını tanımlayın
 Artık satır formatını şuraya erişerek ayarlayabiliriz:`RowFormat` nesnesi`DocumentBuilder` nesne. İlgili özellikleri kullanarak satır yüksekliğini ve kenar boşluklarını (dolguları) ayarlayabiliriz.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 5. Adım: Tablo kenar boşluklarını ayarlayın
 Daha sonra tablonun karşılık gelen özelliklerine erişerek tablo dolgularını ayarlayabiliriz.`Table` nesne. Bu kenar boşlukları tablonun tüm satırlarına uygulanacaktır.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 6. Adım: Satıra içerik ekleyin
 Son olarak belge oluşturucuyu kullanarak satıra içerik ekleyebiliriz.`Writeln()` yöntem.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Adım 7: Tabloyu tamamlayın ve belgeyi kaydedin
İçinde

 sonunda tabloyu oluşturmayı bitiriyoruz.`EndRow()`Ve`EndTable()` yöntemini kullandıktan sonra değiştirilen belgeyi bir dosyaya kaydederiz.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Aspose.Words for .NET kullanarak Tablo Satır Formatını Ayarlama için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Bu biçimlendirme özellikleri tabloda ayarlanır ve tablodaki tüm satırlara uygulanır.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET'i kullanarak tablo satır formatını nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek Word belgelerinizde tablo satır yüksekliğini ve kenar boşluklarını kolayca ayarlayabilirsiniz. Aspose.Words, belgelerinizdeki tabloları düzenlemek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle tablolarınızın görsel düzenini özel ihtiyaçlarınıza göre özelleştirebilirsiniz.
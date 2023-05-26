---
title: Tablo Stili Oluştur
linktitle: Tablo Stili Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak özel bir tablo stili oluşturmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/create-table-style/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir tablo stili oluşturma sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizdeki tablolarınız için nasıl özel bir stil oluşturacağınızı öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenmiş Word belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Ardından, yeni bir örneğini oluşturmanız gerekir.`Document` sınıf ve bu belge için bir belge oluşturucu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Yeni bir tablo başlatın ve hücreleri ekleyin
Tabloyu oluşturmaya başlamak için,`StartTable()` Belge oluşturucunun yöntemini kullanarak tabloya hücreler ekleriz.`InsertCell()` yöntemini kullanarak hücrelerin içeriğini yazıyoruz.`Write()` yöntem.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## 4. Adım: Bir tablo stili oluşturun
 Şimdi kullanarak bir tablo stili oluşturabiliriz.`TableStyle` sınıf ve`Add()` belgeden yöntem`s `Styles koleksiyonu. Kenarlıklar, kenar boşlukları ve dolgular gibi stilin özelliklerini tanımlarız.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Adım 5: Tablo stilini tabloya uygulayın
 Son olarak oluşturduğumuz tablo stilini kullanarak tabloya uyguluyoruz.`Style` tablonun özelliği.

```csharp
table.Style = tableStyle;
```

## 6. Adım: Değiştirilen belgeyi kaydedin
Son olarak değiştirilen belgeyi bir dosyaya kaydedin. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak tablonuz için özel bir stil yarattınız.

### Aspose.Words for .NET kullanarak Tablo Stili Oluşturma için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir tablo stili oluşturmayı öğrendik. Bu adım adım kılavuzu izleyerek, Word belgelerinizdeki tablolarınızın stilini kolayca özelleştirebilirsiniz. Aspose.Words, belgelerinizdeki tabloları değiştirmek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, Word belgelerinizin görsel sunumunu geliştirebilir ve belirli ihtiyaçları karşılayabilirsiniz.
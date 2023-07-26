---
title: Stile Sahip Tablo Oluşturun
linktitle: Stile Sahip Tablo Oluşturun
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak özel bir stille tablo oluşturmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

Bu eğitimde, Aspose.Words for .NET kullanarak stil sahibi bir tablo oluşturma sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizde özel stile sahip bir tabloyu nasıl oluşturacağınızı öğreneceksiniz.

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

## 3. Adım: Yeni bir tablo başlatın ve bir hücre ekleyin
 Tabloyu oluşturmaya başlamak için`StartTable()` Belge oluşturucunun yöntemini kullanarak tabloya bir hücre ekleriz.`InsertCell()` yöntem.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Adım 4: Tablonun stilini tanımlayın
 Şimdi tablo stilini kullanarak ayarlayabiliriz.`StyleIdentifier` mülk. Bu örnekte "MediumShading1Accent1" stilini kullanıyoruz.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## 5. Adım: Stil seçeneklerini tabloya uygulayın
 Stil tarafından hangi özelliklerin biçimlendirilmesi gerektiğini şunu kullanarak belirtebiliriz:`StyleOptions`dizinin özelliği. Bu örnekte şu seçenekleri uyguluyoruz: "FirstColumn", "RowBands" ve "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## 6. Adım: Tablo boyutunu otomatik olarak ayarlayın
 Dizinin boyutunu içeriğine göre otomatik olarak ayarlamak için,`AutoFit()` ile yöntem`AutoFitBehavior.AutoFitToContents` davranış.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## 7. Adım: Hücrelere içerik ekleyin
 Artık şunu kullanarak hücrelere içerik ekleyebiliriz:`Writeln()` Ve`InsertCell()` belge oluşturucu yöntemleri. Bu örnekte, "Öğe" ve "Miktar (

kg)" ve ilgili veriler.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## 8. Adım: Değiştirilen belgeyi kaydedin
Son olarak, değiştirilen belgeyi bir dosyaya kaydediyoruz. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak özel stile sahip bir tablo oluşturdunuz.

### Aspose.Words for .NET kullanarak Build Table With Style için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Herhangi bir tablo biçimlendirmesi ayarlamadan önce en az bir satır eklemeliyiz.
	builder.InsertCell();
	// Benzersiz stil tanımlayıcısına göre kullanılan tablo stilini ayarlayın.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Stile göre hangi özelliklerin biçimlendirilmesi gerektiğini uygulayın.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak stil sahibi bir tablonun nasıl oluşturulacağını öğrendik. Bu adım adım kılavuzu izleyerek, Word belgelerinizdeki tablolarınızın stilini kolayca özelleştirebilirsiniz. Aspose.Words, belgelerinizdeki tabloları değiştirmek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, Word belgelerinizin görsel sunumunu geliştirebilir ve belirli ihtiyaçları karşılayabilirsiniz.
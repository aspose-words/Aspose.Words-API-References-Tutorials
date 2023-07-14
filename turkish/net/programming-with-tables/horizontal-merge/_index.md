---
title: Yatay Birleştirme
linktitle: Yatay Birleştirme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word tablosundaki hücreleri yatay olarak nasıl birleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/horizontal-merge/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablodaki hücreleri yatay olarak birleştirmeyi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word tablolarınızdaki hücreleri programlı olarak yatay olarak birleştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi oluşturma ve belge oluşturucuyu başlatma
Tablo ve hücrelerle Sözcük İşleme'yi başlatmak için yeni bir belge oluşturmamız ve belge oluşturucuyu başlatmamız gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi oluşturun ve belge oluşturucuyu başlatın
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Hücrelerin yatay birleştirilmesiyle tablonun oluşturulması
Ardından, tabloyu oluşturacağız ve Aspose.Words for .NET tarafından sağlanan özellikleri kullanarak yatay hücre birleştirme uygulayacağız. Aşağıdaki kodu kullanın:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Bu hücre öncekiyle birleştirilir ve boş olmalıdır.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Burada tabloyu oluşturmak ve hücre yatay birleştirme özelliklerini ayarlamak için belge oluşturucuyu kullanıyoruz. biz kullanıyoruz`HorizontalMerge`mülkiyeti`CellFormat` Her hücreye uygulanacak yatay birleştirme türünü belirtmek için nesne. kullanma`CellMerge.First` kullanırken ilk hücreyi sonrakiyle birleştiriyoruz`CellMerge.Previous` mevcut hücreyi önceki hücreyle birleştiriyoruz.`CellMerge.None` hücrenin birleştirilmemesi gerektiğini belirtir.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi hücreler yatay olarak birleştirilmiş olarak kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Yatay Birleştirme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Bu hücre öncekiyle birleştirilir ve boş olmalıdır.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablodaki hücreleri yatay olarak birleştirmeyi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word tablolarınıza programlı olarak yatay hücre birleştirmeyi uygulayabilirsiniz. Bu özellik, daha karmaşık tablo düzenleri oluşturmanıza ve verilerinizi daha iyi düzenlemenize olanak tanır.
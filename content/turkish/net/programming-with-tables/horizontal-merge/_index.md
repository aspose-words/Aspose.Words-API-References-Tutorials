---
title: Yatay Birleştirme
linktitle: Yatay Birleştirme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word tablosundaki hücreleri yatay olarak nasıl birleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/horizontal-merge/
---

Bu derste, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablodaki hücreleri yatay olarak nasıl birleştireceğimizi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word tablolarınızdaki hücreleri programlı olarak yatay olarak birleştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi oluşturma ve belge oluşturucuyu başlatma
Kelime İşleme'yi tablo ve hücrelerle başlatmak için yeni bir belge oluşturmamız ve belge oluşturucuyu başlatmamız gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi oluşturun ve belge oluşturucuyu başlatın
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 3: Hücrelerin yatay birleştirilmesiyle tablonun oluşturulması
Daha sonra tabloyu oluşturacağız ve Aspose.Words for .NET tarafından sağlanan özellikleri kullanarak yatay hücre birleştirmeyi uygulayacağız. Aşağıdaki kodu kullanın:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Bu hücre öncekiyle birleştirilmiştir ve boş olmalıdır.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Burada tabloyu oluşturmak ve hücrenin yatay birleştirme özelliklerini ayarlamak için belge oluşturucuyu kullanıyoruz. biz kullanıyoruz`HorizontalMerge` mülkiyeti`CellFormat` Her hücreye uygulanacak yatay birleştirme türünü belirtmek için nesne. Kullanma`CellMerge.First` kullanırken ilk hücreyi bir sonrakiyle birleştiriyoruz`CellMerge.Previous` mevcut hücreyi önceki hücreyle birleştiriyoruz.`CellMerge.None` hücrenin birleştirilmemesi gerektiğini belirtir.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi hücreleri yatay olarak birleştirilmiş şekilde kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanılarak Yatay Birleştirme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Bu hücre öncekiyle birleştirilmiştir ve boş olmalıdır.
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
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki tablodaki hücreleri yatay olarak nasıl birleştireceğimizi öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, Word tablolarınızda yatay hücre birleştirmeyi programlı olarak uygulayabilirsiniz. Bu özellik, daha karmaşık tablo düzenleri oluşturmanıza ve verilerinizi daha iyi düzenlemenize olanak tanır.
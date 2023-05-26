---
title: Tablo Oluştur
linktitle: Tablo Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesinde tablo oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/build-table/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde tablo oluşturmayı öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, DocumentBuilder sınıfını kullanarak özel biçimlendirme ve içeriğe sahip bir tablo oluşturabileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Tabloyu Başlatın
Ardından, tabloyu oluşturmaya başlamak için DocumentBuilder sınıfının StartTable yöntemini kullanın:

```csharp
Table table = builder.StartTable();
```

## 3. Adım: Hücreleri Yerleştirin ve İçerik Ekleyin
Artık, DocumentBuilder sınıfının InsertCell ve Write yöntemlerini kullanarak tabloya hücreler ekleyebilir ve bunlara içerik ekleyebilirsiniz. Hücre biçimlendirmesini gerektiği gibi özelleştirin:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## 4. Adım: Satırı Sonlandırın
İlk satırın hücrelerine içerik ekledikten sonra, satırı sonlandırmak için DocumentBuilder sınıfının EndRow yöntemini kullanın:

```csharp
builder.EndRow();
```

## 5. Adım: Satır Biçimlendirmesini Özelleştirin
RowFormat ve CellFormat nesnelerinin özelliklerini ayarlayarak bir satırın biçimlendirmesini özelleştirebilirsiniz:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Adım 6: Tabloyu Sonlandırın
Tabloyu tamamlamak için DocumentBuilder sınıfının EndTable yöntemini kullanın:

```csharp
builder.EndTable();
```

### Aspose.Words for .NET kullanarak Tablo Oluşturmak için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir tablo oluşturmak için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesinde tablo oluşturmayı başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodu kullanarak, artık özel biçimlendirmeli tablolar oluşturabilirsiniz.
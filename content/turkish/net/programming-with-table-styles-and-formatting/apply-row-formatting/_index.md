---
title: Satır Biçimlendirmesini Uygula
linktitle: Satır Biçimlendirmesini Uygula
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir tabloya satır formatlaması uygulamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir tabloya satır formatlaması uygulamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.Words for .NET kullanarak Word belgelerinizdeki tablo satırlarını nasıl formatlayacağınızı net bir şekilde anlayacaksınız.

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

## 3. Adım: Yeni bir pano başlatın
 Satır biçimlendirmesini uygulamak için önce aşağıdakileri kullanarak yeni bir tablo başlatmalıyız:`StartTable()` belge oluşturucunun yöntemi.

```csharp
Table table = builder. StartTable();
```

## 4. Adım: Hücreyi ekleyin ve satır formatına gidin
Artık tabloya bir hücre ekleyebilir ve belge oluşturucuyu kullanarak bu hücrenin satır biçimine erişebiliriz.`InsertCell()`Ve`RowFormat` yöntemler.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Adım 5: Satır Yüksekliğini Ayarlayın
 Satır yüksekliğini ayarlamak için şunu kullanırız:`Height`Ve`HeightRule` satır biçiminin özellikleri. Bu örnekte, 100 puntoluk bir satır yüksekliği belirledik ve`Exactly` kural.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 6. Adım: Tablo biçimlendirmesini tanımlayın
 Bazı biçimlendirme özellikleri tablonun kendisinde ayarlanabilir ve tüm tablo satırlarına uygulanabilir. Bu örnekte, tablo kenar boşluğu özelliklerini kullanarak ayarladık.`LeftPadding`, `RightPadding`, `TopPadding`Ve`BottomPadding` özellikler.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 7. Adım: Satıra içerik ekleyin
Şimdi yapabiliriz

 Belge yapıcının yöntemlerini kullanarak satıra içerik ekleyeceğiz. Bu örnekte, şunu kullanıyoruz:`Writeln()` satıra metin ekleme yöntemi.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Adım 8: Satırı ve tabloyu bitirin
 İçeriği satıra ekledikten sonra, satırı kullanarak sonlandırabiliriz.`EndRow()` yöntemini kullanın ve ardından tabloyu kullanarak sonlandırın.`EndTable()` yöntem.

```csharp
builder. EndRow();
builder. EndTable();
```

## 9. Adım: Değiştirilen belgeyi kaydedin
Son olarak değiştirilen belgeyi bir dosyaya kaydediyoruz. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak bir tabloya satır formatlaması uyguladınız.

### Aspose.Words for .NET kullanarak Satır Formatlaması Uygulamak için örnek kaynak kodu 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak satır formatlamanın bir tabloya nasıl uygulanacağını öğrendik. Bu adım adım kılavuzu izleyerek bu işlevselliği C# projelerinize kolayca entegre edebilirsiniz. Tablo satır formatını değiştirmek belge işlemenin önemli bir yönüdür ve Aspose.Words bunu başarmak için güçlü ve esnek bir API sunar. Bu bilgiyle Word belgelerinizin görsel sunumunu geliştirebilir ve belirli gereksinimleri karşılayabilirsiniz.
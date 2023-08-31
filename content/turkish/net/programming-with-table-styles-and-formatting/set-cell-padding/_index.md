---
title: Hücre Dolgusunu Ayarla
linktitle: Hücre Dolgusunu Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak tablo hücre kenar boşluklarını ayarlamaya yönelik adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

Bu eğitimde, Aspose.Words for .NET'i kullanarak tablo hücresi kenar boşluklarını ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.Words for .NET kullanarak Word belgelerinizdeki tablolarınızın hücre içeriğinin sol, üst, sağ ve alt kenar boşluklarını (boşluk) nasıl ayarlayacağınızı öğreneceksiniz.

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
builder. StartTable();
builder. InsertCell();
```

## 4. Adım: Hücre kenar boşluklarını ayarlayın
 Artık hücre kenar boşluklarını aşağıdaki komutu kullanarak ayarlayabiliriz:`SetPaddings()` yöntemi`CellFormat` nesne. Kenar boşlukları noktalarla tanımlanır ve sol, üst, sağ ve alt sırasıyla belirtilir.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## 5. Adım: Hücreye içerik ekleyin
 Daha sonra belge oluşturucuyu kullanarak hücreye içerik ekleyebiliriz.`Writeln()` yöntem.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Adım 6: Tabloyu tamamlayın ve belgeyi kaydedin
 Son olarak aşağıdaki komutu kullanarak tabloyu oluşturmayı tamamlıyoruz:`EndRow()` yöntem ve`EndTable()`, ardından değiştirilen belgeyi bir dosyaya kaydederiz.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Aspose.Words for .NET kullanarak Hücre Dolgusunu Ayarla için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Hücre içeriğinin sol/üst/sağ/alt kısmına eklenecek alan miktarını (nokta cinsinden) ayarlar.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir tablo hücresinin kenar boşluklarını nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, Word belgelerinizdeki tablolarınızda içeriğin solunda, üstünde, sağında ve altında boşluklar oluşturmak için hücre kenar boşluklarını kolayca ayarlayabilirsiniz. Aspose.Words, belgelerinizdeki tabloları düzenlemek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle tablolarınızın formatını özel ihtiyaçlarınıza göre özelleştirebilirsiniz.
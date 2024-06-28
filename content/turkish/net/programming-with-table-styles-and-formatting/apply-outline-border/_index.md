---
title: Anahat Kenarlığını Uygula
linktitle: Anahat Kenarlığını Uygula
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir tabloya anahat kenarlığı uygulamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir tabloya anahat kenarlığı uygulama sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.Words for .NET'i kullanarak Word belgelerinizdeki tablo kenarlıklarını nasıl değiştireceğiniz konusunda net bir anlayışa sahip olacaksınız.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Burası Word belgenizin saklandığı yerdir. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin
 Daha sonra, Word belgesini bir örneğine yüklemeniz gerekir.`Document` sınıf.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. Adım: Tabloya erişin
 Anahat kenarlığı uygulamak için belgedeki tabloya erişmemiz gerekir.`Table` class Aspose.Words'te bir tabloyu temsil eder.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 4. Adım: Tabloyu sayfanın ortasına hizalayın
 Artık tabloyu sayfanın ortasına hizalayabiliriz.`Alignment` tablonun özelliği.

```csharp
table. Alignment = Table Alignment. Center;
```

## Adım 5: Mevcut tablo kenarlıklarını silin.
Yeni bir anahat kenarlığıyla başlamak için öncelikle mevcut tüm kenarlıkları tablodan silmemiz gerekir. Bu, kullanılarak yapılabilir.`ClearBorders()` yöntem.

```csharp
table. ClearBorders();
```

## Adım 6: Masanın etrafında yeşil bir kenarlık tanımlayın
 Artık masanın çevresine yeşil bir kenarlık koyabiliriz.`SetBorder()` Tablonun her iki tarafı için yöntem. Bu örnekte 1,5 punto kalınlığında ve yeşil renkte "Tek" tipi bordür kullanıyoruz.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Adım 7: Hücreleri arka plan rengiyle doldurun.
Tablonun görsel sunumunu iyileştirmek için hücreleri zemin arka plan rengiyle doldurabiliriz.

fikir. Bu örnekte açık yeşil renk kullanıyoruz.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Adım 8: Değiştirilen belgeyi kaydedin
Son olarak değiştirilen belgeyi bir dosyaya kaydediyoruz. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak bir tabloya anahat kenarlığı uyguladınız.

### Aspose.Words for .NET kullanarak Anahat Kenarlığını Uygula için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Tabloyu sayfanın ortasına hizalayın.
	table.Alignment = TableAlignment.Center;
	//Tablodaki mevcut sınırları temizleyin.
	table.ClearBorders();
	// Masanın çevresine yeşil bir kenarlık koyun ancak içine değil.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Hücreleri açık yeşil düz renkle doldurun.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir tabloya anahat kenarlığının nasıl uygulanacağını öğrendik. Bu adım adım kılavuzu izleyerek bu işlevselliği C# projelerinize kolayca entegre edebilirsiniz. Tablo formatını değiştirmek belge işlemenin önemli bir yönüdür ve Aspose.Words bunu başarmak için güçlü ve esnek bir API sunar. Bu bilgiyle Word belgelerinizin görsel sunumunu geliştirebilir ve belirli gereksinimleri karşılayabilirsiniz.
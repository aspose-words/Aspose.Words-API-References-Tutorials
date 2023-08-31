---
title: Anahat Kenarlığını Uygula
linktitle: Anahat Kenarlığını Uygula
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir tabloya dış hat kenarlığı uygulamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir tabloya ana hat kenarlığı uygulama sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizdeki tablo kenarlıklarını nasıl değiştireceğinizi net bir şekilde anlayacaksınız.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Word belgenizin saklandığı yer burasıdır. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin
 Ardından, Word belgesini bir örneğine yüklemeniz gerekir.`Document` sınıf.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. Adım: Tabloya erişin
 Anahat kenarlığı uygulamak için belgedeki tabloya erişmemiz gerekir. bu`Table` class, Aspose.Words'te bir tabloyu temsil eder.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 4. Adım: Tabloyu sayfanın ortasına hizalayın
 Şimdi tabloyu kullanarak sayfanın ortasına hizalayabiliriz.`Alignment` tablonun özelliği.

```csharp
table. Alignment = Table Alignment. Center;
```

## 5. Adım: Mevcut tablo kenarlıklarını silin
Yeni bir anahat kenarlığıyla başlamak için önce tablodaki mevcut tüm sınırları silmemiz gerekir. Bu, kullanılarak yapılabilir`ClearBorders()` yöntem.

```csharp
table. ClearBorders();
```

## Adım 6: Tablonun etrafında yeşil bir kenarlık tanımlayın
 Artık tablonun çevresine yeşil bir çerçeve çizebiliriz.`SetBorder()` tablonun her tarafı için yöntem. Bu örnekte, 1,5 punto kalınlığında ve yeşil renkli "Single" tipi bir bordür kullanıyoruz.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## 7. Adım: Hücreleri arka plan rengiyle doldurun
Tablonun görsel sunumunu iyileştirmek için hücreleri zemin arka plan rengiyle doldurabiliriz.

fikir. Bu örnekte açık yeşil bir renk kullanıyoruz.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## 8. Adım: Değiştirilen belgeyi kaydedin
Son olarak, değiştirilen belgeyi bir dosyaya kaydediyoruz. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak bir tabloya ana hat kenarlığı uyguladınız.

### Aspose.Words for .NET kullanarak Apply Outline Border için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Tabloyu sayfanın ortasına hizalayın.
	table.Alignment = TableAlignment.Center;
	//Tablodaki mevcut tüm sınırları temizleyin.
	table.ClearBorders();
	// Masanın etrafına yeşil bir kenarlık koyun ama içine değil.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Hücreleri açık yeşil düz renkle doldurun.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir tabloya ana hat kenarlığı uygulamayı öğrendik. Bu adım adım kılavuzu izleyerek, bu işlevi C# projelerinize kolayca entegre edebilirsiniz. Tablo biçimlendirmesinin manipüle edilmesi belge işlemenin önemli bir yönüdür ve Aspose.Words bunu başarmak için güçlü ve esnek bir API sunar. Bu bilgiyle, Word belgelerinizin görsel sunumunu geliştirebilir ve belirli gereksinimleri karşılayabilirsiniz.
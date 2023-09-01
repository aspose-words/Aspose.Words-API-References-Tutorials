---
title: Kenarlıklı Tablo Oluştur
linktitle: Kenarlıklı Tablo Oluştur
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak kenarlıklı bir tablo oluşturmaya yönelik adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

Bu eğitimde, Aspose.Words for .NET kullanarak kenarlıklı bir tablo oluşturmak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.Words for .NET kullanarak Word belgelerinizde özel kenarlıklara sahip bir tablonun nasıl oluşturulacağını öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Burası Word belgenizin saklandığı yerdir. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Mevcut belgeyi yükleyin
 Daha sonra mevcut Word belgesini bir örneğine yüklemeniz gerekir.`Document` sınıf.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. Adım: Tabloya erişin ve mevcut sınırları kaldırın
 Kenarlıklı tabloyu oluşturmaya başlamak için belgedeki tabloya gitmemiz ve mevcut kenarlıkları kaldırmamız gerekiyor.`ClearBorders()` yöntemi tablodaki tüm sınırları kaldırır.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## Adım 4: Tablo Kenarlıklarını Ayarlayın
 Artık tablo kenarlıklarını aşağıdaki komutu kullanarak ayarlayabiliriz:`SetBorders()` yöntem. Bu örnekte 1,5 punto kalınlığında yeşil renkli bir bordür kullanıyoruz.

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## 5. Adım: Değiştirilen belgeyi kaydedin
Son olarak değiştirilen belgeyi bir dosyaya kaydediyoruz. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak özel kenarlıklara sahip bir tablo oluşturdunuz.

### Aspose.Words for .NET kullanarak Kenarlıklı Tablo Oluşturma için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Tablodaki mevcut sınırları temizleyin.
	table.ClearBorders();
	// Masanın çevresine ve içine yeşil bir kenarlık koyun.
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak kenarlıklı bir tablonun nasıl oluşturulacağını öğrendik. Bu adım adım kılavuzu izleyerek Word belgelerinizdeki tablo kenarlıklarınızı kolayca özelleştirebilirsiniz. Aspose.Words, belgelerinizdeki tabloları düzenlemek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle Word belgelerinizin görsel sunumunu geliştirebilir ve özel ihtiyaçlarınızı karşılayabilirsiniz.
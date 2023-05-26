---
title: Tablodaki Metni Değiştir
linktitle: Tablodaki Metni Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki tablodaki metni nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-text-in-table/
---

Bu makalede, Aspose.Words for .NET kitaplığında Tablodaki Metin Değiştir işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesindeki bir tablonun içindeki belirli metni bulmanızı ve değiştirmenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi yükleyin

 Bir tabloda metin değiştirmeyi kullanmaya başlamadan önce, belgeyi Aspose.Words for .NET'e yüklememiz gerekiyor. Bu, kullanılarak yapılabilir`Document` sınıf ve belge dosyası yolunu belirterek:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## 2. Adım: Panoya erişin

 Belge yüklendikten sonra, metin değiştirmeyi gerçekleştirmek istediğimiz tabloya gitmemiz gerekiyor. Örneğimizde,`GetChild` ile yöntem`NodeType.Table` belgedeki ilk tabloyu almak için parametre:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## 3. Adım: Metin Değiştirme Gerçekleştirin

 şimdi biz kullanıyoruz`Range.Replace` dizideki metin değiştirmeyi gerçekleştirme yöntemi. Örneğimizde, "Havuç" kelimesinin tüm oluşumlarını "Yumurta" ile değiştiriyoruz.`FindReplaceOptions` ile seçenek`FindReplaceDirection.Forward` arama yönü Ayrıca tablonun son satırının son hücresindeki "50" değerini "20" ile değiştiriyoruz:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## 4. Adım: Düzenlenen belgeyi kaydedin

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words for .NET Bir belgeyi yüklemek, tabloya erişmek, metin değiştirmeyi gerçekleştirmek ve değiştirilen belgeyi kaydetmek için adım adım bir kılavuz izledik.

### Aspose.Words for .NET kullanarak Tablodaki Metni Değiştir için örnek kaynak kodu

Aspose.Words for .NET ile bir tabloda metin değiştirmeyi kullanmayı gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Çözüm

Bu yazıda, Aspose'un Tablodaki Metin Değiştir işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik.

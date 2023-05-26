---
title: Tabloyu İçeriğe Otomatik Sığdır
linktitle: Tabloyu İçeriğe Otomatik Sığdır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki tabloyu içeriğine otomatik olarak sığdırmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/auto-fit-table-to-contents/
---

Bu öğreticide, C# kullanarak bir Word belgesindeki bir tabloyu içeriğine otomatik olarak sığdırmak için Aspose.Words for .NET'i nasıl kullanacağımızı öğreneceğiz. Bu işlevselliğe ulaşmak için adım adım kod yazma sürecinden geçeceğiz. Bu eğitimin sonunda, Word belgelerindeki tabloları programlı olarak nasıl değiştireceğinizi net bir şekilde anlayacaksınız.

## 1. Adım: Projeyi kurun
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Word belgesini yükleyin
Tablo ile çalışmaya başlamak için tabloyu içeren Word belgesini yüklememiz gerekiyor. Bu adımları takip et:

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Word belgesini yükleyin
Document doc = new Document(dataDir + "Tables.docx");
```

"BELGE DİZİNİNİZİ" belgenizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Tabloya erişin ve tabloyu içeriğe otomatik olarak sığdırın
Ardından, belge içindeki tabloya erişmemiz ve otomatik sığdırma davranışını uygulamamız gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Tabloya erişin
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Tabloyu içeriğine otomatik sığdır
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Burada, türün ilk alt düğümünü yayınlıyoruz`Table` belgeden ve ardından kullanarak`AutoFit` ile yöntem`AutoFitToContents` tablo genişliğini içeriğine uyacak şekilde ayarlama davranışı.

## 4. Adım: Değiştirilen belgeyi kaydedin
Son olarak, değiştirilen belgeyi otomatik sığdırılan tabloyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Tabloyu İçeriğe Otomatik Sığdır için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tabloyu içeriğine otomatik olarak sığdırmayı öğrendik. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki tabloları programlı olarak değiştirebilirsiniz. Bu, tablo genişliğini içeriğine göre dinamik olarak ayarlamanıza olanak tanıyarak daha profesyonel ve görsel olarak çekici bir belge sağlar.
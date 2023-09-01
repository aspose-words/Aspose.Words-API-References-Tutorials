---
title: Tabloyu İçeriğe Otomatik Sığdır
linktitle: Tabloyu İçeriğe Otomatik Sığdır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesindeki bir tabloyu içeriğine nasıl otomatik olarak sığdıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/auto-fit-table-to-contents/
---

Bu eğitimde, C# kullanarak bir Word belgesindeki bir tabloyu içeriğine otomatik olarak sığdırmak için Aspose.Words for .NET'i nasıl kullanacağımızı öğreneceğiz. Bu işlevselliğe ulaşmak için kod yazma sürecini adım adım gerçekleştireceğiz. Bu eğitimin sonunda, Word belgelerindeki tabloları programlı olarak nasıl değiştireceğiniz konusunda net bir anlayışa sahip olacaksınız.

## 1. Adım: Projeyi ayarlayın
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Word belgesini yükleyin
Kelime İşleme'yi tabloyla başlatmak için tabloyu içeren Word belgesini yüklememiz gerekir. Bu adımları takip et:

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Word belgesini yükleyin
Document doc = new Document(dataDir + "Tables.docx");
```

"BELGE DİZİNİ"ni belgenizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Tabloya erişin ve onu içeriğe otomatik olarak sığdırın
Daha sonra belge içindeki tabloya erişmemiz ve otomatik sığdırma davranışını uygulamamız gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Tabloya erişme
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Tabloyu içeriğine otomatik olarak sığdır
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Burada türün ilk alt düğümünü yayınlıyoruz`Table` belgeden ve ardından kullanarak`AutoFit` yöntemi ile`AutoFitToContents` Tablo genişliğini içeriğine uyacak şekilde ayarlama davranışı.

## 4. Adım: Değiştirilen belgeyi kaydedin
Son olarak, değiştirilen belgeyi otomatik takılan tabloyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

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
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tabloyu içeriğine nasıl otomatik olarak sığdıracağımızı öğrendik. Adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki tabloları programlı olarak değiştirebilirsiniz. Bu, tablonun genişliğini içeriğe göre dinamik olarak ayarlamanıza olanak tanıyarak daha profesyonel ve görsel açıdan çekici bir belge sunar.
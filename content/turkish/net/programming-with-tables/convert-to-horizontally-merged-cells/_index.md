---
title: Yatay Olarak Birleştirilmiş Hücrelere Dönüştür
linktitle: Yatay Olarak Birleştirilmiş Hücrelere Dönüştür
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde tablo hücrelerini yatay olarak birleştirilmiş hücrelere nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

Bu eğitimde, Aspose.Words for .NET'i kullanarak tablo hücrelerini bir Word belgesinde yatay olarak birleştirilmiş hücrelere nasıl dönüştüreceğimizi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablo hücrelerini programlı olarak değiştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tabloya erişme
Kelime İşleme'yi tabloyla başlatmak için onu içeren belgeyi yüklememiz ve ona erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Diziye erişim
Table table = doc.FirstSection.Body.Tables[0];
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca belgenin yatay olarak birleştirilmiş hücrelere sahip bir tablo içerdiğinden emin olun.

## 3. Adım: Yatay olarak birleştirilmiş hücrelere dönüştürün
 Daha sonra tablo hücrelerini yatay olarak birleştirilmiş hücrelere dönüştüreceğiz.`ConvertToHorizontallyMergedCells()` yöntem. Aşağıdaki kodu kullanın:

```csharp
// Yatay olarak birleştirilmiş hücrelere dönüştür
table. ConvertToHorizontallyMergedCells();
```

 Burada sadece şunu diyoruz:`ConvertToHorizontallyMergedCells()` Dönüşümü gerçekleştirmek için dizideki yöntem.

### Aspose.Words for .NET kullanarak Yatay Birleştirilmiş Hücrelere Dönüştürme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Artık birleştirilmiş hücrelerin uygun birleştirme bayrakları var.
	table.ConvertToHorizontallyMergedCells();
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde tablo hücrelerini yatay olarak birleştirilmiş hücrelere nasıl dönüştüreceğimizi öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, Word belgelerinizdeki tablo hücrelerini programlı olarak değiştirebilirsiniz. Bu özellik, verilerinizi esnek ve kişiselleştirilmiş bir şekilde bir tabloda yönetmenize ve düzenlemenize olanak tanır.
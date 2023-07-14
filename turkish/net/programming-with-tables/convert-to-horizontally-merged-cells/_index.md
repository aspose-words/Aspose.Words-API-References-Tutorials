---
title: Yatay Birleştirilmiş Hücrelere Dönüştür
linktitle: Yatay Birleştirilmiş Hücrelere Dönüştür
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinde tablo hücrelerini yatay olarak birleştirilmiş hücrelere dönüştürmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

Bu öğreticide, bir Word belgesinde tablo hücrelerini yatay olarak birleştirilmiş hücrelere dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablo hücrelerini programlı olarak değiştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme ve tabloya erişme
Tablo ile Sözcük İşleme başlatmak için tabloyu içeren belgeyi yüklememiz ve tabloya erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Diziye erişim
Table table = doc.FirstSection.Body.Tables[0];
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca, belgenin yatay olarak birleştirilmiş hücrelere sahip bir tablo içerdiğinden emin olun.

## 3. Adım: Yatay olarak birleştirilmiş hücrelere dönüştürün
 Ardından, tablo hücrelerini yatay olarak birleştirilmiş hücrelere dönüştüreceğiz.`ConvertToHorizontallyMergedCells()` yöntem. Aşağıdaki kodu kullanın:

```csharp
// Yatay olarak birleştirilmiş hücrelere dönüştür
table. ConvertToHorizontallyMergedCells();
```

 Burada sadece diyoruz`ConvertToHorizontallyMergedCells()` dönüştürmeyi gerçekleştirmek için dizideki yöntem.

### Aspose.Words for .NET kullanarak Yatay Olarak Birleştirilmiş Hücrelere Dönüştürmek için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Artık birleştirilmiş hücrelerde uygun birleştirme bayrakları var.
	table.ConvertToHorizontallyMergedCells();
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde tablo hücrelerinin yatay olarak birleştirilmiş hücrelere nasıl dönüştürüleceğini öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki tablo hücrelerini programlı olarak değiştirebilirsiniz. Bu özellik, verilerinizi bir tabloda esnek ve kişiselleştirilmiş bir şekilde yönetmenize ve düzenlemenize olanak tanır.
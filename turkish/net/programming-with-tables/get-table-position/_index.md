---
title: Masa Konumunu Alın
linktitle: Masa Konumunu Alın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki bir tablonun konumunu nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/get-table-position/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablonun konumunu nasıl alacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablo konumlandırma özelliklerini programlı olarak elde edebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme ve tabloya erişme
Tablo ile Sözcük İşleme başlatmak için tabloyu içeren belgeyi yüklememiz ve tabloya erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Tables.docx");

// Diziye erişim
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca, belgenin konumunu almak istediğiniz tabloyu içerdiğinden emin olun.

## 3. Adım: Dizi Konumlandırma Özelliklerini Alma
Ardından, dizinin konumlandırma tipini kontrol edeceğiz ve uygun konumlandırma özelliklerini elde edeceğiz. Aşağıdaki kodu kullanın:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Burada, dizinin kayan tipte olup olmadığını kontrol etmek için bir koşul kullanıyoruz. Eğer öyleyse, yazdırıyoruz`RelativeHorizontalAlignment` Ve`RelativeVerticalAlignment` tablonun göreli yatay ve dikey hizalamasını elde etmek için özellikler. Aksi takdirde, yazdırırız`Alignment` dizi hizalamasını almak için özellik.

### Aspose.Words for .NET kullanarak Get Table Position için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablonun konumunu nasıl alacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak Word belgelerinizde programlı olarak tablo konumlandırma özellikleri elde edebilirsiniz. Bu özellik, dizileri belirli konumlarına göre analiz etmenize ve değiştirmenize olanak tanır.
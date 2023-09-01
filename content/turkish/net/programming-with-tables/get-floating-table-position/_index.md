---
title: Yüzen Masa Konumunu Alın
linktitle: Yüzen Masa Konumunu Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde kayan tabloların konumunu nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/get-floating-table-position/
---

Bu derste, Aspose.Words for .NET'i kullanarak bir Word belgesinde kayan tablonun konumunu nasıl elde edeceğimizi öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki kayan tablonun konumlandırma özelliklerini programlı olarak elde edebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tablolara erişme
Kelime İşleme'yi tablolarla başlatmak için onları içeren belgeyi yüklememiz ve onlara erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca belgenin kayan tablolar içerdiğinden emin olun.

## Adım 3: Kayan Tablo Konumlandırma Özelliklerini Alma
Daha sonra, belgedeki tüm tabloları gözden geçireceğiz ve kayan tablo konumlandırma özelliklerini elde edeceğiz. Aşağıdaki kodu kullanın:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Dizi kayan türdeyse konumlandırma özelliklerini yazdırın.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Burada bir kullanıyoruz`foreach` Belgedeki tüm diziler arasında döngü yapmak için döngü. Dizinin float türünde olup olmadığını kontrol ederek kontrol ederiz.`TextWrapping` mülk. Eğer öyleyse, tablonun yatay bağlantı, dikey bağlantı, mutlak yatay ve dikey mesafeler, örtüşme izni, mutlak yatay mesafe ve göreli dikey hizalama gibi konumlandırma özelliklerini yazdırırız.
 
### Aspose.Words for .NET kullanarak Kayan Tablo Konumunu Al için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Tablo kayan tipteyse konumlandırma özelliklerini yazdırın.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde kayan tablonun konumunu nasıl elde edeceğimizi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki kayan tabloların konumlandırma özelliklerini program aracılığıyla elde edebilirsiniz. Bu özellik, kayan tabloları özel ihtiyaçlarınıza göre analiz etmenize ve değiştirmenize olanak tanır.
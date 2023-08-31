---
title: Kayan Tablo Konumunu Alın
linktitle: Kayan Tablo Konumunu Alın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinde kayan tabloların konumunu nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/get-floating-table-position/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde kayan bir tablonun konumunun nasıl alınacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki kayan bir tablonun konumlandırma özelliklerini programlı olarak elde edebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tablolara erişme
Sözcük İşleme'yi tablolarla başlatmak için, onları içeren belgeyi yüklememiz ve bunlara erişmemiz gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca, belgenin kayan tablolar içerdiğinden emin olun.

## 3. Adım: Kayan Tablo Konumlandırma Özelliklerini Alma
Ardından, belgedeki tüm tabloları dolaşacağız ve kayan tablo konumlandırma özelliklerini elde edeceğiz. Aşağıdaki kodu kullanın:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Dizi kayan bir türse, konumlandırma özelliklerini yazdırın.
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

 Burada bir kullanıyoruz`foreach` belgedeki tüm diziler arasında döngü yapmak için döngü. Kontrol ederek dizinin kayan tip olup olmadığını kontrol ederiz.`TextWrapping` mülk. Öyleyse, tablonun yatay bağlantı, dikey bağlantı, mutlak yatay ve dikey mesafeler, örtüşme izni, mutlak yatay mesafe ve göreli dikey hizalama gibi konumlandırma özelliklerini yazdırırız.
 
### Aspose.Words for .NET kullanarak Kayan Tablo Konumunu Getir için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Tablo kayan türdeyse, konumlandırma özelliklerini yazdırın.
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
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde kayan bir tablonun konumunun nasıl alınacağını öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki kayan tabloların konumlandırma özelliklerini programlı olarak elde edebilirsiniz. Bu özellik, kayan tabloları özel ihtiyaçlarınıza göre analiz etmenizi ve değiştirmenizi sağlar.
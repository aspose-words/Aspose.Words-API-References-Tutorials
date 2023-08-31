---
title: Tablo Konumunu Al
linktitle: Tablo Konumunu Al
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde bir tablonun konumunu nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/get-table-position/
---

Bu derste Aspose.Words for .NET kullanarak bir Word belgesinde bir tablonun konumunun nasıl alınacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablo konumlandırma özelliklerini programlı olarak alabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tabloya erişme
Kelime İşleme'yi tabloyla başlatmak için onu içeren belgeyi yüklememiz ve ona erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Tables.docx");

// Diziye erişim
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca belgenin konumunu almak istediğiniz tabloyu içerdiğinden emin olun.

## Adım 3: Dizi Konumlandırma Özelliklerini Alma
Daha sonra dizinin konumlandırma tipini kontrol edip uygun konumlandırma özelliklerini alacağız. Aşağıdaki kodu kullanın:

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

 Burada dizinin float tipinde olup olmadığını kontrol etmek için bir koşul kullanıyoruz. Eğer öyleyse, yazdırırız`RelativeHorizontalAlignment` Ve`RelativeVerticalAlignment` Tablonun göreceli yatay ve dikey hizalamasını elde etmek için özellikler. Aksi halde yazdırırız`Alignment` Dizi hizalamasını almak için özellik.

### Aspose.Words for .NET kullanarak Tablo Konumunu Al için örnek kaynak kodu 

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
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde bir tablonun konumunu nasıl elde edeceğimizi öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki tablo konumlandırma özelliklerini programlı olarak alabilirsiniz. Bu özellik, dizileri belirli konumlarına göre analiz etmenize ve değiştirmenize olanak tanır.
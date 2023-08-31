---
title: Yüzer Tabla Konumu
linktitle: Yüzer Tabla Konumu
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde bir tabloyu kayan konumda nasıl konumlandıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/floating-table-position/
---

Bu eğitimde, Aspose.Words for .NET'i kullanarak bir tabloyu Word belgesinde kayan konumda konumlandırmayı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki kayan tabloların konumunu ve hizalamasını programlı olarak kontrol edebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme ve tabloya erişme
Kelime İşleme'yi tabloyla başlatmak için onu içeren belgeyi yüklememiz ve ona erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Diziye erişim
Table table = doc.FirstSection.Body.Tables[0];
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca belgenin kayan konumda konumlandırılacak bir tablo içerdiğinden emin olun.

## Adım 3: Yüzen tahtanın konumlandırılması
Daha sonra Aspose.Words for .NET tarafından sağlanan özellikleri kullanarak tabloyu kayan konumda konumlandıracağız. Aşağıdaki kodu kullanın:

```csharp
// Yüzer tablanın konumlandırılması
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Burada şunu kullanıyoruz:`AbsoluteHorizontalDistance` Tablonun sayfanın sol kenarından mutlak yatay mesafesini ayarlama özelliği. Biz de kullanıyoruz`RelativeVerticalAlignment` Tablonun çevresindeki içeriğe göre göreli dikey hizalamasını ayarlama özelliği.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi tablo kayan konumda olacak şekilde kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanılarak Kayan Tablo Konumu için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde bir tabloyu kayan konumda nasıl konumlandıracağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, Word belgelerinizdeki kayan tabloların konumunu ve hizalamasını programlı olarak kontrol edebilirsiniz.
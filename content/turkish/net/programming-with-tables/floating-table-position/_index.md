---
title: Yüzer Masa Konumu
linktitle: Yüzer Masa Konumu
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinde bir tabloyu kayan konumda nasıl konumlandıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/floating-table-position/
---

Bu öğreticide, bir Word belgesinde bir tabloyu kayan bir konumda konumlandırmak için Aspose.Words for .NET'i nasıl kullanacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki kayan tabloların konumunu ve hizalamasını programlı olarak kontrol edebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme ve tabloya erişme
Tablo ile Sözcük İşleme başlatmak için tabloyu içeren belgeyi yüklememiz ve tabloya erişmemiz gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Diziye erişim
Table table = doc.FirstSection.Body.Tables[0];
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun. Ayrıca, belgenin kayan konumda konumlandırılacak bir tablo içerdiğinden emin olun.

## 3. Adım: Yüzer tahtanın konumlandırılması
Ardından, Aspose.Words for .NET tarafından sağlanan özellikleri kullanarak tabloyu kayan bir konumda konumlandıracağız. Aşağıdaki kodu kullanın:

```csharp
// Yüzen tablonun konumlandırılması
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Burada kullandığımız`AbsoluteHorizontalDistance` tablonun sayfanın sol kenarından mutlak yatay uzaklığını ayarlamak için özelliği. biz de kullanıyoruz`RelativeVerticalAlignment` tablonun çevreleyen içeriğe göre dikey hizalamasını ayarlamak için özelliği.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi, tablo kayan bir konumda konumlanmış olarak kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Floating Table Position için örnek kaynak kodu 

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
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde bir tabloyu kayan bir konumda nasıl konumlandıracağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizdeki kayan tabloların konumunu ve hizalamasını program aracılığıyla denetleyebilirsiniz.
---
title: Ölçü Birimleri Arasında Dönüştürme
linktitle: Ölçü Birimleri Arasında Dönüştürme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgedeki ölçü birimleri arasında dönüştürme yapmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/convert-between-measurement-units/
---

Bu eğitimde, Aspose.Words for .NET ile ölçüm birimleri arasında dönüşüm yapmak için C# kaynak kodunu size anlatacağız. Bu özellik, kenar boşluklarını, üstbilgi ve altbilgi mesafelerini vb. farklı ölçü birimlerinde belirtmenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi ve Oluşturucuyu Oluşturma

Bu adımda yeni bir belge oluşturacağız ve yapıcıyı başlatacağız. Aşağıdaki kodu kullanın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Ölçü birimlerini yapılandırın

Şimdi kenar boşlukları, üstbilgi ve altbilgi mesafeleri vb. değerlerini farklı ölçü birimlerine dönüştüreceğiz. Değerleri belirli ölçü birimlerinde belirtmek için aşağıdaki kodu kullanın:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Bu kod şunu kullanır:`ConvertUtil` Belirtilen değerleri inç'e ( inç) dönüştürmek için Aspose.Words sınıfı`InchToPoint`). Ayrıca, mevcut diğer dönüştürme yöntemlerini de kullanabilirsiniz.`ConvertUtil` Değerleri diğer ölçü birimlerine dönüştürmek için sınıf.

### Aspose.Words for .NET kullanarak Ölçü Birimleri Arasında Dönüştürme için örnek kaynak kodu

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Artık Aspose.Words for .NET kullanarak bir belgede kenar boşluklarını, üstbilgi ve altbilgi mesafelerini vb. belirtirken ölçü birimleri arasında nasıl dönüşüm yapacağınızı öğrendiniz. Bu eğitimde verilen adım adım kılavuzu takip ederek istediğiniz ölçü birimlerindeki değerleri kendi belgelerinizde kolayca belirtebilirsiniz.
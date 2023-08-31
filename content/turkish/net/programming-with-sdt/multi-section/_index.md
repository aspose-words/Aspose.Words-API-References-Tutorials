---
title: Çoklu Bölüm
linktitle: Çoklu Bölüm
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesinde çok bölümlü yapılandırılmış belge etiketlerini nasıl alacağınızı ve işleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/multi-section/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesinde çok bölümlü yapılandırılmış belge etiketleriyle nasıl çalışılacağı açıklanmaktadır. Belgede bulunan bölüm etiketlerini alıp işleyebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin ve Çok Bölümlü Etiketleri Alın
 Word belgesini kullanarak yükleyin`Document` yapıcı, belgenin yolunu parametre olarak iletir. kullanarak belgedeki tüm yapılandırılmış belge etiketi aralığı başlangıç düğümlerini alın.`GetChildNodes` yöntem.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Adım 3: Çok Bölümlü Etiketleri İşleyin
Yapılandırılmış belge etiketi aralığı başlangıç düğümlerinin koleksiyonunu yineleyin. Bu örnekte, her etiketin başlığını konsola yazdırıyoruz. Gereksinimlerinize göre daha fazla işlem gerçekleştirebilirsiniz.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Aspose.Words for .NET kullanan Çoklu Bölüm için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki çok bölümlü yapılandırılmış belge etiketlerini başarıyla aldınız ve işlediniz.
---
title: Çoklu Bölüm
linktitle: Çoklu Bölüm
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki çok bölümlü yapılandırılmış belge etiketlerini nasıl alacağınızı ve işleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/multi-section/
---

Bu öğretici, Aspose.Words for .NET kullanarak bir Word belgesinde çok bölümlü yapılandırılmış belge etiketleriyle nasıl çalışılacağını açıklar. Belgede bulunan bölüm etiketlerini alabilir ve işleyebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin ve Çok Bölümlü Etiketleri Alın
 kullanarak Word belgesini yükleyin.`Document` yapıcı, belgenin yolunu bir parametre olarak iletir. kullanarak belgedeki tüm yapılandırılmış belge etiketi aralığı başlangıç düğümlerini alın.`GetChildNodes` yöntem.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## 3. Adım: Çok Bölümlü Etiketleri İşleyin
Yapılandırılmış belge etiketi aralığı başlangıç düğümlerinin koleksiyonunu yineleyin. Bu örnekte, her etiketin başlığını konsola yazdırıyoruz. Gereksinimlerinize göre daha fazla işlem yapabilirsiniz.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Aspose.Words for .NET kullanan Çoklu Bölüm için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki çok bölümlü yapılandırılmış belge etiketlerini başarıyla aldınız ve işlediniz.
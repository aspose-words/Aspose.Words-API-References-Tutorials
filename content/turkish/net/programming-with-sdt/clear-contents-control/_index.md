---
title: İçerik Kontrolünü Temizle
linktitle: İçerik Kontrolünü Temizle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki kontrolün içeriğini nasıl temizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/clear-contents-control/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki bir SDT'nin içeriğinin nasıl temizleneceğini gösterir. Bir SDT'nin içeriğinin temizlenmesi, içerik denetimi içindeki tüm metinleri veya alt düğümleri kaldırır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin ve StructuredDocumentTag'i Alın
 kullanarak Word belgesini yükleyin.`Document` yapıcı, belgenin yolunu bir parametre olarak iletir. Ardından, istenen`StructuredDocumentTag` belgeden. Bu örnekte, SDT'nin belgedeki ilk alt düğüm olduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. Adım: StructuredDocumentTag'in İçeriğini Temizleyin
 kullanarak SDT'nin içeriğini temizleyin.`Clear` yöntem. Bu, içerik denetimi içindeki tüm metinleri veya alt düğümleri kaldırır.

```csharp
sdt.Clear();
```

## 4. Adım: Belgeyi Kaydedin
 Değiştirilen belgeyi şunu kullanarak kaydedin:`Save`yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.ClearContentsControl.doc" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Aspose.Words for .NET kullanan Clear Contents Control için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki bir StructuredDocumentTag içeriğini başarıyla temizlediniz.
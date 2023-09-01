---
title: İçerik Kontrolünü Temizle
linktitle: İçerik Kontrolünü Temizle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir kontrolün içeriğini nasıl temizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/clear-contents-control/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesindeki SDT içeriğinin nasıl temizleneceği gösterilmektedir. Bir SDT'nin içeriğinin temizlenmesi, içerik kontrolü içindeki tüm metinleri veya alt düğümleri kaldırır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin ve StructuredDocumentTag'i Alın
 Word belgesini kullanarak yükleyin`Document` yapıcı, belgenin yolunu parametre olarak iletir. Daha sonra istediğinizi geri alın`StructuredDocumentTag` belgeden. Bu örnekte SDT'nin belgedeki ilk alt düğüm olduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. Adım: StructuredDocumentTag'in İçeriğini Temizleyin
 kullanarak SDT içeriğini temizleyin.`Clear` yöntem. Bu, içerik kontrolü içindeki tüm metinleri veya alt düğümleri kaldırır.

```csharp
sdt.Clear();
```

## Adım 4: Belgeyi Kaydedin
 Değiştirilen belgeyi kullanarak kaydedin.`Save`yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.ClearContentsControl.doc" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Aspose.Words for .NET kullanan Temiz İçerik Kontrolü için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki StructuredDocumentTag içeriğini başarıyla temizlediniz.
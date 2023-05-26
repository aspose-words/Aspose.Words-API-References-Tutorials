---
title: Onay Kutusunun Mevcut Durumu
linktitle: Onay Kutusunun Mevcut Durumu
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir onay kutusu içerik kontrolünün mevcut durumunu nasıl alacağınızı ve ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/current-state-of-check-box/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki bir onay kutusu içerik kontrolünün mevcut durumunun nasıl alınacağını ve ayarlanacağını açıklar. Geçerli durumuna göre onay kutusunu işaretleyebilir veya işaretini kaldırabilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin ve Onay Kutusu İçerik Denetimini Alın
 kullanarak Word belgesini yükleyin.`Document` yapıcı, belgenin yolunu bir parametre olarak iletir. Ardından, istenen onay kutusu içerik kontrolünü belgeden alın. Bu örnekte, onay kutusunun belgedeki ilk yapılandırılmış belge etiketi olduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. Adım: Mevcut Durumuna Göre Onay Kutusunu İşaretleyin veya İşaretini Kaldırın
 Alınan yapılandırılmış belge etiketinin türünde olup olmadığını kontrol edin`SdtType.Checkbox` . Eğer öyleyse,`Checked` içerik kontrolünün özelliği`true` kutuyu işaretlemek için Aksi takdirde, işaretlemeden bırakabilirsiniz.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## 4. Adım: Belgeyi Kaydedin
 Değiştirilen belgeyi belirtilen dizine kaydedin.`Save`yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.CurrentStateOfCheckBox.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Aspose.Words for .NET kullanan Current State Of Check Box için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Belgeden ilk içerik denetimini alın.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki bir onay kutusu içerik kontrolünü başarıyla aldınız ve mevcut durumunu ayarladınız.
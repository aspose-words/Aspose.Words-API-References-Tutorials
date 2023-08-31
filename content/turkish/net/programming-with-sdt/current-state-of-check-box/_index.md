---
title: Onay Kutusunun Mevcut Durumu
linktitle: Onay Kutusunun Mevcut Durumu
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesindeki onay kutusu içerik kontrolünün mevcut durumunu nasıl alacağınızı ve ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/current-state-of-check-box/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesindeki onay kutusu içerik kontrolünün mevcut durumunun nasıl alınacağı ve ayarlanacağı açıklanmaktadır. Geçerli durumuna göre onay kutusunu işaretleyebilir veya işaretini kaldırabilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin ve Onay Kutusu İçerik Denetimini Alın
 Word belgesini kullanarak yükleyin`Document` yapıcı, belgenin yolunu parametre olarak iletir. Daha sonra belgeden istenen onay kutusu içerik denetimini alın. Bu örnekte onay kutusunun belgedeki ilk yapılandırılmış belge etiketi olduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Adım 3: Mevcut Durumuna Göre Onay Kutusunu İşaretleyin veya İşaretini Kaldırın
 Alınan yapılandırılmış belge etiketinin türünde olup olmadığını kontrol edin`SdtType.Checkbox` . Eğer öyleyse, ayarlayın`Checked` içerik kontrolünün özelliği`true` kutuyu işaretlemek için. Aksi halde işaretlemeden bırakabilirsiniz.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Adım 4: Belgeyi Kaydedin
 Değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydedin:`Save`yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.CurrentStateOfCheckBox.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Aspose.Words for .NET kullanan Mevcut Onay Kutusu Durumu için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Belgeden ilk içerik kontrolünü alın.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki onay kutusu içerik kontrolünü başarıyla aldınız ve mevcut durumunu ayarladınız.
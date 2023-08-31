---
title: Açılan Kutu İçerik Kontrolü
linktitle: Açılan Kutu İçerik Kontrolü
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde Birleşik Giriş Kutusu İçerik Denetimi'nin nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/combo-box-content-control/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesinde Açılan Kutu İçerik Denetiminin nasıl oluşturulacağı açıklanmaktadır. Birleşik giriş kutusu içerik kontrolleri, kullanıcıların açılır listeden bir öğe seçmesine olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge ve StructuredDocumentTag Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`StructuredDocumentTag` Birleşik giriş kutusu içerik kontrolünü temsil etmek için. Belirt`SdtType.ComboBox` tür olarak ve`MarkupLevel.Block` Blok düzeyinde bir açılan kutu oluşturmak için işaretleme düzeyi olarak.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Adım 3: Birleşik Giriş Kutusuna Öğe Ekleme
 kullanarak açılan kutuya öğeler ekleyin.`ListItems` mülkiyeti`StructuredDocumentTag` Her öğe bir ile temsil edilir`SdtListItem` bir görüntü metni ve bir değer alan nesne. Bu örnekte açılan kutuya üç öğe ekliyoruz.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Adım 4: StructuredDocumentTag'i Belgeye Ekleme
 Açılan kutu içerik kontrolünü kullanarak belgenin gövdesine ekleyin.`AppendChild` belgenin ilk bölümünün gövdesinin yöntemi.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Adım 5: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.ComboBoxContentControl.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Aspose.Words for .NET kullanan Birleşik Giriş Kutusu İçerik Kontrolü için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde başarılı bir şekilde Birleşik Giriş Kutusu İçerik Denetimi oluşturdunuz.
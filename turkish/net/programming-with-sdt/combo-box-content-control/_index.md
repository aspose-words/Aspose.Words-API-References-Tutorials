---
title: Açılan Kutu İçeriği Kontrolü
linktitle: Açılan Kutu İçeriği Kontrolü
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesinde Birleşik Giriş Kutusu İçerik Kontrolü oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/combo-box-content-control/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesinde Birleşik Giriş Kutusu İçerik Kontrolü'nün nasıl oluşturulacağını açıklar. Birleşik giriş kutusu içerik denetimleri, kullanıcıların açılır listeden bir öğe seçmesine olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge ve StructuredDocumentTag Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`StructuredDocumentTag` birleşik giriş kutusu içerik denetimini temsil etmek için. Belirtin`SdtType.ComboBox` tip olarak ve`MarkupLevel.Block` blok düzeyinde birleşik giriş kutusu oluşturmak için biçimlendirme düzeyi olarak.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## 3. Adım: Açılan Kutuya Öğeler Ekleyin
 kullanarak birleşik giriş kutusuna öğe ekleyin.`ListItems`mülkiyeti`StructuredDocumentTag` Her öğe bir ile temsil edilir`SdtListItem` bir görüntüleme metni ve bir değer alan nesne. Bu örnekte, açılan kutuya üç öğe ekliyoruz.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## 4. Adım: StructuredDocumentTag'i Belgeye Ekleyin
 Birleşik giriş kutusu içerik denetimini belgenin gövdesine şu şekilde ekleyin:`AppendChild` belgenin ilk bölümünün gövdesi yöntemi.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## 5. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.ComboBoxContentControl.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Aspose.Words for .NET kullanan Combo Box Content Control için örnek kaynak kodu 

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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde Birleşik Giriş Kutusu İçerik Kontrolü'nü başarıyla oluşturdunuz.
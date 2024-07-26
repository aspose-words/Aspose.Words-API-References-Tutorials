---
title: Zengin Metin Kutusu İçerik Kontrolü
linktitle: Zengin Metin Kutusu İçerik Kontrolü
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak metin biçimlendirme ve stillendirmeyi etkinleştirerek bir Word belgesinde zengin metin kutusu içerik kontrolünü nasıl oluşturacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/rich-text-box-content-control/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesinde zengin metin kutusu içerik kontrolünün nasıl oluşturulacağı gösterilmektedir. Zengin metin kutusu içerik kontrolleri, kullanıcıların çeşitli stil ve biçimlendirme seçenekleriyle metin girmesine ve biçimlendirmesine olanak tanır.

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
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`StructuredDocumentTag` zengin metin kutusu içerik kontrolünü temsil etmek için. Belirt`SdtType.RichText` tür olarak ve`MarkupLevel.Block` Blok düzeyinde zengin metin kutusu oluşturmak için işaretleme düzeyi olarak.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## 3. Adım: Zengin Metin İçeriğini Oluşturun ve Biçimlendirin
Bir paragraf oluşturun ve zengin metin içeriğini temsil edecek şekilde çalıştırın. Renk, yazı tipi vb. gibi metin ve biçimlendirme seçeneklerini ayarlayın.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## 4. Adım: Zengin Metin İçeriğini İçerik Kontrolüne Ekleme
 Zengin metin içeriğine sahip paragrafı şuraya ekleyin:`ChildNodes` zengin metin kutusu içerik denetiminin toplanması.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Adım 5: İçerik Denetimini Belgeye Ekleme
 Zengin metin kutusu içerik denetimini kullanarak belgenin gövdesine ekleyin.`AppendChild` belgenin ilk bölümünün gövdesinin yöntemi.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Adım 6: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save`yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.RichTextBoxContentControl.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Aspose.Words for .NET kullanan Zengin Metin Kutusu İçerik Kontrolü için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde başarılı bir şekilde zengin metin kutusu içerik kontrolü oluşturdunuz.
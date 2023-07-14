---
title: Zengin Metin Kutusu İçerik Kontrolü
linktitle: Zengin Metin Kutusu İçerik Kontrolü
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'i kullanarak bir Word belgesinde metin biçimlendirme ve stillendirme sağlayan zengin bir metin kutusu içerik denetimi oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/rich-text-box-content-control/
---

Bu eğitim, Aspose.Words for .NET kullanılarak bir Word belgesinde zengin metin kutusu içerik kontrolünün nasıl oluşturulacağını gösterir. Zengin metin kutusu içerik denetimleri, kullanıcıların çeşitli stiller ve biçimlendirme seçenekleriyle metin girmesine ve biçimlendirmesine olanak tanır.

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
 Yeni bir örneğini oluştur`Document` sınıf ve bir`StructuredDocumentTag` zengin metin kutusu içerik denetimini temsil etmek için. Belirtin`SdtType.RichText` tip olarak ve`MarkupLevel.Block` blok düzeyinde bir zengin metin kutusu oluşturmak için biçimlendirme düzeyi olarak.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## 3. Adım: Zengin Metin İçeriğini Oluşturun ve Biçimlendirin
Zengin metin içeriğini temsil etmek için bir paragraf oluşturun ve çalıştırın. Renk, yazı tipi vb. metin ve biçimlendirme seçeneklerini ayarlayın.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## 4. Adım: Zengin Metin İçeriğini İçerik Kontrolüne Ekleyin
Zengin metin içeriğine sahip paragrafı`ChildNodes` zengin metin kutusu içerik denetimi koleksiyonu.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## 5. Adım: İçerik Denetimini Belgeye Ekleyin
 kullanarak zengin metin kutusu içerik denetimini belgenin gövdesine ekleyin.`AppendChild` belgenin ilk bölümünün gövdesi yöntemi.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## 6. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.RichTextBoxContentControl.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Aspose.Words for .NET kullanan Zengin Metin Kutusu İçerik Kontrolü için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde başarılı bir şekilde zengin metin kutusu içeriği kontrolü oluşturdunuz.
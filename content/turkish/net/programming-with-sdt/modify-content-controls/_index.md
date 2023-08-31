---
title: İçerik Kontrollerini Değiştirin
linktitle: İçerik Kontrollerini Değiştirin
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içerik kontrollerindeki metinleri, açılır listeleri ve görüntüleri nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/modify-content-controls/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki farklı içerik kontrol türlerinin nasıl değiştirileceğini açıklar. Bir açılır listenin metnini, seçilen değerini güncelleyebilir veya içerik denetimlerinde bir resmi değiştirebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin ve İçerik Kontrollerini Yineleyin
 kullanarak Word belgesini yükleyin.`Document`yapıcı, belgenin yolunu bir parametre olarak iletir. kullanarak belgedeki tüm yapılandırılmış belge etiketlerini yineleyin.`foreach` döngü.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // İçerik denetimi türüne göre eylemler gerçekleştirin
}
```

## 3. Adım: Düz Metin İçerik Kontrolünü Değiştirin
 türündeki içerik denetimleri için`SdtType.PlainText`, mevcut tüm alt öğeleri kaldırın, yeni bir paragraf oluşturun ve istenen metinle bir çalıştırma ekleyin.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## 4. Adım: Açılır Liste İçerik Denetimini Değiştirin
 türündeki içerik denetimleri için`SdtType.DropDownList` , seçilen değeri belirli bir değere ayarlayarak güncelleyin.`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## 5. Adım: Resim İçerik Kontrolünü Değiştirin
 türündeki içerik denetimleri için`SdtType.Picture`, içerik denetimi içindeki şekli alın ve görüntüsünü yenisiyle değiştirin.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## 6. Adım: Değiştirilen Belgeyi Kaydedin
 Değiştirilen belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.ModifyContentControls.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Aspose.Words for .NET kullanarak Modify Content Controls için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki farklı içerik kontrollerini başarıyla değiştirdiniz.
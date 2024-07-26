---
title: İçerik Kontrollerini Değiştirin
linktitle: İçerik Kontrollerini Değiştirin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesindeki içerik kontrollerindeki metni, açılır listeleri ve görüntüleri nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/modify-content-controls/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesindeki farklı içerik kontrol türlerinin nasıl değiştirileceği açıklanmaktadır. İçerik kontrollerindeki metni, açılır listenin seçili değerini güncelleyebilir veya bir resmi değiştirebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin ve İçerik Kontrolleri Üzerinde Yineleyin
 Word belgesini kullanarak yükleyin`Document` yapıcı, belgenin yolunu parametre olarak iletir. Bir belge kullanarak belgedeki tüm yapılandırılmış belge etiketlerini yineleyin.`foreach` döngü.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // İçerik kontrolünün türüne göre eylemler gerçekleştirin
}
```

## 3. Adım: Düz Metin İçerik Denetimini Değiştirin
 Türün içerik kontrolleri için`SdtType.PlainText`, mevcut tüm alt öğeleri kaldırın, yeni bir paragraf oluşturun ve istediğiniz metni içeren bir satır ekleyin.

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
 Türün içerik kontrolleri için`SdtType.DropDownList` , seçilen değeri belirli bir değere ayarlayarak güncelleyin`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## 5. Adım: Resim İçeriği Kontrolünü Değiştirin
 Türün içerik kontrolleri için`SdtType.Picture`, içerik denetimi içindeki şekli alın ve görüntüsünü yenisiyle değiştirin.

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

## Adım 6: Değiştirilen Belgeyi Kaydedin
 Değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydedin:`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.ModifyContentControls.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Aspose.Words for .NET kullanarak İçerik Kontrollerini Değiştirmek için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki farklı içerik kontrol türlerini başarıyla değiştirdiniz.
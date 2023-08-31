---
title: İçerik Kontrol Rengini Ayarla
linktitle: İçerik Kontrol Rengini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içerik kontrolünün rengini nasıl ayarlayacağınızı ve görünümünü nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/set-content-control-color/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesindeki içerik kontrolünün renginin nasıl ayarlanacağı açıklanmaktadır. Renklerini değiştirerek içerik kontrollerinin görünümünü özelleştirebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin ve İçerik Denetimini Alın
 Word belgesini kullanarak yükleyin`Document` yapıcı, belgenin yolunu parametre olarak iletir. İstediğiniz içerik kontrolünü belgeden alın. Bu örnekte içerik denetiminin belgedeki ilk yapılandırılmış belge etiketi olduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. Adım: İçerik Kontrol Rengini Ayarlayın
 Bir atayarak içerik kontrolünün rengini ayarlayın.`Color` değeri`Color` yapılandırılmış belge etiketinin özelliği. Bu örnekte rengi kırmızı olarak ayarladık.

```csharp
sdt.Color = Color.Red;
```

## Adım 4: Belgeyi Kaydedin
 Değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydedin:`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.SetContentControlColor.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Aspose.Words for .NET kullanarak İçerik Kontrol Rengini Ayarlama için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki içerik kontrolünün rengini başarıyla ayarladınız.
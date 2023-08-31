---
title: İçerik Kontrol Rengini Ayarla
linktitle: İçerik Kontrol Rengini Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içerik kontrolünün rengini, görünüşünü özelleştirerek nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/set-content-control-color/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki içerik kontrolünün renginin nasıl ayarlanacağını açıklar. Renklerini değiştirerek içerik denetimlerinin görünümünü özelleştirebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin ve İçerik Denetimini Alın
 kullanarak Word belgesini yükleyin.`Document` yapıcı, belgenin yolunu bir parametre olarak iletir. Belgeden istenen içerik denetimini alın. Bu örnekte, içerik kontrolünün belgedeki ilk yapılandırılmış belge etiketi olduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. Adım: İçerik Kontrol Rengini Ayarlayın
 atayarak içerik kontrolünün rengini ayarlayın.`Color` değer`Color` yapılandırılmış belge etiketinin özelliği. Bu örnekte, rengi kırmızı olarak ayarladık.

```csharp
sdt.Color = Color.Red;
```

## 4. Adım: Belgeyi Kaydedin
 Değiştirilen belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.SetContentControlColor.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Aspose.Words for .NET kullanarak Set Content Control Color için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki bir içerik kontrolünün rengini başarıyla ayarladınız.
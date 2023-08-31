---
title: İçerik Kontrol Stilini Ayarla
linktitle: İçerik Kontrol Stilini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Tutarlı formatlama uygulayarak Aspose.Words for .NET kullanarak bir Word belgesinde içerik kontrolünün stilini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/set-content-control-style/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesinde içerik kontrolü stilinin nasıl ayarlanacağı açıklanmaktadır. Tutarlı biçimlendirme için içerik kontrollerine önceden tanımlanmış veya özel stiller uygulayabilirsiniz.

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

## 3. Adım: Stili Alın ve İçerik Kontrolüne Uygulayın
 İstediğiniz stili belgenin stil koleksiyonundan alın. Bu örnekte "Alıntı" stilini kullanarak alıyoruz`StyleIdentifier.Quote` . Ardından, alınan stili şu öğeye atayın:`Style` yapılandırılmış belge etiketinin özelliği.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Adım 4: Belgeyi Kaydedin
 Değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydedin:`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.SetContentControlStyle.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Aspose.Words for .NET kullanarak İçerik Kontrol Stilini Ayarlama için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki içerik kontrolünün stilini başarıyla ayarladınız.
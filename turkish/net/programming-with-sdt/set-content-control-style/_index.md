---
title: İçerik Kontrol Stilini Ayarla
linktitle: İçerik Kontrol Stilini Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Tutarlı biçimlendirme uygulayarak Aspose.Words for .NET kullanarak bir Word belgesinde içerik kontrolünün stilini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/set-content-control-style/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesinde içerik denetimi stilinin nasıl ayarlanacağını açıklar. Tutarlı biçimlendirme için içerik denetimlerine önceden tanımlanmış veya özel stiller uygulayabilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

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

## 3. Adım: Stili Alın ve İçerik Kontrolüne Uygulayın
 Belgenin stiller koleksiyonundan istediğiniz stili alın. Bu örnekte, kullanarak "Alıntı" stilini alıyoruz.`StyleIdentifier.Quote` . Ardından, alınan stili şuna atayın:`Style` yapılandırılmış belge etiketinin özelliği.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## 4. Adım: Belgeyi Kaydedin
 Değiştirilen belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.SetContentControlStyle.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Aspose.Words for .NET kullanarak İçerik Kontrol Stilini Ayarlamak için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde bir içerik kontrolünün stilini başarıyla ayarladınız.
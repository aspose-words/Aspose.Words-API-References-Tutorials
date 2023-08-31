---
title: Görüntüler Klasörünü Ayarla
linktitle: Görüntüler Klasörünü Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Markdown'a dışa aktarırken görüntüler klasörünü nasıl ayarlayacağınızı öğrenin. Daha iyi organizasyon ve entegrasyon için görsellerin yerleşimini özelleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-markdownsaveoptions/set-images-folder/
---

Burada Aspose.Words kütüphanesini .NET kullanarak Markdown dışa aktarma seçenekleri için resim klasörünü ayarlamaya yardımcı olan aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. Bu kodu kullanmadan önce projenize Aspose.Words kütüphanesini eklediğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Resimleri içeren belgenin bulunduğu belge dizininize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: Resimleri içeren belgeyi yükleyin

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Dışa aktarmak istediğimiz görselleri içeren belirtilen belgeyi Markdown seçenekleriyle yüklüyoruz.

## 3. Adım: Markdown dışa aktarma seçenekleri için resimler klasörünü ayarlayın

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Bir örneğini oluşturuyoruz`MarkdownSaveOptions` ve kullanarak resimler klasörünün yolunu ayarlayın.`ImagesFolder` mülk. Dışa aktarılan görüntüleri kaydetmek istediğiniz klasörün doğru yolunu belirttiğinizden emin olun.

## 4. Adım: Belgeyi Markdown dışa aktarma seçenekleriyle kaydedin

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Belirtilen Markdown dışa aktarma seçeneklerini kullanarak belgeyi bir bellek akışına kaydediyoruz. Daha sonra Markdown içeriğini bir dosyaya kaydetmek gibi diğer işlemleri gerçekleştirmek için akışı kullanabilirsiniz.

### Aspose.Words for .NET ile MarkdownSaveOptions için resim klasörünü ayarlamak için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Bu kaynak kodu, görüntüleri içeren bir belgenin nasıl yükleneceğini ve ardından Markdown dışa aktarma seçenekleri için görüntüler klasörünün nasıl ayarlanacağını gösterir. Belirlenen seçenekler kullanılarak belge daha sonra bir bellek akışına kaydedilir. Bu, Markdown içeriğini dışa aktarırken görüntüler klasörünün konumunu özelleştirmenize olanak tanır.
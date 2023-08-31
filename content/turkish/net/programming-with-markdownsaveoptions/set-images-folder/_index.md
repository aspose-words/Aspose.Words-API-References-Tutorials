---
title: Görüntüler Klasörünü Ayarla
linktitle: Görüntüler Klasörünü Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Markdown'a dışa aktarırken resimler klasörünü nasıl ayarlayacağınızı öğrenin. Daha iyi organizasyon ve entegrasyon için görüntülerin yerleşimini özelleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-markdownsaveoptions/set-images-folder/
---

Aspose.Words library for .NET kullanarak Markdown dışa aktarma seçenekleri için görseller klasörünü ayarlamaya yardımcı olan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. Bu kodu kullanmadan önce Aspose.Words kütüphanesini projenize dahil ettiğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Görüntüleri içeren belgenin bulunduğu belgeler dizininizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: Resimleri içeren belgeyi yükleyin

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Markdown seçenekleri ile export etmek istediğimiz görselleri içeren belirtilen dökümanı yüklüyoruz.

## 3. Adım: Markdown dışa aktarma seçenekleri için görseller klasörünü ayarlayın

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 örneğini oluşturuyoruz`MarkdownSaveOptions` ve kullanarak resimler klasörünün yolunu ayarlayın.`ImagesFolder` mülk. Dışa aktarılan görüntüleri kaydetmek istediğiniz klasörün yolunu doğru belirttiğinizden emin olun.

## 4. Adım: Belgeyi Markdown dışa aktarma seçenekleriyle kaydedin

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Belirtilen Markdown dışa aktarma seçeneklerini kullanarak belgeyi bir bellek akışına kaydediyoruz. Ardından, Markdown içeriğini bir dosyaya kaydetmek gibi diğer işlemleri gerçekleştirmek için akışı kullanabilirsiniz.

### Aspose.Words for .NET ile MarkdownSaveOptions için görseller klasörünü ayarlamak için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Bu kaynak kodu, görüntüler içeren bir belgenin nasıl yükleneceğini ve ardından Markdown dışa aktarma seçenekleri için görüntüler klasörünün nasıl ayarlanacağını gösterir. Belge daha sonra belirtilen seçenekler kullanılarak bir bellek akışına kaydedilir. Bu, Markdown içeriğini dışa aktarırken görüntüler klasörünün konumunu özelleştirmenizi sağlar.
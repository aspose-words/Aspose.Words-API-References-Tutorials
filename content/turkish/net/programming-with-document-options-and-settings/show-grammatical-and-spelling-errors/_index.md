---
title: Dilbilgisi ve Yazım Hatalarını Göster
linktitle: Dilbilgisi ve Yazım Hatalarını Göster
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgede gramer ve yazım hatalarının görüntülenmesini sağlayan adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Bu eğitimde, Aspose.Words for .NET'te gramer ve yazım hatalarının görüntülenmesini sağlayan C# kaynak kodunu anlatacağız. Bu özellik, bir belgedeki dilbilgisi ve yazım hatalarını görüntülemenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda gramer ve yazım hatalarını görüntülemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Hata Görüntülemeyi Etkinleştirin

Şimdi belgedeki gramer ve yazım hatalarının görüntülenmesini sağlayacağız. Hata görüntülemeyi etkinleştirmek için aşağıdaki kodu kullanın:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Bu kod dilbilgisi hatalarının görüntülenmesini sağlar (`ShowGrammaticalErrors`) ve yazım hataları (`ShowSpellingErrors`) belgede.

### Aspose.Words for .NET Kullanarak Dilbilgisi ve Yazım Hatalarını Gösterme örneği kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgede gramer ve yazım hatalarının görüntülenmesini nasıl etkinleştireceğinizi öğrendiniz. Bu eğitimde verilen adım adım kılavuzu takip ederek bu özelliği kendi belgelerinizde kolayca etkinleştirebilirsiniz.
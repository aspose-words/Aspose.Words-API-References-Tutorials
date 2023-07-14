---
title: Dilbilgisi ve Yazım Hatalarını Göster
linktitle: Dilbilgisi ve Yazım Hatalarını Göster
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgedeki dilbilgisi ve imla hatalarının görüntülenmesini sağlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Bu öğreticide, Aspose.Words for .NET ile dilbilgisi ve yazım hatalarının görüntülenmesini sağlamak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgedeki dilbilgisi ve yazım hatalarını görüntülemenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda gramer ve imla hatalarını görüntülemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Hata Görüntülemeyi Etkinleştirin

Şimdi belgedeki dilbilgisi ve yazım hatalarının görüntülenmesini etkinleştireceğiz. Hata görüntülemeyi etkinleştirmek için aşağıdaki kodu kullanın:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Bu kod dilbilgisi hatalarının görüntülenmesini sağlar (`ShowGrammaticalErrors`) ve yazım hataları (`ShowSpellingErrors`) belgede.

### Aspose.Words for .NET kullanarak Dilbilgisi ve Yazım Hatalarını Göster için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Aspose.Words for .NET kullanarak bir belgedeki dilbilgisi ve yazım hatalarının görüntülenmesini nasıl etkinleştireceğinizi artık öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek bu özelliği kendi belgelerinizde kolayca etkinleştirebilirsiniz.
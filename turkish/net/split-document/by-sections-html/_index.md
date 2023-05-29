---
title: Bölümlere Göre Html
linktitle: Bölümlere Göre Html
second_title: Aspose.Words for .NET API Referansı
description: Eksiksiz bir kod örneği ile Aspose.Words for .NET kullanarak bir Word belgesini Html'de bölümlere ayırmayı öğrenin.
type: docs
weight: 10
url: /tr/net/split-document/by-sections-html/
---

Bu örnekte, Aspose.Words for .NET'in HTML Bölümlerine Göre özelliğini kullanarak bir Word belgesini HTML formatında ayrı bölümlere nasıl ayıracağınızı göstereceğiz. Kaynak kodunu anlamak ve her bölüm için ayrı HTML belgeleri oluşturmak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için, belgeniz için dizini belirtin ve belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Adım 2: Belgeyi HTML biçiminde bölümlere ayırma

Şimdi belgeyi HTML biçiminde bölümlere ayırmak için kaydetme seçeneklerini ayarlayacağız. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Aspose.Words for .NET kullanan By Sections HTML için örnek kaynak kodu

Aspose.Words for .NET'in By HTML Sections özelliğinin tam kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

Bu kodla, Aspose.Words for .NET kullanarak bir Word belgesini HTML biçiminde ayrı bölümlere ayırabileceksiniz.

Artık ilk belgenin her bölümü için ayrı HTML belgeleri oluşturabilirsiniz.




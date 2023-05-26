---
title: sayfa sayfa
linktitle: sayfa sayfa
second_title: Aspose.Words for .NET API Referansı
description: .NET için Aspose.Words Sayfa Sayfa özelliğinin C# kaynak kodunu açıklayan adım adım kılavuz
type: docs
weight: 10
url: /tr/net/split-document/page-by-page/
---

Bu öğreticide, Aspose.Words for .NET'in Sayfa Sayfa özelliğini kullanarak bir Word belgesini nasıl tek tek sayfalara böleceğinizi göstereceğiz. Kaynak kodunu anlamak ve her sayfa için ayrı belgeler almak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için, belgeniz için dizini belirtin ve belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## 2. Adım: Belgeyi sayfaya göre bölün

Şimdi belgenin her sayfasını yineleyeceğiz ve belgeyi ayrı sayfalara ayıracağız. İşte nasıl:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Her sayfayı ayrı bir belge olarak kaydedin.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## 3. Adım: Belgeleri birleştirin

Her sayfa için ayrı belgeleriniz olduğunda, gerekirse bunları birleştirebilirsiniz. İşte nasıl:

```csharp
MergeDocuments();
```

### Aspose.Words for .NET kullanan Page By Page için örnek kaynak kodu

Aspose.Words for .NET'in Sayfa Sayfa özelliğinin tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	int pageCount = doc.PageCount;

	for (int page = 0; page < pageCount; page++)
	{
		// Her sayfayı ayrı bir belge olarak kaydedin.
		Document extractedPage = doc.ExtractPages(page, 1);
		extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
	}
	

	MergeDocuments();

```

Bu kodla, Aspose.Words for .NET kullanarak bir Word belgesini ayrı sayfalara bölebileceksiniz. Gerekirse ayrı belgeleri de birleştirebilirsiniz.


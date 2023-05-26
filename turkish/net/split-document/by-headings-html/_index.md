---
title: Başlıklara göre Html
linktitle: Başlıklara göre Html
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'in Başlığa Göre HTML özelliğinin C# kaynak kodunu açıklayan adım adım kılavuz
type: docs
weight: 10
url: /tr/net/split-document/by-headings-html/
---
Bu öğreticide, Aspose.Words for .NET'in HTML Başlığına Göre özelliğini kullanarak bir Word belgesini nasıl daha küçük parçalara böleceğinizi göstereceğiz. Kaynak kodunu anlamak ve Başlığa dayalı ayrı HTML belgeleri oluşturmak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için, belgeniz için dizini belirtin ve belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Adım 2: Belgeyi HTML biçiminde Başlığa göre bölme

Şimdi, belgeyi HTML biçimindeki Başlığa göre daha küçük parçalara bölmek için kaydetme seçeneklerini ayarlayacağız. İşte nasıl:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Belgeyi, bu durumda başlığa göre ayırarak daha küçük parçalara bölün.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Aspose.Words for .NET kullanan Başlığa Göre HTML için örnek kaynak kodu

Aspose.Words for .NET'in HTML Başlığına Göre özelliğinin tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	HtmlSaveOptions options = new HtmlSaveOptions
	{
		// Bir belgeyi daha küçük parçalara ayırın, bu örnekte başlığa göre bölün.
		DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
	};
	

	doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
	

```

Bu kodla, Aspose.Words for .NET kullanarak bir Word belgesini başlıklara göre daha küçük parçalara bölebileceksiniz. Daha sonra her bölüm için ayrı HTML belgeleri oluşturabilirsiniz.


---
title: Bölümlere Göre
linktitle: Bölümlere Göre
second_title: Aspose.Words for .NET API Referansı
description: Eksiksiz bir kod örneği ile Aspose.Words for .NET kullanarak bir Word belgesini nasıl ayrı bölümlere ayıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/split-document/by-sections/
---

Bu örnekte, Aspose.Words for .NET'in Bölümlere Göre özelliğini kullanarak bir Word belgesini nasıl ayrı bölümlere ayıracağınızı göstereceğiz. Kaynak kodunu anlamak ve her bölüm için ayrı belgeler almak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için, belgenizin dizinini belirtmemiz ve belgeyi bir Belge nesnesine yüklememiz gerekiyor. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Adım 2: Belgeyi bölümlere ayırın

Şimdi belgenin her bölümünü yineleyeceğiz ve belgeyi bölüm bölüm daha küçük parçalara ayıracağız. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Belgeyi bu durumda bölümlere ayırarak daha küçük parçalara ayırın.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Her bölümü ayrı bir belge olarak kaydedin.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Aspose.Words for .NET kullanan By Sections için örnek kaynak kodu

Aspose.Words for .NET'in Bölümlere Göre özelliğinin tam kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

for (int i = 0; i < doc.Sections.Count; i++)
{
	// Bir belgeyi daha küçük parçalara ayırın, bu örnekte bölüme göre bölün.
	Section section = doc.Sections[i].Clone();

	Document newDoc = new Document();
	newDoc.Sections.Clear();

	Section newSection = (Section) newDoc.ImportNode(section, true);
	newDoc.Sections.Add(newSection);

	// Her bölümü ayrı bir belge olarak kaydedin.
	newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
}
```

Bu kodla, Aspose.Words for .NET'i kullanarak bir Word belgesini ayrı bölümlere ayırabileceksiniz.

Artık belirli bölümlerle kolayca çalışabilirsiniz.


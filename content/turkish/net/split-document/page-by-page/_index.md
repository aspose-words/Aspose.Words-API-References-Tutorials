---
title: Word Belgesini Sayfaya Göre Böl
linktitle: Word Belgesini Sayfaya Göre Böl
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesini ayrı sayfalara nasıl böleceğinizi öğrenin. Bu güçlü API, belgeleri bölme işlemini basitleştirerek verimli ve kullanışlı hale getirir.
type: docs
weight: 10
url: /tr/net/split-document/page-by-page/
---

Bu eğitimde, Aspose.Words for .NET'in belge işleme özelliğini kullanarak bir Word belgesini ayrı sayfalara nasıl bölebileceğiniz konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve her sayfa için ayrı belgeler almak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için belgenizin dizinini belirtin ve belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
//Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Adım 2: Belgeyi sayfaya göre bölme

Şimdi belgenin her sayfasını yineleyeceğiz ve belgeyi ayrı sayfalara böleceğiz. İşte nasıl:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Her sayfayı ayrı bir belge olarak kaydedin.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Aspose.Words for .NET kullanan Sayfa Sayfa için örnek kaynak kodu

Aspose.Words for .NET'in Sayfa Sayfa özelliğinin tam kaynak kodu:

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


```

Bu kodla Aspose.Words for .NET'i kullanarak bir Word belgesini ayrı sayfalara bölebileceksiniz. Gerekirse ayrı belgeleri de birleştirebilirsiniz.

## Çözüm

Tebrikler! Aspose.Words for .NET'in Sayfa Sayfa özelliğini kullanarak bir Word belgesini ayrı sayfalara nasıl böleceğinizi öğrendiniz. Sağlanan kaynak kodunu takip ederek bir belgenin her sayfasını çıkarabilir ve bunları ayrı belgeler olarak kaydedebilirsiniz.

Bir belgeyi sayfaya bölmek, belirli sayfalarla çalışmanız veya içeriği ayrıntılı bir şekilde dağıtmanız gerektiğinde yararlı olabilir. Aspose.Words for .NET, belgeleri bölme sürecini basitleştirerek verimli ve kullanışlı hale getiren güçlü bir API sağlar.

Belge işleme yeteneklerinizi geliştirmek ve iş akışınızı kolaylaştırmak için Aspose.Words for .NET tarafından sunulan diğer özellikleri keşfetmekten çekinmeyin.

### SSS

#### Aspose.Words for .NET kullanarak bir belgeyi birden fazla sayfaya nasıl bölebilirim?

 Bir belgeyi birden çok sayfaya bölmek için`ExtractPages` Aspose.Words API'nin sayfa aralığını alma yöntemi. Başlangıç sayfasını ve çıkarılacak sayfa sayısını belirterek her sayfa için ayrı belgeler oluşturabilirsiniz.

#### Bir belgeyi sayfaya bölerken çıktı biçimini özelleştirebilir miyim?

Evet, Aspose.Words for .NET bir belgeyi sayfaya bölerken çeşitli çıktı formatlarını destekler. Gereksinimlerinize bağlı olarak her sayfayı DOCX, PDF, HTML ve daha birçok formatta ayrı bir belge olarak kaydedebilirsiniz.

#### Bir belgeyi belirli bir sayfa aralığına göre bölebilir miyim?

Kesinlikle! Aspose.Words for .NET, bir belgeyi belirli bir sayfa aralığına göre bölmenize olanak tanır. Başlangıç sayfasını ve çıkarılacak sayfa sayısını ayarlayarak belgeyi bölmek için sayfa aralığını tam olarak tanımlayabilirsiniz.

#### Bölünmüş belgeleri tek bir belgede birleştirmek mümkün müdür?

Evet, Aspose.Words for .NET tarafından sağlanan birleştirme işlevini kullanarak bölünmüş belgeleri tekrar tek bir belgede birleştirebilirsiniz. Ayrı belgeleri birleştirerek, gerektiğinde orijinal belgeyi yeniden oluşturabilir veya farklı yapıya sahip yeni bir belge oluşturabilirsiniz.
---
title: Word Belgesini Sayfaya Göre Böl
linktitle: Word Belgesini Sayfaya Göre Böl
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesini ayrı sayfalara nasıl ayıracağınızı öğrenin. Bu güçlü API, belgeleri bölme sürecini basitleştirerek verimli ve kullanışlı hale getirir.
type: docs
weight: 10
url: /tr/net/split-document/page-by-page/
---

Bu eğitimde, Aspose.Words for .NET'in belge işleme özelliğini kullanarak bir Word belgesini nasıl ayrı sayfalara böleceğinizi göstereceğiz. Kaynak kodunu anlamak ve her sayfa için ayrı belgeler almak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için, belgeniz için dizini belirtin ve belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## 2. Adım: Belgeyi sayfaya göre bölme

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


```

Bu kodla, Aspose.Words for .NET kullanarak bir Word belgesini ayrı sayfalara bölebileceksiniz. Gerekirse ayrı belgeleri de birleştirebilirsiniz.

## Çözüm

Tebrikler! Aspose.Words for .NET'in Sayfa Sayfa özelliğini kullanarak bir Word belgesini ayrı sayfalara nasıl ayıracağınızı öğrendiniz. Sağlanan kaynak kodunu takip ederek, bir belgenin her sayfasını ayıklayabilir ve ayrı belgeler olarak kaydedebilirsiniz.

Bir belgeyi sayfalara göre bölmek, belirli sayfalarla çalışmanız veya içeriği parçalı bir şekilde dağıtmanız gerektiğinde yararlı olabilir. Aspose.Words for .NET, belgeleri bölme sürecini basitleştirerek verimli ve kullanışlı hale getiren güçlü bir API sağlar.

Aspose.Words for .NET tarafından belge işleme becerilerinizi geliştirmek ve iş akışınızı kolaylaştırmak için sunulan diğer özellikleri keşfetmekten çekinmeyin.

### SSS

#### Aspose.Words for .NET kullanarak bir belgeyi birden çok sayfaya nasıl bölebilirim?

 Bir belgeyi birden çok sayfaya bölmek için,`ExtractPages` sayfa aralığını elde etmek için Aspose.Words API'sinin yöntemi. Başlangıç sayfasını ve ayıklanacak sayfa sayısını belirterek her sayfa için ayrı belgeler oluşturabilirsiniz.

#### Bir belgeyi sayfa sayfa bölerken çıktı formatını özelleştirebilir miyim?

Evet, Aspose.Words for .NET, bir belgeyi sayfa sayfa bölerken çeşitli çıktı biçimlerini destekler. Gereksinimlerinize bağlı olarak her sayfayı DOCX, PDF, HTML ve daha fazlası gibi biçimlerde ayrı bir belge olarak kaydedebilirsiniz.

#### Bir belgeyi belirli bir sayfa aralığına göre bölebilir miyim?

Kesinlikle! Aspose.Words for .NET, bir belgeyi belirli bir sayfa aralığına göre bölmenize izin verir. Başlangıç sayfasını ve ayıklanacak sayfa sayısını ayarlayarak, belgeyi bölmek için sayfa aralığını tam olarak tanımlayabilirsiniz.

#### Bölünmüş belgeleri tekrar tek bir belgede birleştirmek mümkün mü?

Evet, Aspose.Words for .NET tarafından sağlanan birleştirme işlevini kullanarak bölünmüş belgeleri tekrar tek bir belgede birleştirebilirsiniz. Ayrı belgeleri birleştirerek, orijinal belgeyi yeniden oluşturabilir veya gerektiğinde farklı bir yapıya sahip yeni bir belge oluşturabilirsiniz.
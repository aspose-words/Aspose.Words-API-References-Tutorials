---
title: Word Belgesini Başlıklara Göre Böl Html
linktitle: Başlıklara göre Html
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'in HTML özelliğine Başlayarak split word belgesinin C# kaynak kodunu açıklayan adım adım kılavuz
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
// Belgeyi, bu durumda başlığa göre ayırarak daha küçük parçalara ayırın.
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

## Çözüm

 Bu öğreticide, Aspose.Words for .NET'in HTML Başlığına Göre özelliğini kullanarak bir Word belgesini daha küçük parçalara nasıl ayıracağımızı öğrendik. belirterek`DocumentSplitCriteria` gibi`HeadingParagraph` içinde`HtmlSaveOptions`, orijinal belgede bulunan başlıklara dayalı olarak ayrı HTML belgeleri oluşturabildik.

Bir belgeyi başlıklara göre bölmek, özellikle birden çok bölümü olan büyük belgelerde içeriği düzenlemek ve yönetmek için yararlı olabilir. Aspose.Words for .NET, belge bölme işlemleri ve çeşitli biçimlerde çıktılar oluşturmak için güvenilir ve verimli bir çözüm sunar.

Aspose.Words for .NET tarafından belge işleme yeteneklerinizi daha da geliştirmek ve iş akışınızı kolaylaştırmak için sağlanan ek özellikleri ve seçenekleri keşfetmekten çekinmeyin.

### SSS

#### Aspose.Words for .NET kullanarak bir Word belgesini başlıklara dayalı olarak nasıl daha küçük parçalara bölebilirim?

 Bir Word belgesini başlıklara göre bölmek için Aspose.Words for .NET'in HTML Başlığına Göre özelliğini kullanabilirsiniz. Sağlanan kaynak kodunu takip edin ve`DocumentSplitCriteria` ile`HeadingParagraph` içinde`HtmlSaveOptions` nesne. Bu, belgeyi her başlıkta daha küçük parçalara böler.

#### Word belgesini hangi biçimlere bölebilirim?

Sağlanan kaynak kodu, Word belgesinin HTML biçiminde daha küçük parçalara bölünmesini gösterir. Ancak Aspose.Words for .NET, DOCX, PDF, EPUB ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler. Kodu değiştirebilir ve istenen çıktı biçimini belirtebilirsiniz.`HtmlSaveOptions` buna göre itiraz edin.

#### Belgeyi bölmek için farklı bir kriter seçebilir miyim?

 Evet, gereksinimlerinize göre belgeyi bölmek için farklı bir ölçüt seçebilirsiniz. Aspose.Words for .NET, aşağıdakiler gibi birkaç kriter seçeneği sunar:`HeadingParagraph`, `Page`, `Section` , ve dahası. Değiştirmek`DocumentSplitCriteria` mülkiyet`HtmlSaveOptions` Bölme için uygun ölçütleri seçmek için nesne.

#### Bölünmüş parçalar için çıktı HTML'sini nasıl özelleştirebilirim?

 Aspose.Words for .NET, bölünmüş parçalar için çıktı HTML'sini özelleştirmenize izin verir.`HtmlSaveOptions` nesne. CSS stilleri, resimler, yazı tipleri ve daha fazlası gibi çeşitli özellikleri kontrol edebilirsiniz. HTML çıktısını özelleştirme hakkında daha fazla ayrıntı için Aspose.Words belgelerine bakın.

#### Belgeyi birden çok ölçüte göre bölebilir miyim?

 Evet, ölçüt seçeneklerini uygun şekilde birleştirerek belgeyi birden çok ölçüte göre bölebilirsiniz. Örneğin, belgeyi hem başlığa hem de sayfaya göre bölebilirsiniz.`DocumentSplitCriteria` mülkiyet`HeadingParagraph | Page`. Bu, belgeyi her başlıkta ve her sayfada bölerek her iki kritere göre daha küçük parçalar oluşturur.
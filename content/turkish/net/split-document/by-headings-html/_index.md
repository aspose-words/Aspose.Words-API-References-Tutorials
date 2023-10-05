---
title: Word Belgesini Başlıklara Göre Böl Html
linktitle: Başlıklara Göre Html
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in HTML özelliğinin başlığına göre bölünmüş word belgesinin C# kaynak kodunu açıklayan adım adım kılavuz
type: docs
weight: 10
url: /tr/net/split-document/by-headings-html/
---
Bu eğitimde, Aspose.Words for .NET'in HTML Başlığına Göre özelliğini kullanarak bir Word belgesini nasıl daha küçük parçalara ayıracağınız konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve Başlığa dayalı ayrı HTML belgeleri oluşturmak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için belgenizin dizinini belirtin ve belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Adım 2: Belgeyi HTML formatında Başlığa göre bölme

Şimdi belgeyi HTML formatında Başlığa göre daha küçük parçalara bölmek için kaydetme seçeneklerini ayarlayacağız. İşte nasıl:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Belgeyi daha küçük parçalara bölün; bu durumda başlığa göre ayırın.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Aspose.Words for .NET kullanan Başlıklara Göre HTML için örnek kaynak kodu

Aspose.Words for .NET'in HTML Başlığına Göre özelliğinin tam kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Bir belgeyi daha küçük parçalara bölün; bu örnekte başlığa göre bölün.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Bu kodla, Aspose.Words for .NET kullanarak bir Word belgesini başlıklara göre daha küçük parçalara bölebileceksiniz. Daha sonra her parça için ayrı HTML belgeleri oluşturabilirsiniz.

## Çözüm

 Bu eğitimde Aspose.Words for .NET'in HTML Başlığına Göre özelliğini kullanarak bir Word belgesini daha küçük parçalara nasıl böleceğimizi öğrendik. Belirterek`DocumentSplitCriteria` gibi`HeadingParagraph` içinde`HtmlSaveOptions`sayesinde, orijinal belgede bulunan başlıklara dayalı olarak ayrı HTML belgeleri oluşturabildik.

Bir belgeyi başlıklara göre bölmek, özellikle birden fazla bölümü olan büyük belgelerde içeriği düzenlemek ve yönetmek için yararlı olabilir. Aspose.Words for .NET, belge bölme ve çeşitli formatlarda çıktı oluşturma işlemleri için güvenilir ve etkili bir çözüm sunar.

Belge işleme yeteneklerinizi daha da geliştirmek ve iş akışınızı kolaylaştırmak için Aspose.Words for .NET tarafından sağlanan ek özellikleri ve seçenekleri keşfetmekten çekinmeyin.

### SSS

#### Aspose.Words for .NET kullanarak bir Word belgesini başlıklara göre nasıl daha küçük parçalara bölebilirim?

 Bir Word belgesini başlıklara göre bölmek için Aspose.Words for .NET'in HTML Başlığına Göre özelliğini kullanabilirsiniz. Sağlanan kaynak kodunu takip edin ve`DocumentSplitCriteria` ile`HeadingParagraph` içinde`HtmlSaveOptions` nesne. Bu, belgeyi her başlıkta daha küçük parçalara bölecektir.

#### Word belgesini hangi formatlara bölebilirim?

Sağlanan kaynak kodu, Word belgesinin HTML biçiminde daha küçük parçalara bölünmesini gösterir. Ancak Aspose.Words for .NET, DOCX, PDF, EPUB ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler. Kodu değiştirebilir ve istediğiniz çıktı formatını belirtebilirsiniz.`HtmlSaveOptions` buna göre itiraz edin.

#### Belgeyi bölmek için farklı bir kriter seçebilir miyim?

 Evet, gereksinimlerinize göre belgeyi bölmek için farklı bir kriter seçebilirsiniz. Aspose.Words for .NET çeşitli kriter seçenekleri sunar;`HeadingParagraph`, `Page`, `Section` , ve dahası. Değiştirmek`DocumentSplitCriteria` içindeki mülk`HtmlSaveOptions` Bölme için uygun kriterleri seçmek için nesneyi seçin.

#### Bölünmüş parçalar için çıktı HTML'sini nasıl özelleştirebilirim?

 Aspose.Words for .NET, ek seçenekler belirleyerek bölünmüş parçalar için çıktı HTML'sini özelleştirmenize olanak tanır.`HtmlSaveOptions` nesne. CSS stilleri, resimler, yazı tipleri ve daha fazlası gibi çeşitli özellikleri kontrol edebilirsiniz. HTML çıktısını özelleştirmeyle ilgili daha fazla ayrıntı için Aspose.Words belgelerine bakın.

#### Belgeyi birden fazla kritere göre bölebilir miyim?

 Evet, kriter seçeneklerini uygun şekilde birleştirerek belgeyi birden fazla kritere göre bölebilirsiniz. Örneğin, belgeyi hem başlığa hem de sayfaya göre bölebilirsiniz.`DocumentSplitCriteria`mülkiyet`HeadingParagraph | Page`. Bu, belgeyi her başlığa ve her sayfaya bölerek her iki kritere göre daha küçük bölümler oluşturacaktır.
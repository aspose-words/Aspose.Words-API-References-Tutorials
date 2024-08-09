---
title: Yer İşaretli Metni Word Belgesine Kopyala
linktitle: Yer İşaretli Metni Word Belgesine Kopyala
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak yer imlerine eklenmiş metni Word belgeleri arasında zahmetsizce kopyalayın. Bu adım adım kılavuzla nasıl yapılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/copy-bookmarked-text/
---
## giriiş

Hiç belirli bölümleri bir Word belgesinden diğerine kopyalamaya ihtiyaç duyduğunuzu fark ettiniz mi? Şanslısın! Bu eğitimde, Aspose.Words for .NET'i kullanarak yer imli metni bir Word belgesinden diğerine nasıl kopyalayacağınız konusunda size yol göstereceğiz. İster dinamik bir rapor oluşturuyor olun ister belge oluşturmayı otomatikleştiriyor olun, bu kılavuz süreci sizin için kolaylaştıracaktır.

## Önkoşullar

Dalışa geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET Kütüphanesi: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio veya başka herhangi bir .NET geliştirme ortamı.
- Temel C# Bilgisi: C# programlama ve .NET çerçevesine aşinalık.

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarının aktarıldığından emin olun:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## 1. Adım: Kaynak Belgeyi Yükleyin

Öncelikle kopyalamak istediğiniz yer imlerine eklenmiş metni içeren kaynak belgeyi yüklemeniz gerekir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Burada,`dataDir` belge dizininizin yoludur ve`Bookmarks.docx` kaynak belgedir.

## Adım 2: Yer İşaretini Tanımlayın

Daha sonra kaynak belgeden kopyalamak istediğiniz yer imini tanımlayın.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Yer değiştirmek`"MyBookmark1"` yer iminizin gerçek adıyla birlikte.

## 3. Adım: Hedef Belgesini Oluşturun

Şimdi yer imlerine eklenen metnin kopyalanacağı yeni bir belge oluşturun.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 4. Adım: Yer İşaretli İçeriği İçe Aktarın

 Stillerin ve biçimlendirmenin korunduğundan emin olmak için şunu kullanın:`NodeImporter` Yer imlerine eklenen içeriği kaynak belgeden hedef belgeye aktarmak için.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Adım 5: AppendBookmarkedText Yöntemini Tanımlayın

İşte sihrin gerçekleştiği yer burası. Yer imlerine eklenen metnin kopyalanmasını işlemek için bir yöntem tanımlayın:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Adım 6: Hedef Belgesini Kaydedin

Son olarak, kopyalanan içeriği doğrulamak için hedef belgeyi kaydedin.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Çözüm

İşte bu kadar! Aspose.Words for .NET'i kullanarak yer imlerine eklenmiş metni bir Word belgesinden diğerine başarıyla kopyaladınız. Bu yöntem, belge işleme görevlerini otomatikleştirmek için güçlüdür ve iş akışınızı daha verimli ve akıcı hale getirir.

## SSS'ler

### Birden fazla yer imini aynı anda kopyalayabilir miyim?
Evet, birden fazla yer imini yineleyebilir ve her birini kopyalamak için aynı yöntemi kullanabilirsiniz.

### Yer imi bulunamazsa ne olur?
`Range.Bookmarks` mülk geri dönecek`null`, bu nedenle istisnalardan kaçınmak için bu vakayı ele aldığınızdan emin olun.

### Orijinal yer iminin formatını koruyabilir miyim?
 Kesinlikle! Kullanma`ImportFormatMode.KeepSourceFormatting` orijinal formatın korunmasını sağlar.

### Yer imlerine eklenen metnin boyutunda bir sınır var mı?
Belirli bir sınır yoktur ancak performans çok büyük belgelerde değişiklik gösterebilir.

### Farklı Word belge formatları arasında metin kopyalayabilir miyim?
Evet, Aspose.Words çeşitli Word formatlarını destekler ve yöntem bu formatlarda çalışır.
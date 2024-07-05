---
title: Adres Mektup Birleştirmede Belgeyi Ekle
linktitle: Adres Mektup Birleştirmede Belgeyi Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı, adım adım eğitimde Aspose.Words for .NET kullanarak adres-mektup birleştirme alanlarına nasıl belge ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## giriiş

Aspose.Words for .NET ile belge otomasyonu dünyasına hoş geldiniz! Adres-mektup birleştirme işlemi sırasında belgeleri ana belgedeki belirli alanlara dinamik olarak nasıl ekleyeceğinizi hiç merak ettiniz mi? Peki, doğru yerdesiniz. Bu eğitim, Aspose.Words for .NET kullanarak adres-mektup birleştirme alanlarına belge ekleme sürecinde size adım adım rehberlik edecektir. Her parçanın mükemmel bir şekilde yerine oturduğu bir bulmacanın parçalarını bir araya getirmeye benziyor. O halde hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: Yapabilirsin[en son sürümü buradan indirin](https://releases.aspose.com/words/net/) . Lisans satın almanız gerekiyorsa bunu yapabilirsiniz.[Burada](https://purchase.aspose.com/buy) . Alternatif olarak, bir[geçici lisans](https://purchase.aspose.com/temporary-license/) veya şunu deneyin[ücretsiz deneme](https://releases.aspose.com/).
2. Geliştirme Ortamı: Visual Studio veya başka herhangi bir C# IDE.
3. Temel C# Bilgisi: C# programlamaya aşinalık bu eğitimi çocuk oyuncağı haline getirecektir.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Bunlar projenizin yapı taşları gibidir.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Süreci yönetilebilir adımlara ayıralım. Her adım bir öncekinin üzerine inşa edilecek ve sizi eksiksiz bir çözüme götürecektir.

## 1. Adım: Dizininizi Kurma

Belgeleri eklemeye başlamadan önce belgeler dizininizin yolunu tanımlamanız gerekir. Belgelerinizin saklandığı yer burasıdır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Ana Belgeyi Yükleme

Daha sonra ana belgeyi yükleyeceksiniz. Bu belge, diğer belgelerin ekleneceği birleştirme alanlarını içerir.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## 3. Adım: Alan Birleştirme Geri Aramasını Ayarlama

Birleştirme işlemini gerçekleştirmek için bir geri arama işlevi ayarlamanız gerekir. Bu işlev, belgelerin belirtilen birleştirme alanlarına eklenmesinden sorumlu olacaktır.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Adım 4: Adres Mektup Birleştirmeyi Yürütme

Şimdi adres-mektup birleştirmeyi yürütmenin zamanı geldi. Sihir yapılan yer burasıdır. Birleştirme alanını ve bu alana eklenmesi gereken belgeyi belirteceksiniz.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Adım 5: Belgeyi Kaydetme

Adres-mektup birleştirme tamamlandıktan sonra değiştirilen belgeyi kaydedersiniz. Bu yeni belgede eklenen içerik tam istediğiniz yerde olacaktır.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Adım 6: Geri Arama İşleyicisini Oluşturma

Geri çağırma işleyicisi, birleştirme alanı için özel işlemler yapan bir sınıftır. Alan değerinde belirtilen belgeyi yükler ve geçerli birleştirme alanına ekler.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Adım 7: Belgeyi Ekleme

Bu yöntem, belirtilen belgeyi geçerli paragraf veya tablo hücresine ekler.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak adres-mektup birleştirme işlemi sırasında belgeleri belirli alanlara başarıyla eklediniz. Bu güçlü özellik, özellikle büyük hacimli belgelerle uğraşırken, zamandan ve emekten büyük miktarda tasarruf etmenizi sağlayabilir. Bunu, tüm ağır yükleri sizin için halledecek kişisel bir asistana sahip olmak gibi düşünün. Öyleyse devam edin ve deneyin. Mutlu kodlama!

## SSS'ler

### Farklı birleştirme alanlarına birden fazla belge ekleyebilir miyim?
Evet yapabilirsin. Uygun birleştirme alanlarını ve karşılık gelen belge yollarını belirtmeniz yeterlidir.`MailMerge.Execute` yöntem.

### Eklenen belgeyi ana belgeden farklı biçimlendirmek mümkün müdür?
 Kesinlikle! Şunu kullanabilirsiniz:`ImportFormatMode` parametresi`NodeImporter` biçimlendirmeyi kontrol etmek için.

### Birleştirme alanı adı dinamikse ne olur?
Dinamik birleştirme alanı adlarını, geri çağırma işleyicisine parametre olarak ileterek işleyebilirsiniz.

### Bu yöntemi farklı dosya formatlarıyla kullanabilir miyim?
Evet, Aspose.Words DOCX, PDF ve daha fazlasını içeren çeşitli dosya formatlarını destekler.

### Belge ekleme işlemi sırasında hataları nasıl ele alabilirim?
Oluşabilecek istisnaları yönetmek için geri arama işleyicinizde hata işlemeyi uygulayın.
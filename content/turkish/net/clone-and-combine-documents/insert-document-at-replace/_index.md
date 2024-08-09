---
title: Belgeyi Değiştirme Sırasına Ekle
linktitle: Belgeyi Değiştirme Sırasına Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Ayrıntılı, adım adım kılavuzumuzla Aspose.Words for .NET kullanarak bir Word belgesini diğerine sorunsuz bir şekilde nasıl ekleyeceğinizi öğrenin. Belge işlemeyi kolaylaştırmak isteyen geliştiriciler için mükemmeldir.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-replace/
---
## giriiş

Merhaba belge ustaları! Hiç kendinizi bir Word belgesini diğerine sorunsuz bir şekilde nasıl ekleyeceğinizi bulmaya çalışırken kodlara gömülmüş halde buldunuz mu? Korkmayın, çünkü bugün bu görevi kolaylaştırmak için Aspose.Words for .NET dünyasına dalıyoruz. Bulma ve değiştirme işlemi sırasında belgeleri belirli noktalara eklemek için bu güçlü kitaplığın nasıl kullanılacağına ilişkin ayrıntılı, adım adım bir kılavuzu inceleyeceğiz. Aspose.Words sihirbazı olmaya hazır mısınız? Hadi başlayalım!

## Önkoşullar

Koda geçmeden önce, yerine getirmeniz gereken birkaç şey var:

-  Visual Studio: Makinenizde Visual Studio'nun kurulu olduğundan emin olun. Henüz sahip değilseniz, adresinden indirebilirsiniz.[Burada](https://visualstudio.microsoft.com/).
-  Aspose.Words for .NET: Aspose.Words kütüphanesine ihtiyacınız olacak. Şu adresten alabilirsiniz:[Web sitesi](https://releases.aspose.com/words/net/).
- Temel C# Bilgisi: C# ve .NET'e ilişkin temel bir anlayış, bu öğreticiyi takip etmenize yardımcı olacaktır.

Pekala, bunları aradan çıkaralım, biraz kodla ellerimizi kirletelim!

## Ad Alanlarını İçe Aktar

Öncelikle Aspose.Words ile çalışmak için gerekli ad alanlarını içe aktarmamız gerekiyor. Bu, bir projeye başlamadan önce tüm araçlarınızı toplamaya benzer. Bunları kullanarak C# dosyanızın en üstüne yönergeleri ekleyin:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Artık önkoşullarımızı yerine getirdiğimize göre, süreci küçük adımlara ayıralım. Her adım çok önemli ve bizi hedefimize yaklaştıracak.

## 1. Adım: Belge Dizinini Ayarlama

Öncelikle belgelerimizin saklandığı dizini belirtmemiz gerekiyor. Bu, büyük performanstan önce sahneyi hazırlamak gibidir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` dizininizin yolu ile. Belgelerinizin yaşayacağı ve nefes alacağı yer burasıdır.

## Adım 2: Ana Belgeyi Yükleyin

Daha sonra içine başka bir belge eklemek istediğimiz ana belgeyi yüklüyoruz. Bunu tüm aksiyonun gerçekleşeceği ana sahnemiz olarak düşünün.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Bu kod, ana belgeyi belirtilen dizinden yükler.

## 3. Adım: Bul ve Değiştir Seçeneklerini Ayarlayın

Belgemizi eklemek istediğimiz belirli konumu bulmak için bul ve değiştir işlevini kullanırız. Bu, yeni eklememizin tam yerini bulmak için harita kullanmaya benziyor.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Burada yönü geriye doğru ayarlıyoruz ve daha sonra tanımlayacağımız özel bir geri arama işleyicisini belirliyoruz.

## Adım 4: Değiştirme İşlemini Gerçekleştirin

Şimdi, başka bir belge eklemek için özel geri çağrımızı kullanırken, ana belgemize belirli bir yer tutucu metni aramasını ve onu hiçbir şeyle değiştirmemesini söylüyoruz.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Bu kod bul ve değiştir işlemini gerçekleştirir ve ardından güncellenen belgeyi kaydeder.

## Adım 5: Özel Bir Geri Arama İşleyicisini Değiştirme Oluşturun

Özel geri arama işleyicimiz sihrin gerçekleştiği yerdir. Bu işleyici, bulma ve değiştirme işlemi sırasında belge ekleme işleminin nasıl gerçekleştirileceğini tanımlayacaktır.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Eşleşme metnini içeren paragraftan sonra bir belge ekleyin.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Eşleşme metnini içeren paragrafı kaldırın.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Burada eklenecek belgeyi yüklüyoruz ve ardından eklemeyi gerçekleştirmek için bir yardımcı yöntem çağırıyoruz.

## Adım 6: Belge Ekleme Yöntemini Tanımlayın

Yapbozumuzun son parçası, belgeyi belirtilen konuma gerçekten yerleştiren yöntemdir.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Bölümün gövdesindeki tüm blok düzeyindeki düğümler arasında döngü yapın,
		// daha sonra bir bölümün son boş paragrafı olmayan her düğümü kopyalayın ve ekleyin.
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

Bu yöntem, eklenecek belgedeki düğümlerin içe aktarılmasını ve bunların ana belgede doğru noktaya yerleştirilmesini sağlar.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET kullanarak bir belgeyi diğerine eklemeye yönelik kapsamlı bir kılavuz. Bu adımları izleyerek belge birleştirme ve düzenleme görevlerini kolayca otomatikleştirebilirsiniz. İster bir belge yönetim sistemi oluşturuyor olun, ister yalnızca belge işleme iş akışınızı kolaylaştırmaya ihtiyacınız olsun, Aspose.Words güvenilir yardımcınızdır.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, Word belgelerini programlı olarak işlemek için güçlü bir kütüphanedir. Word belgelerini kolaylıkla oluşturmanıza, değiştirmenize, dönüştürmenize ve işlemenize olanak tanır.

### Aynı anda birden fazla belge ekleyebilir miyim?
Evet, bir belge koleksiyonu üzerinde yineleme yaparak geri arama işleyicisini birden çok eklemeyi işleyecek şekilde değiştirebilirsiniz.

### Ücretsiz deneme mevcut mu?
 Kesinlikle! Ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).

### Aspose.Words için nasıl destek alabilirim?
adresini ziyaret ederek destek alabilirsiniz.[Aspose.Words forumu](https://forum.aspose.com/c/words/8).

### Eklenen belgenin formatını koruyabilir miyim?
 Evet,`NodeImporter` class, düğümleri bir belgeden diğerine aktarırken biçimlendirmenin nasıl işleneceğini belirtmenize olanak tanır.
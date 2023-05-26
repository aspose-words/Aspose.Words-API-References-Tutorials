---
title: Kullanım Hedef Stillerini Listeleme
linktitle: Kullanım Hedef Stillerini Listeleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak hedef belgenin liste stillerini korurken Word belgelerini nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/list-use-destination-styles/
---

Bu eğitim, Aspose.Words for .NET'in Liste Kullanım Hedef Stillerini kullanma sürecinde size rehberlik edecektir. Bu özellik, hedef belgenin liste stillerini kullanırken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET kurulu. Aspose web sitesinden indirebilir veya NuGet aracılığıyla kurabilirsiniz.
2. Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## 1. Adım: Belge Dizinlerini Başlatın

 Öncelikle, belge dizininize giden yolu ayarlamanız gerekir. değerini değiştir`dataDir` belgelerinizin bulunduğu yola değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Kaynak ve Hedef Belgeleri Yükleyin

 Ardından, Aspose.Words'ü kullanarak kaynak ve hedef belgeleri yüklemeniz gerekir.`Document` sınıf. içindeki dosya adlarını güncelleyin.`Document` belge adlarınıza göre yapıcı.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. Adım: Kaynak Belgeyi, Hedef Belgeden sonra Devam Edecek şekilde ayarlayın

 Kaynak belgedeki içeriğin hedef belge bittikten sonra da devam etmesini sağlamak için,`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4. Adım: Liste Biçimlendirmesini İşleyin

Liste biçimlendirmesini işlemek için, kaynak belgedeki her paragrafı yineleyecek ve bunun bir liste öğesi olup olmadığını kontrol edeceksiniz. Öyleyse, liste kimliğini hedef belgedeki mevcut listelerle karşılaştırırsınız. Aynı kimliğe sahip bir liste varsa, kaynak belgede listenin bir kopyasını oluşturacak ve kopyalanan listeyi kullanmak için paragrafın liste biçimini güncelleyeceksiniz.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.UseDestinationStyles` parametresi, ekleme işlemi sırasında hedef belgenin liste stillerinin kullanılmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 6. Adım: Nihai Belgeyi Kaydedin

Son olarak, birleştirilmiş belgeyi kullanarak Hedef Stillerini Listele özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Aspose.Words for .NET kullanan List Use Destination Styles için örnek kaynak kodu 

Aspose.Words for .NET kullanarak C# dilinde "List Use Destination Styles" özelliğinin tam kaynak kodu burada:


```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Kaynak belgeyi, hedef belgenin bitiminden hemen sonra devam edecek şekilde ayarlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Oluşturulan listeleri takip edin.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Hedef belgenin zaten bu kimliğe sahip bir liste içerip içermediğini kontrol edin. Eğer öyleyse, o zaman bu olabilir
			// iki listenin birlikte çalışmasına neden olur. Bunun yerine kaynak belgede listenin bir kopyasını oluşturun.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Bu kimlik için yeni kopyalanan bir liste zaten var, saklanan listeyi alın,
				// ve geçerli paragrafta kullanın.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Bu listenin bir kopyasını belgeye ekleyin ve daha sonra başvurmak üzere saklayın.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Bu paragrafın listesini kopyalananlar listesine ayarlayın.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Kaynak belgeyi hedef belgenin sonuna ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Liste Kullanım Hedef Stilleri özelliğini başarıyla uyguladınız. Nihai belge, hedef belgedeki liste stilleriyle birleştirilmiş içeriği içerecektir.
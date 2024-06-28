---
title: Hedef Stillerini Listele
linktitle: Hedef Stillerini Listele
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak hedef belgenin liste stillerini korurken Word belgelerini nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/list-use-destination-styles/
---

Bu eğitim, Aspose.Words for .NET'in Liste Kullanım Hedefi Stilleri özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, hedef belgenin liste stillerini kullanırken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET kuruldu. Aspose web sitesinden indirebilir veya NuGet aracılığıyla yükleyebilirsiniz.
2. Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## Adım 1: Belge Dizinlerini Başlatın

 Öncelikle belge dizininizin yolunu ayarlamanız gerekir. Değerini değiştirin`dataDir` belgelerinizin bulunduğu yola göre değişkendir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak ve Hedef Belgelerini Yükleyin

Daha sonra Aspose.Words'ü kullanarak kaynak ve hedef belgeleri yüklemeniz gerekir.`Document` sınıf. Dosya adlarını güncelleyin`Document` belge adlarınıza göre yapıcı.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Adım 3: Kaynak Belgeyi Hedef Belgeden Sonra Devam Edecek Şekilde Ayarlayın

 Kaynak belgedeki içeriğin hedef belgenin bitiminden sonra da devam etmesini sağlamak için`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Adım 4: Liste Biçimlendirmesini İşleyin

Liste biçimlendirmesini yönetmek için kaynak belgedeki her paragrafı yineleyecek ve bunun bir liste öğesi olup olmadığını kontrol edeceksiniz. Eğer öyleyse, liste kimliğini hedef belgedeki mevcut listelerle karşılaştıracaksınız. Aynı kimliğe sahip bir liste varsa, kaynak belgede listenin bir kopyasını oluşturacak ve kopyalanan listeyi kullanmak için paragrafın liste biçimini güncelleyeceksiniz.

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

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.UseDestinationStyles` parametresi, ekleme işlemi sırasında hedef belgenin liste stillerinin kullanılmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Adım 6: Son Belgeyi Kaydedin

Son olarak, birleştirilmiş belgeyi, Hedef Stillerini Kullan Listele özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Aspose.Words for .NET kullanan Liste Kullanım Hedef Stilleri için örnek kaynak kodu 

Aspose.Words for .NET kullanan C#'taki "Hedef Stillerini Kullan" özelliğinin tam kaynak kodu:


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
				// Bu kimlik için yeni kopyalanmış bir liste zaten mevcut, saklanan listeyi alın,
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
				// Bu paragrafın listesini kopyalanan listeye ayarlayın.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Kaynak belgeyi hedef belgenin sonuna ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Hedef Stilleri Kullan özelliğini başarıyla uyguladınız. Nihai belge, hedef belgedeki liste stilleriyle birleştirilmiş içeriği içerecektir.
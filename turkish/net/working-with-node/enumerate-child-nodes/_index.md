---
title: Alt Düğümleri Numaralandır
linktitle: Alt Düğümleri Numaralandır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir paragrafta alt düğümleri nasıl numaralandıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-node/enumerate-child-nodes/
---

Aspose.Words for .NET kullanarak alt düğümlerin nasıl numaralandırılacağını gösteren aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce, Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Bu, Aspose.Words kitaplığının içe aktarılmasını ve gerekli ad alanlarının kaynak dosyanıza eklenmesini içerir.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## 2. Adım: Yeni bir belge oluşturun
 Bu adımda, kullanarak yeni bir belge oluşturacağız.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Paragrafa ve alt düğümlerine erişin
 Bir paragrafın alt düğümlerini numaralandırmak için önce paragrafın kendisine erişmemiz gerekir. Kullan`GetChild` ile yöntem`Paragraph` belgenin ilk paragrafını almak için düğüm türü.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

Ardından, paragrafın alt düğümlerinin koleksiyonunu kullanarak alırız.`ChildNodes` mülk.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## 4. Adım: Alt düğümlere göz atın
 Artık alt düğümler koleksiyonuna sahip olduğumuza göre, bir kullanarak bunlar arasında döngü yapabiliriz.`foreach` döngü. Her alt düğümün türünü kontrol ediyoruz ve türe göre belirli işlemler gerçekleştiriyoruz.

```csharp
foreach (Node child in children)
{
     // Bir paragraf, diziler, şekiller ve diğerleri gibi farklı türlerdeki çocukları içerebilir.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

 Bu örnekte, alt düğümün türünde olup olmadığını kontrol ediyoruz.`Run` (örneğin bir metin parçası). Eğer öyleyse, düğümü şuna dönüştürürüz:`Run` kullanarak metni görüntüleyin ve`run.Text`.

## Aspose.Words for .NET ile alt düğümleri numaralandırmak için örnek kaynak kodu


```csharp
	Document doc = new Document();
	Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

	NodeCollection children = paragraph.ChildNodes;
	foreach (Node child in children)
	{
		// Bir paragraf, diziler, şekiller ve diğerleri gibi çeşitli türlerdeki çocukları içerebilir.
		if (child.NodeType == NodeType.Run)
		{
			Run run = (Run) child;
			Console.WriteLine(run.Text);
		}
	}
            
```

Bu, bir paragrafın alt düğümlerini Aspose.Words for .NET ile numaralandırmak için eksiksiz bir kod örneğidir. Referansları içe aktardığınızdan emin olun


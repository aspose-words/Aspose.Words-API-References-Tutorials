---
title: Ana Düğümü Al
linktitle: Ana Düğümü Al
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belirli bir öğenin ana düğümünü nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-node/get-parent-node/
---

Aspose.Words for .NET kullanarak ana düğümün nasıl alınacağını gösteren aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce, Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Bu, Aspose.Words kitaplığının içe aktarılmasını ve gerekli ad alanlarının kaynak dosyanıza eklenmesini içerir.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
```

## 2. Adım: Yeni bir belge oluşturun
 Bu adımda, kullanarak yeni bir belge oluşturacağız.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Üst düğüme erişin
Belirli bir düğümün ana düğümünü almak için önce o düğüme erişmemiz gerekir. Bu örnekte, genellikle bir bölüm olan belgenin ilk alt düğümüne erişiyoruz.

```csharp
Node section = doc.FirstChild;
```

## 4. Adım: Üst düğümü kontrol edin
Artık belirli bir düğüme sahip olduğumuza göre, üst düğümün belgenin kendisiyle eşleşip eşleşmediğini kontrol edebiliriz. Bu örnekte, eşitlik operatörünü () kullanarak üst düğümü belgeyle karşılaştırıyoruz.`==`) ve sonucu görüntüleyin.

```csharp
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

### Aspose.Words for .NET ile üst düğümü almak için örnek kaynak kodu


```csharp
	Document doc = new Document();

	// Bölüm, belgenin ilk alt düğümüdür.
	Node section = doc.FirstChild;

	// Bölümün ana düğümü belgedir.
	Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
            
```

Bu, Aspose.Words for .NET ile belirli bir düğümün ana düğümünü almak için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun.

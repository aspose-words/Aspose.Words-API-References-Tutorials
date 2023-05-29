---
title: Sahip Belgesi
linktitle: Sahip Belgesi
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te sahip belgesini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-node/owner-document/
---

Aspose.Words for .NET ile tescilli belge işlevselliğinin nasıl kullanılacağını gösteren aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce, Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Bu, Aspose.Words kitaplığının içe aktarılmasını ve gerekli ad alanlarının kaynak dosyanıza eklenmesini içerir.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## 2. Adım: Yeni bir belge oluşturun
 Bu adımda, kullanarak yeni bir belge oluşturacağız.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Sahip belgesiyle bir düğüm oluşturun
 Herhangi bir türde yeni bir düğüm oluşturduğunuzda, belgeyi oluşturucuya iletmeniz gerekir. Bu örnekte, belgeyi kullanarak yeni bir paragraf düğümü oluşturuyoruz.`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## 4. Adım: Üst düğümü ve sahip belgesini kontrol edin
 Artık paragraf düğümünü oluşturduğumuza göre, onun bir üst düğümü olup olmadığını ve sahibi olan belgenin aynı olup olmadığını kontrol edebiliriz.`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Adım 5: Düğüm özelliklerini belge verileriyle değiştirin
Bir düğüm ile bir belge arasındaki ilişki, stiller veya listeler gibi belgeye özgü verilere atıfta bulunan özelliklere erişim ve bu özelliklerin değiştirilmesine izin verir. Bu örnekte paragraf stili adını "Heading 1" olarak ayarlıyoruz.

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## 6. Adım: Paragrafı belgeye ekleyin
Artık paragraf düğümünü belgenin ana bölümüne ekleyebiliriz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 7. Adım: Ekledikten sonra üst düğümü doğrulayın
Belgeye paragrafı ekledikten sonra, artık bir üst düğüme sahip olup olmadığını tekrar kontrol ediyoruz.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Aspose.Words for .NET ile sahip belgesi için örnek kaynak kodu

```csharp
Document doc = new Document();

// Herhangi bir türde yeni bir düğüm oluşturmak, yapıcıya iletilen bir belge gerektirir.
Paragraph para = new Paragraph(doc);

// Yeni paragraf düğümünün henüz bir üst öğesi yok.
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

// Ancak paragraf düğümü belgesini bilir.
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

// Bir düğümün her zaman bir belgeye ait olması, erişmemize ve değiştirmemize izin verir.
// stiller veya listeler gibi belge genelindeki verilere başvuran özellikler.
para.ParagraphFormat.StyleName = "Heading 1";

// Şimdi paragrafı ilk bölümün ana metnine ekleyin.
doc.FirstSection.Body.AppendChild(para);

//Paragraf düğümü artık Gövde düğümünün alt öğesidir.
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```




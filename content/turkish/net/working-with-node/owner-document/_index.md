---
title: Sahip Belgesi
linktitle: Sahip Belgesi
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te sahip belgesini nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-node/owner-document/
---

Aşağıda, Aspose.Words for .NET ile özel belge işlevselliğinin nasıl kullanılacağını gösteren, C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Buna Aspose.Words kütüphanesinin içe aktarılması ve gerekli ad alanlarının kaynak dosyanıza eklenmesi de dahildir.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## 2. Adım: Yeni bir belge oluşturun
 Bu adımda yeni bir belge oluşturacağız.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Sahip belgesiyle bir düğüm oluşturun
 Herhangi bir türde yeni bir düğüm oluşturduğunuzda belgeyi yapıcıya aktarmanız gerekir. Bu örnekte belgeyi kullanarak yeni bir paragraf düğümü oluşturuyoruz.`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## 4. Adım: Üst düğümü ve sahip belgesini kontrol edin
Artık paragraf düğümünü oluşturduğumuza göre, onun bir üst düğümü olup olmadığını ve sahip olduğu belgenin paragraf düğümüyle aynı olup olmadığını kontrol edebiliriz.`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Adım 5: Düğüm özelliklerini belge verileriyle değiştirin
Bir düğüm ile belge arasındaki ilişki, stiller veya listeler gibi belgeye özgü verilere atıfta bulunan özelliklere erişime ve bunların değiştirilmesine olanak tanır. Bu örnekte paragraf stili adını "Başlık 1" olarak ayarlıyoruz.

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Adım 6: Paragrafı belgeye ekleyin
Artık paragraf düğümünü belgenin ana bölümüne ekleyebiliriz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 7. Adım: Ekledikten sonra üst düğümü doğrulayın
Paragrafı belgeye ekledikten sonra artık bir üst düğüm olup olmadığını tekrar kontrol ederiz.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Aspose.Words for .NET ile sahip belgesi için örnek kaynak kodu

```csharp
Document doc = new Document();

// Herhangi bir türde yeni bir düğüm oluşturmak, yapıcıya bir belgenin aktarılmasını gerektirir.
Paragraph para = new Paragraph(doc);

// Yeni paragraf düğümünün henüz bir üst öğesi yok.
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

// Ancak paragraf düğümü belgesini biliyor.
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

// Bir düğümün her zaman bir belgeye ait olması, ona erişmemizi ve onu değiştirmemizi sağlar.
// stiller veya listeler gibi belge genelindeki verilere başvuran özellikler.
para.ParagraphFormat.StyleName = "Heading 1";

// Şimdi paragrafı ilk bölümün ana metnine ekleyin.
doc.FirstSection.Body.AppendChild(para);

// Paragraf düğümü artık Gövde düğümünün bir çocuğudur.
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```

### SSS'ler

#### S: Node.js'de özel belge nedir?

C: Node.js'deki sahip belgesi, belirli bir düğümün ait olduğu XML belgesidir. Düğümü içeren XML belgesinin örneğini temsil eder.

#### S: Bir düğümün sahiplik belgesi nasıl alınır?

 C: Node.js'de bir düğümün sahiplik belgesini almak için`ownerDocument` düğümün özelliği. Bu özellik, düğümün sahibi olan XML belgesini döndürür.

#### S: Özel belge ne için kullanılır?

C: Sahip belgesi, bir XML belgesindeki bir düğümün genel içeriğini temsil etmek için kullanılır. Belgedeki diğer düğümlere erişim sağlar ve bunlar üzerinde işlem yapılmasına olanak sağlar.

#### S: Bir düğümün sahip belgesini değiştirebilir miyiz?

C: Çoğu durumda, bir düğümün belge sahibi, düğüm oluşturulduğunda belirlenir ve doğrudan değiştirilemez. Sahip belgesi salt okunur bir özelliktir.

#### S: Bir sahip belgesinin düğümlerine nasıl erişilir?

C: Özel bir belgedeki düğümlere erişmek için Node.js ortamınızda kullanılan XML API'sinin sağladığı yöntemleri ve özellikleri kullanabilirsiniz. Örneğin, gibi yöntemleri kullanabilirsiniz.`getElementsByTagName` veya`querySelector` Belgedeki belirli düğümleri seçmek için.
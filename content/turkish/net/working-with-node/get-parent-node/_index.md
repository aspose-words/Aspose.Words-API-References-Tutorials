---
title: Ana Düğümü Alın
linktitle: Ana Düğümü Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belirli bir öğenin üst düğümünü nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-node/get-parent-node/
---

Aşağıda, Aspose.Words for .NET kullanılarak ana düğümün nasıl elde edileceğini gösteren, C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Buna Aspose.Words kütüphanesinin içe aktarılması ve gerekli ad alanlarının kaynak dosyanıza eklenmesi de dahildir.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
```

## 2. Adım: Yeni bir belge oluşturun
 Bu adımda yeni bir belge oluşturacağız.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Üst düğüme erişin
Belirli bir düğümün ana düğümünü almak için önce o düğüme erişmemiz gerekir. Bu örnekte, belgenin genellikle bir bölüm olan ilk alt düğümüne erişiyoruz.

```csharp
Node section = doc.FirstChild;
```

## 4. Adım: Üst düğümü kontrol edin
Artık belirli bir düğüme sahip olduğumuza göre, onun üst düğümünün belgenin kendisiyle eşleşip eşleşmediğini kontrol edebiliriz. Bu örnekte, eşitlik operatörünü () kullanarak üst düğümü belgeyle karşılaştırıyoruz.`==`) ve sonucu görüntüleyin.

```csharp
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

### Aspose.Words for .NET ile ana düğümü almak için örnek kaynak kodu


```csharp
Document doc = new Document();

// Bölüm, belgenin ilk alt düğümüdür.
Node section = doc.FirstChild;

// Bölümün ana düğümü belgedir.
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

Bu, Aspose.Words for .NET ile belirli bir düğümün üst düğümünü almaya yönelik eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları izlediğinizden emin olun.

### SSS'ler

#### S: Node.js'deki üst düğüm nedir?

C: Node.js'deki ana düğüm, bir XML belgesinin hiyerarşisindeki bir sonraki daha yüksek düğümü ifade eder. Bu, belirtilen düğümü içeren düğümdür.

#### S: Belirli bir düğümün üst düğümü nasıl alınır?

C: Belirli bir düğümün üst düğümünü almak için`parentNode` düğümün özelliği. Bu özellik geçerli düğümün üst düğümünü döndürür.

#### S: Bir düğümün üst düğümü olup olmadığı nasıl kontrol edilir?

 C: Bir düğümün bir üst düğümü olup olmadığını kontrol etmek için, basitçe`parentNode` Düğümün özelliği ayarlandı. Ayarlanırsa bu, düğümün bir üst düğümüne sahip olduğu anlamına gelir.

#### S: Bir düğümün üst düğümünü değiştirebilir miyiz?

 C: Çoğu durumda, bir düğümün üst düğümü XML belgesinin yapısına göre belirlenir ve doğrudan değiştirilemez. Ancak belirli yöntemleri kullanarak bir düğümü başka bir düğüme taşıyabilirsiniz:`appendChild` veya`insertBefore`.

#### S: Ana düğümlerin hiyerarşisine nasıl göz atılır?

 C: Ana düğümlerin hiyerarşisinde geçiş yapmak için, belirli bir düğümden başlayarak yineleme yapabilirsiniz.`parentNode` belgenin kök düğümüne ulaşana kadar özellik.
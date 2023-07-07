---
title: Word Belgesinde İleri Bağlantıyı Kır
linktitle: Word Belgesinde İleri Bağlantıyı Kır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki ileri bağlantıları nasıl kıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET, Microsoft Word belgeleriyle programlı olarak çalışmak için çeşitli özellikler sunan güçlü bir kitaplıktır. Yararlı özelliklerinden biri, bir kelime belgesindeki bağlantıları ileriye doğru kırabilme yeteneğidir. Bu öğreticide, Aspose.Words for .NET kullanarak word belgesindeki ileri bağlantının nasıl kırılacağını gösteren C# kaynak kodunu keşfedeceğiz.

## 1. Adım: C# Kaynak Kodu Önizlemesi

Sağlanan C# kaynak kodu, Aspose.Words for .NET'in "Break A Link" özelliğine odaklanır. Bir belgenin içindeki Metin Kutusu şeklindeki bir bağlantının nasıl kesileceğini gösterir. Kod, bağlantıları kesmek için farklı senaryolar sunar ve istenen sonuçların nasıl elde edileceğine dair net talimatlar sağlar.

## 2. Adım: Belgeyi ayarlama ve bir Metin Kutusu şekli oluşturma

Başlamak için, belgeyi kurmamız ve bir TextBox şekli oluşturmamız gerekiyor. Aşağıdaki kod, yeni bir örneğini başlatır.`Document` class ve bir metin kutusu şekli oluşturur:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 3. Adım: TextBox'ta ileri bağlantıyı kes

 TextBox'ta bir yönlendirme bağlantısını kesmek için şunu kullanabiliriz:`BreakForwardLink()` yöntem. Bu yöntem, dizideki bir sonraki şekle olan bağlantıyı keser. Aşağıdaki kod, bir ileri bağlantının nasıl kesileceğini gösterir:

```csharp
textBox.BreakForwardLink();
```

## 4. Adım: Boş bir değer ayarlayarak ileri bağlantıyı kesin

 Alternatif olarak, TextBox'ları ayarlayarak bir ileri bağlantıyı kesebiliriz.`Next` mülkiyet`null`. Bu, sonraki şekle olan bağlantıyı etkili bir şekilde kaldırır. Aşağıdaki kod bu yaklaşımı göstermektedir:

```csharp
textBox. Next = null;
```

## 5. Adım: TextBox'a yönlendiren bir bağlantıyı kesin

 Bazı durumlarda, TextBox şekline götüren bir bağlantıyı kesmemiz gerekir. Bunu çağırarak elde edebiliriz.`BreakForwardLink()` yöntemi`Previous` TextBox bağlantısını kesen form. İşte böyle bir bağlantının nasıl kırılacağına dair bir örnek:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Aspose.Words for .NET ile bir bağlantıyı kesmek için örnek kaynak kodu

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// İleri bağlantıyı kes.
textBox.BreakForwardLink();

//Boş bir değer ayarlayarak ileri bağlantıyı kesin.
textBox. Next = null;

// Bu metin kutusuna yönlendiren bir bağlantıyı koparın.
textBox.Previous?.BreakForwardLink();
```

## Çözüm

Tebrikler! Artık, Aspose.Words .NET kitaplığını kullanarak bir Word belgesindeki yeniden yönlendirme bağlantılarını nasıl kıracağınızı öğrendiniz. Bu kılavuzdaki adımları izleyerek belgeyi ayarlayabildiniz, bir TextBox şekli oluşturabildiniz ve farklı yöntemler kullanarak yönlendirme bağlantılarını kırabildiniz.

### Word belgesinde ileriye dönük bağlantı için SSS

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki yeniden yönlendirme bağlantılarını kesmek için kullanılan kitaplık nedir?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki yeniden yönlendirme bağlantılarını kırmak için kullanılan kitaplık Aspose.Words for .NET'tir.

#### S: Bir TextBox'ta yönlendirme bağlantısı nasıl bozulur?

 C: Bir Metin Kutusundaki bir iletme bağlantısını kesmek için şunu kullanabilirsiniz:`BreakForwardLink()` yöntem. Bu yöntem, dizideki bir sonraki şekle olan bağlantıyı keser.

#### S: Boş bir değer ayarlayarak bir yönlendirme bağlantısını nasıl kesebilirim?

 A: Alternatif olarak, ayarlayarak bir yönlendirme bağlantısını kesebilirsiniz.`Next`TextBox özelliği`null`. Bu, sonraki şekle olan bağlantıyı etkili bir şekilde kaldırır.

#### S: TextBox'a giden bir bağlantı nasıl kesilir?

 C: Bazı durumlarda, TextBox'a giden bir bağlantıyı kesmeniz gerekir. Bunu arayarak başarabilirsiniz.`BreakForwardLink()` yöntemi`Previous` TextBox bağlantısını kesen form.

#### S: Metin Kutuları dışındaki öğelerde yönlendirme bağlantılarını kesebilir miyiz?

C: Evet, Aspose.Words for .NET ile paragraflar, tablolar, resimler vb. farklı öğelerdeki yönlendirme bağlantılarını kırmak mümkündür. İşlem, bağlantıyı kesmek istediğiniz belirli öğeye bağlı olarak değişebilir.
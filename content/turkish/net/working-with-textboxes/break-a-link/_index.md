---
title: Word Belgesinde İleri Bağlantıyı Kes
linktitle: Word Belgesinde İleri Bağlantıyı Kes
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki ileri bağlantıları nasıl keseceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET, Microsoft Word belgeleriyle programlı olarak Kelime İşleme için çeşitli özellikler sunan güçlü bir kütüphanedir. Yararlı özelliklerinden biri, bir word belgesindeki ileri bağlantıları kesme yeteneğidir. Bu eğitimde, Aspose.Words for .NET kullanarak word belgesinde ileri bağlantının nasıl kesileceğini gösteren C# kaynak kodunu inceleyeceğiz.

## Adım 1: C# Kaynak Kodu Önizlemesi

Sunulan C# kaynak kodu Aspose.Words for .NET'in "Bağlantıyı Kes" özelliğine odaklanıyor. Bir belgenin içindeki TextBox şeklindeki bir bağlantının nasıl kesileceğini gösterir. Kod, bağlantıların kopmasına yönelik farklı senaryolar sunar ve istenen sonuçların nasıl elde edileceğine dair net talimatlar sağlar.

## Adım 2: Belgeyi ayarlama ve TextBox şekli oluşturma

 Başlamak için belgeyi ayarlamamız ve bir TextBox şekli oluşturmamız gerekiyor. Aşağıdaki kod, yeni bir örneğini başlatır.`Document` sınıfını açar ve bir metin kutusu şekli oluşturur:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 3. Adım: TextBox'ta ileri bağlantıyı kesin

 TextBox'ta ileri bağlantıyı kesmek için şunu kullanabiliriz:`BreakForwardLink()` yöntem. Bu yöntem, sıradaki bir sonraki şekle olan bağlantıyı keser. Aşağıdaki kod, ileri bağlantının nasıl kesileceğini gösterir:

```csharp
textBox.BreakForwardLink();
```

## Adım 4: Boş bir değer ayarlayarak ileri bağlantıyı kesin

 Alternatif olarak, TextBox'un ayarını yaparak ileri bağlantıyı kesebiliriz.`Next`mülkiyet`null`. Bu, bir sonraki şekle olan bağlantıyı etkili bir şekilde ortadan kaldırır. Aşağıdaki kod bu yaklaşımı göstermektedir:

```csharp
textBox. Next = null;
```

## Adım 5: TextBox'a giden bağlantıyı kesin

 Bazı durumlarda TextBox şekline giden bağlantıyı kesmemiz gerekir. Bunu arayarak başarabiliriz.`BreakForwardLink()` konusundaki yöntem`Previous` TextBox bağlantısını kesen form. Böyle bir bağlantının nasıl kırılacağına dair bir örnek:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Aspose.Words for .NET ile bağlantıyı kesmek için örnek kaynak kodu

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// İleri bağlantıyı kes.
textBox.BreakForwardLink();

// Boş bir değer ayarlayarak ileri bağlantıyı kesin.
textBox. Next = null;

// Bu metin kutusuna yönlendiren bağlantıyı kesin.
textBox.Previous?.BreakForwardLink();
```

## Çözüm

Tebrikler! Artık .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesindeki yönlendirme bağlantılarını nasıl keseceğinizi öğrendiniz. Bu kılavuzdaki adımları izleyerek belgeyi ayarlayabildiniz, bir TextBox şekli oluşturabildiniz ve farklı yöntemler kullanarak yönlendirme bağlantılarını kesebildiniz.

### Word belgesindeki ileri bağlantı bağlantısı için SSS

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki yönlendirme bağlantılarını kırmak için kullanılan kitaplık nedir?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki yönlendirme bağlantılarını kırmak için kullanılan kütüphane Aspose.Words for .NET'tir.

#### S: TextBox'taki yönlendirme bağlantısı nasıl kesilir?

 C: Bir TextBox'taki ileri bağlantıyı kesmek için şunu kullanabilirsiniz:`BreakForwardLink()` yöntem. Bu yöntem, sıradaki bir sonraki şekle olan bağlantıyı keser.

#### S: Boş bir değer ayarlayarak yönlendirme bağlantısını nasıl kesebilirim?

C: Alternatif olarak, yönlendirme bağlantısını ayarlayarak da kesebilirsiniz.`Next` TextBox'ın özelliği`null`. Bu, bir sonraki şekle olan bağlantıyı etkili bir şekilde ortadan kaldırır.

#### S: TextBox'a giden bir bağlantı nasıl koparılır?

 C: Bazı durumlarda TextBox'a giden bağlantıyı kesmeniz gerekir. Bunu arayarak başarabilirsiniz.`BreakForwardLink()` konusundaki yöntem`Previous` TextBox bağlantısını kesen form.

#### S: TextBox'lar dışındaki öğelerdeki yönlendirme bağlantılarını kesebilir miyiz?

C: Evet, Aspose.Words for .NET ile paragraflar, tablolar, resimler vb. farklı öğelerdeki yönlendirme bağlantılarını kırmak mümkündür. Bu süreç, bağlantıyı kesmek istediğiniz belirli öğeye bağlı olarak değişebilir.
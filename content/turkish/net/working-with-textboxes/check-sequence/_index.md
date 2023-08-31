---
title: Kontrol Sırası
linktitle: Kontrol Sırası
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki Metin Kutularının sırasını nasıl kontrol edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-textboxes/check-sequence/
---
Bu adım adım kılavuz, .NET için Aspose.Words kitaplığı kullanılarak bir Word belgesindeki Metin Kutularının sırasının nasıl kontrol edileceğini açıklar. Belgeyi nasıl yapılandıracağınızı, bir Metin Kutusu şekli oluşturmayı, Metin Kutularına erişmeyi ve sıradaki konumlarını kontrol etmeyi öğreneceksiniz.

## 1. Adım: Belgeyi ayarlama ve bir Metin Kutusu şekli oluşturma

 Başlamak için, belgeyi kurmamız ve bir TextBox şekli oluşturmamız gerekiyor. Aşağıdaki kod, yeni bir örneğini başlatır.`Document` class ve bir metin kutusu şekli oluşturur:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## 2. Adım: Metin Kutusu sırasını kontrol etme

 Şimdi kullanarak TextBox sırasını kontrol edeceğiz.`if` koşullar. Sağlanan kaynak kodu, Metin Kutusunun önceki ve sonraki şekillere göre konumunu kontrol etmek için üç ayrı koşul içerir.

## Adım 3: Sekans başlığını kontrol etme:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Metin Kutusunun bir sonraki şekli varsa (`Next`) ancak önceki şekil yok (`Previous`), bu, dizinin başı olduğu anlamına gelir. "Sekansın başı" mesajı görüntülenecektir.

## Adım 4: Dizinin ortasını kontrol etme:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

TextBox'ta hem Sonraki şekil (`Next`) ve Önceki şekil (`Previous`), bu, dizinin ortasında olduğunu gösterir. "Sekansın ortası" mesajı görüntülenecektir.

## Adım 5: Dizinin sonunun doğrulanması:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Metin Kutusunun sonraki şekli yoksa (`Next`) ancak önceki bir şekle sahiptir (`Previous`), bu, dizinin sonu olduğu anlamına gelir. "Sıranın sonu" mesajı görüntülenecektir.

### Aspose.Words for .NET ile sıralamayı doğrulamak için örnek kaynak kodu

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

## Çözüm

Tebrikler! Artık Aspose.Words .NET kitaplığını kullanarak bir Word belgesindeki Metin Kutularının sırasını nasıl kontrol edeceğinizi biliyorsunuz. Bu kılavuzdaki adımları izleyerek belgeyi ayarlayabilir, bir Metin Kutusu şekli oluşturabilir ve dizinin başında mı, ortasında mı yoksa sonunda mı olduğunu kontrol edebilirsiniz.

### Kontrol sırası için SSS

#### S: Aspose.Words for .NET kullanarak TextBox'ların sırasını kontrol etmek için kullanılan kütüphane nedir?

C: Aspose.Words for .NET kullanarak TextBox'ların sırasını kontrol etmek için kullanılan kütüphane Aspose.Words for .NET'tir.

#### S: Bir TextBox'un dizinin başı olup olmadığı nasıl belirlenir?

C: Bir TextBox'un dizinin başı olup olmadığını belirlemek için, sonraki bir forma sahip olup olmadığını kontrol edebilirsiniz (`Next`) ancak önceki bir form değil (`Previous`). Eğer öyleyse, bu serinin başı olduğu anlamına gelir.

#### S: Bir TextBox'un dizinin ortasında olup olmadığı nasıl anlaşılır?

A: Bir Metin Kutusunun dizinin ortasında olup olmadığını belirlemek için, onun hem bir sonraki şekle () sahip olup olmadığını kontrol etmeniz gerekir.`Next`) ve bir önceki şekil (`Previous`). Eğer öyleyse, bu dizinin ortasında olduğunu gösterir.

#### S: Bir TextBox'un dizinin sonu olup olmadığı nasıl kontrol edilir?

C: Bir TextBox'un dizinin sonu olup olmadığını kontrol etmek için, sonraki formunun olup olmadığını kontrol edebilirsiniz (`Next`) ancak önceki bir forma sahiptir (`Previous`). Eğer öyleyse, bu dizinin sonu demektir.

#### S: Metin Kutuları dışındaki öğelerin sırasını kontrol edebilir miyiz?

C: Evet, .NET için Aspose.Words kütüphanesini kullanarak paragraflar, tablolar, resimler vb. gibi diğer öğelerin sırasını kontrol etmek mümkündür. İşlem, kontrol etmek istediğiniz belirli öğeye göre değişir.

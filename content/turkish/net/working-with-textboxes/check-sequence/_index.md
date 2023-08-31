---
title: Sırayı Kontrol Et
linktitle: Sırayı Kontrol Et
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki TextBox'ların sırasını nasıl kontrol edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-textboxes/check-sequence/
---
Bu adım adım kılavuz, .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesindeki TextBox'ların sırasının nasıl kontrol edileceğini açıklar. Belgeyi nasıl yapılandıracağınızı, bir TextBox şekli oluşturmayı, TextBox'lara nasıl erişeceğinizi ve bunların sıradaki konumlarını nasıl kontrol edeceğinizi öğreneceksiniz.

## Adım 1: Belgeyi ayarlama ve TextBox şekli oluşturma

 Başlamak için belgeyi ayarlamamız ve bir TextBox şekli oluşturmamız gerekiyor. Aşağıdaki kod, yeni bir örneğini başlatır.`Document` sınıfını açar ve bir metin kutusu şekli oluşturur:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Adım 2: TextBox sırasını kontrol etme

 Şimdi TextBox'un sırasını kullanarak kontrol edeceğiz.`if` koşullar. Sağlanan kaynak kodu, TextBox'un önceki ve sonraki şekillere göre konumunu kontrol etmek için üç ayrı koşul içerir.

## Adım 3: Sıra başlığının kontrol edilmesi:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

TextBox'ın bir sonraki şekli varsa (`Next`) ancak önceki şekil yok (`Previous`), bu da dizinin başı olduğu anlamına gelir. "Sıranın başı" mesajı görüntülenecektir.

## Adım 4: Sıranın ortasının kontrol edilmesi:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

TextBox'ta hem Sonraki şekil (`Next`) ve Önceki şekil (`Previous`), bu dizinin ortasında olduğunu gösterir. "Sıranın ortası" mesajı görüntülenecektir.

## Adım 5: Sıranın sonunun doğrulanması:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

TextBox'un sonraki şekli yoksa (`Next`) ancak önceki bir şekle sahiptir (`Previous`), bu, dizinin sonu olduğu anlamına gelir. "Sıranın sonu" mesajı görüntülenecektir.

### Aspose.Words for .NET ile sırayı doğrulamak için örnek kaynak kodu

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

Tebrikler! Artık .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesindeki TextBox'ların sırasını nasıl kontrol edeceğinizi biliyorsunuz. Bu kılavuzdaki adımları izleyerek belgeyi ayarlayabildiniz, bir TextBox şekli oluşturabildiniz ve bunun sıranın başında mı, ortasında mı yoksa sonunda mı olduğunu kontrol edebildiniz.

### Sırayı kontrol etmeye yönelik SSS'ler

#### S: Aspose.Words for .NET kullanarak TextBox'ların sırasını kontrol etmek için kullanılan kütüphane nedir?

C: Aspose.Words for .NET kullanarak TextBox'ların sırasını kontrol etmek için kullanılan kütüphane Aspose.Words for .NET'tir.

#### S: Bir TextBox'un dizinin başı olup olmadığı nasıl belirlenir?

C: Bir TextBox'un dizinin başı olup olmadığını belirlemek için bir sonraki formun olup olmadığını kontrol edebilirsiniz (`Next`) ancak önceki bir form değil (`Previous`). Eğer öyleyse, bu onun serinin lideri olduğu anlamına gelir.

#### S: Bir TextBox'ın sıranın ortasında olup olmadığını nasıl anlarım?

C: Bir TextBox'un sıranın ortasında olup olmadığını belirlemek için, hem sonraki şekle sahip olup olmadığını kontrol etmeniz gerekir (`Next`) ve önceki bir şekil (`Previous`). Eğer öyleyse, bu dizinin ortasında olduğunu gösterir.

#### S: Bir TextBox'un dizinin sonu olup olmadığı nasıl kontrol edilir?

C: Bir TextBox'un dizinin sonu olup olmadığını kontrol etmek için, bir sonraki formun olup olmadığını kontrol edebilirsiniz (`Next`) ancak önceki bir formu var (`Previous`). Eğer öyleyse, bu, dizinin sonu olduğu anlamına gelir.

#### S: TextBox'lar dışındaki öğelerin sırasını kontrol edebilir miyiz?

C: Evet, .NET için Aspose.Words kütüphanesini kullanarak paragraflar, tablolar, resimler vb. diğer öğelerin sırasını kontrol etmek mümkündür. İşlem, kontrol etmek istediğiniz belirli öğeye bağlı olarak değişecektir.

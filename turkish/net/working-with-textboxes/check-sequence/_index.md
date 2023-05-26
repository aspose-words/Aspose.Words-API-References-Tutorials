---
title: Kontrol Sırası
linktitle: Kontrol Sırası
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki Metin Kutularının sırasını nasıl kontrol edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-textboxes/check-sequence/
---

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
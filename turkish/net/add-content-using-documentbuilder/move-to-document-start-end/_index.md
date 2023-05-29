---
title: Belge Başlangıç Sonuna Taşı
linktitle: Belge Başlangıç Sonuna Taşı
second_title: Aspose.Words for .NET API Referansı
description: Bu adım adım kılavuz ile Word belgelerinde belge başlangıcına ve bitişine gitmek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-document-start-end/
---

Bu örnekte, Aspose.Words for .NET'in Belge Başlangıcına/Bitişine Taşı özelliğini inceleyeceğiz. Aspose.Words, geliştiricilerin Word belgelerini program aracılığıyla oluşturmasına, değiştirmesine ve dönüştürmesine olanak sağlayan güçlü bir belge işleme kitaplığıdır. Belge Başlangıcına/Bitişine Taşı özelliği, DocumentBuilder sınıfını kullanarak bir belgenin başına veya sonuna gitmemizi sağlar.

## Kaynak kodunu adım adım açıklama

Aspose.Words for .NET kullanarak Belge Başlangıcına/Bitirine Taşı özelliğinin nasıl kullanılacağını anlamak için kaynak kodunu adım adım inceleyelim.


## 1. Adım: Belge ve belge oluşturucuyu başlatma

Ardından, Document ve DocumentBuilder nesnelerini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belge başlangıcına gitme

İmleç konumunu belgenin başına taşımak için DocumentBuilder sınıfının MoveToDocumentStart yöntemini kullanın:

```csharp
builder.MoveToDocumentStart();
```

## 3. Adım: Belgenin sonuna gitme

İmleç konumunu belgenin sonuna taşımak için DocumentBuilder sınıfının MoveToDocumentEnd yöntemini kullanın:

```csharp
builder.MoveToDocumentEnd();
```

## Adım 4: İmleç konumunun çıktısını alma

Console.WriteLine veya istediğiniz başka bir yöntemi kullanarak imleç konumunun çıktısını alabilirsiniz. Örneğin:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Aspose.Words for .NET kullanarak Document Start/End'e Taşı için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İmleç konumunu belgenizin başına taşıyın.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// İmleç konumunu belgenizin sonuna taşıyın.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Çözüm

Bu örnekte, Aspose.Words for .NET'in Belge Başlangıcına/Bitişine Taşı özelliğini inceledik. DocumentBuilder sınıfını kullanarak bir belgenin başına ve sonuna nasıl gidileceğini öğrendik. Bu özellik, Word belgeleriyle programlı olarak çalışırken ve belgedeki belirli konumlara içerik eklemeye veya değiştirmeye ihtiyaç duyulduğunda kullanışlıdır.
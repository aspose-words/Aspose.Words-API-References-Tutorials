---
title: Düğüm Türünü Kullan
linktitle: Düğüm Türünü Kullan
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belgeye özgü bilgilere erişmek için düğüm türünü nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-node/use-node-type/
---

Aspose.Words for .NET ile düğüm tipi işlevselliğinin nasıl kullanılacağını gösteren aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce, Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Bu, Aspose.Words kitaplığının içe aktarılmasını ve gerekli ad alanlarının kaynak dosyanıza eklenmesini içerir.

```csharp
using Aspose.Words;
```

## 2. Adım: Yeni bir belge oluşturun
 Bu adımda, kullanarak yeni bir belge oluşturacağız.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Belge Düğümü Türünü Alın
 Bir belgenin düğüm tipini elde etmek için,`NodeType` mülk.

```csharp
NodeType type = doc.NodeType;
```

### Aspose.Words for .NET ile Düğüm Tipini Kullanmak İçin Örnek Kaynak Kodu

```csharp
Document doc = new Document();

NodeType type = doc.NodeType;
```

Bu, düğüm tipini Aspose.Words for .NET ile kullanmak için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun.


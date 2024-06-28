---
title: Uyarı Kaynağını Kullan
linktitle: Uyarı Kaynağını Kullan
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile uyarı kaynağının nasıl kullanılacağını öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/use-warning-source/
---

Bu örnekte size uyarı kaynağının Aspose.Words for .NET ile nasıl kullanılacağını göstereceğiz. Uyarı kaynağı, geri arama işlevi kullanıldığında uyarının kaynağını gösterir.

## 1. Adım: Belgeyi yükleme

 Uyarıları içeren mevcut bir belgeyi kullanarak yükleyeceğiz.`Load` yöntemi`Document` sınıf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Adım 3: Uyarı Kaynağını Kullanma

 Belgenin ayarını yaparak uyarı kaynağını kullanacağız.`WarningCallback` bir koleksiyona ait mülk`WarningInfo` nesneler.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## 4. Adım: Belgeyi kaydetme

Son olarak belgeyi istediğimiz formatta kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Aspose.Words for .NET ile Uyarı Kaynağını Kullanmak için Örnek Kaynak Kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Tebrikler! Artık uyarı kaynağını Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.

### SSS'ler

#### S: "Uyarı" etiketinin görünümünü özelleştirebilir miyiz?

 C: "Uyarı" etiketinin formatı, kullanılan Markdown oluşturucuya bağlıdır. Çoğu durumda, görünümü hedeflemek için CSS kullanarak özelleştirebilirsiniz.`blockquote` belgenizde etiketleyin.

#### S: "Uyarı" etiketine simge eklemek mümkün müdür?

C: Evet, Markdown belgenizdeki HTML kodunu kullanarak "Uyarı" etiketine simgeler eklemek mümkündür. Bir ekleyebilirsiniz`span` Uyarı metninin yanında bir simge görüntülemek için uygun sınıfla etiketleyin.

#### S: "Uyarı" etiketi tüm Markdown okuyucularıyla uyumlu mudur?

 C: "Uyarı" etiketinin uyumluluğu, kullanılan Markdown oluşturma işlemine bağlıdır. Çoğu Markdown okuyucusu şunları destekleyecektir:`blockquote` vurgulanan metni görüntülemek için etiketini kullanın, ancak tam görünüm farklılık gösterebilir.
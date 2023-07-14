---
title: Uyarı Kaynağını Kullan
linktitle: Uyarı Kaynağını Kullan
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile uyarı kaynağının nasıl kullanılacağını adım adım öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/use-warning-source/
---

Bu örnekte, uyarı kaynağının Aspose.Words for .NET ile nasıl kullanılacağını göstereceğiz. Uyarı kaynağı, geri arama işlevini kullanırken uyarının kaynağını gösterir.

## 1. Adım: Belgeyi yükleme

 Kullanarak uyarılar içeren mevcut bir belgeyi yükleyeceğiz.`Load` yöntemi`Document` sınıf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## 3. Adım: Uyarı Kaynağını Kullanma

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

### Uyarı Kaynağını Aspose.Words for .NET ile Kullanmak için Örnek Kaynak Kodu

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

Tebrikler! Artık uyarı kaynağının Aspose.Words for .NET ile nasıl kullanılacağını öğrendiniz.

### SSS

#### S: "Uyarı" etiketinin görünümünü özelleştirebilir miyiz?

C: "Uyarı" etiketinin formatı, kullanılan Markdown oluşturucuya bağlıdır. Çoğu durumda, görünümü hedeflemek için CSS'yi kullanarak özelleştirebilirsiniz.`blockquote` belgenizde etiketleyin.

#### S: "Uyarı" etiketine simgeler eklemek mümkün mü?

 C: Evet, Markdown belgenizdeki HTML kodunu kullanarak "Uyarı" etiketine simgeler eklemek mümkündür. ekleyebilirsiniz`span` uyarı metninin yanında bir simge görüntülemek için uygun sınıfla etiketleyin.

#### S: "Uyarı" etiketi tüm Markdown okuyucularıyla uyumlu mu?

 C: "Uyarı" etiketinin uyumluluğu, kullanılan Markdown işlemeye bağlıdır. Çoğu Markdown okuyucusu aşağıdakileri destekleyecektir:`blockquote` vurgulanan metni görüntülemek için etiketleyin, ancak tam görünüm değişebilir.
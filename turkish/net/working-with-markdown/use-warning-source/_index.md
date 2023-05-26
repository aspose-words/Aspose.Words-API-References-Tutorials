---
title: Uyarı Kaynağını Kullan
linktitle: Uyarı Kaynağını Kullan
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile uyarı kaynağının nasıl kullanılacağını adım adım öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/use-warning-source/
---

Bu örnekte, uyarı kaynağının Aspose.Words for .NET ile nasıl kullanılacağını göstereceğiz. Uyarı kaynağı, geri arama işlevini kullanırken uyarının kaynağını belirtir.

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
---
title: Kaynak Steam Yazı Tipi Kaynağı Örneği
linktitle: Kaynak Steam Yazı Tipi Kaynağı Örneği
second_title: Aspose.Words for .NET API Referansı
description: Özel yazı tiplerini Aspose.Words for .NET'e yüklemek için Kaynak Akışı Yazı Tipi Kaynağını nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/resource-steam-font-source-example/
---

Bu öğreticide, Resource Flow Font Source'u Aspose.Words for .NET ile nasıl kullanacağınız konusunda size yol göstereceğiz. Bu yazı tipi kaynağı, özel yazı tiplerini uygulamanıza dahil etmek istediğinizde yararlı olabilecek bir kaynak akışından yazı tiplerini yüklemenize olanak tanır.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin ve Kaynak Akışı Yazı Tipi Kaynağını Ayarlayın
 Ardından, kullanarak belgeyi yükleyeceğiz`Document` class ve kullanarak kaynak akışı yazı tipi kaynağını ayarlayın.`FontSettings.DefaultInstance.SetFontsSources()` sınıf. Bu, Aspose.Words'ün kaynak akışındaki yazı tiplerini bulmasını sağlayacaktır.

```csharp
// Belge yükleyin ve kaynak akışı yazı tipi kaynağını ayarlayın
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## 3. Adım: Belgeyi kaydedin
Son olarak belgeyi kaydedeceğiz. Yazı tipleri, belirtilen kaynak akışından yüklenecek ve belgeye gömülecektir.

```csharp
// belgeyi kaydet
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Aspose.Words for .NET kullanan Kaynak Steam Yazı Tipi Kaynak Örneği için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Çözüm
Bu eğitimde, Resource Flow Font Source'u Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz. Bu özellik, belgelerinize özel yazı tiplerini gömmek istediğinizde kullanışlı olan bir kaynak beslemesinden yazı tiplerini yüklemenizi sağlar. Farklı yazı tiplerini deneyin ve Aspose.Words'ün yazı tipi yönetimi için sunduğu olanakları keşfedin.

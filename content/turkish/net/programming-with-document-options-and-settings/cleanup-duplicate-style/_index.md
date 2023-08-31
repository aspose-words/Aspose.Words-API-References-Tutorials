---
title: Yinelenen Stili Temizleme
linktitle: Yinelenen Stili Temizleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgedeki yinelenen stilleri temizlemek için adım adım kılavuz. Tam kaynak kodu dahildir.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

Bu eğitimde, Aspose.Words for .NET ile yinelenen stilleri temizlemek için C# kaynak kodunu adım adım anlatacağız. Bu özellik, bir belgeden yinelenen stillerin kaldırılmasına yardımcı olur.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, temizlemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Temizlemeden önce stilleri sayın

Temizlemeye devam etmeden önce, belgede bulunan stillerin sayısını sayacağız. Stil sayısını görüntülemek için aşağıdaki kodu kullanın:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Bu ifade, belgede bulunan stillerin sayısını görüntüler.

## 4. Adım: Yinelenen stilleri temizleyin

Şimdi yinelenen stilleri belgeden temizleyelim. Temizlemeyi gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Bu kod, belirtilen seçenekleri kullanarak belgedeki yinelenen stilleri temizler. Bu örnekte,`DuplicateStyle` yinelenen stilleri temizleme seçeneği.

## Adım 5: Temizledikten sonra stilleri sayın

Temizliği yaptıktan sonra, azalıp azalmadığını kontrol etmek için stil sayısını tekrar sayacağız. Yeni stil sayısını görüntülemek için aşağıdaki kodu kullanın:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Bu ifade, temizlikten sonra kalan stillerin sayısını gösterir.

### Aspose.Words for .NET kullanarak Duplicate Style Temizleme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Temizlemeden önce stillerin sayısı.
	Console.WriteLine(doc.Styles.Count);

	// Belgedeki yinelenen stilleri temizler.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//Temizleme sonrası stil sayısı azaltıldı.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```
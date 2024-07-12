---
title: Yinelenen Stili Temizleme
linktitle: Yinelenen Stili Temizleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgedeki yinelenen stilleri temizlemek için adım adım kılavuz. Tam kaynak kodu dahil.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

Bu eğitimde, Aspose.Words for .NET ile yinelenen stilleri temizlemek için C# kaynak kodunu adım adım anlatacağız. Bu özellik, bir belgeden yinelenen stillerin kaldırılmasına yardımcı olur.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda temizlemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Temizlemeden önce stilleri sayın

Temizliğe devam etmeden önce belgede bulunan stil sayısını sayacağız. Stil sayısını görüntülemek için aşağıdaki kodu kullanın:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Bu ifade, belgede bulunan stillerin sayısını görüntüler.

## 4. Adım: Yinelenen stilleri temizleyin

Şimdi belgedeki yinelenen stilleri temizleyelim. Temizleme işlemini gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Bu kod, belirtilen seçenekleri kullanarak belgedeki yinelenen stilleri temizler. Bu örnekte, etkinleştirdik`DuplicateStyle` yinelenen stilleri temizleme seçeneği.

## 5. Adım: Temizledikten sonra stilleri sayın

Temizliği yaptıktan sonra stil sayısını tekrar sayıp azalıp azalmadığını kontrol edeceğiz. Yeni stil sayısını görüntülemek için aşağıdaki kodu kullanın:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Bu ifade, temizlemeden sonra kalan stil sayısını görüntüler.

### Aspose.Words for .NET kullanarak Yinelenen Stili Temizleme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Temizlemeden önceki stillerin sayısı.
	Console.WriteLine(doc.Styles.Count);

	// Belgedeki yinelenen stilleri temizler.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Temizleme işleminden sonraki stil sayısı azaltıldı.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```
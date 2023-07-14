---
title: Kullanılmayan Stilleri ve Listeleri Temizleme
linktitle: Kullanılmayan Stilleri ve Listeleri Temizleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgedeki kullanılmayan stilleri ve listeleri temizlemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

Bu eğitimde, Aspose.Words for .NET ile kullanılmayan stilleri ve listeleri temizlemek için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgede kullanılmayan stilleri ve listeleri kaldırmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, temizlemek istediğimiz kullanılmayan stilleri ve listeleri içeren Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Temizlemeden önce stilleri ve listeleri sayın

Temizlemeden önce, belgede bulunan stil ve listelerin sayısını sayacağız. Sayaçları görüntülemek için aşağıdaki kodu kullanın:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Bu talimatlar, temizlemeden önce belgede bulunan stillerin ve listelerin sayısını gösterir.

## 4. Adım: Kullanılmayan stilleri ve listeleri temizleyin

Şimdi kullanılmayan stilleri ve listeleri belgeden temizleyelim. Temizlemeyi gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Bu kod, belirtilen seçenekleri kullanarak kullanılmayan stilleri ve listeleri belgeden temizler. Bu örnekte,`UnusedStyles` kullanılmayan stilleri kaldırma ve devre dışı bırakma seçeneği`UnusedLists` listeleri kullanılmasalar bile saklama seçeneği.

## 5. Adım: Temizledikten sonra stilleri ve listeleri sayın

Temizlemeyi yaptıktan sonra, daraltılmış olup olmadıklarını kontrol etmek için stilleri ve listeleri tekrar sayacağız. Yeni sayaçları görüntülemek için aşağıdaki kodu kullanın:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Bu talimatlar, temizlikten sonra kalan stil ve liste sayısını gösterir.

### Aspose.Words for .NET kullanarak Kullanılmayan Stilleri ve Listeleri Temizlemek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Yerleşik stillerle birleştiğinde, belgenin artık sekiz stili vardır.
	// Belgede herhangi bir metin varken özel bir stil "kullanılmış" olarak işaretlenir
	// bu tarzda biçimlendirilmiştir. Bu, eklediğimiz 4 stilin şu anda kullanılmadığı anlamına gelir.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Verilen CleanupOptions'a bağlı olarak kullanılmayan stilleri ve listeleri belgeden temizler.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeden kullanılmayan stilleri ve listeleri nasıl temizleyeceğinizi öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek bu özelliği kendi belgelerinize kolayca uygulayabilirsiniz.


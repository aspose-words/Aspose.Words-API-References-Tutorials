---
title: Yer İşareti Verilerini Güncelle
linktitle: Yer İşareti Verilerini Güncelle
second_title: Aspose.Words for .NET API Referansı
description: .NET için Aspose.Words yer imi veri güncelleme özelliğinin C# kaynak kodunu açıklayan adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/update-bookmark-data/
---

Bu eğitimde, Aspose.Words for .NET'in Yer İşareti Verilerini Güncelle özelliğini anlamak ve uygulamak için adım adım ilerleyen bir kılavuzdan geçeceğiz. Bu özellik, C# kaynak kodunu kullanarak bir Word belgesindeki yer imlerinin içeriğini ve özelliklerini güncellemenizi sağlar.

## Gereksinimler

Öğreticiye devam etmeden önce, aşağıdaki gereksinimlere sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı kurulu
- C# programlama dili hakkında temel bilgi
- Visual Studio veya başka herhangi bir uyumlu IDE

## 1. Adım: Belgeyi yükleyin

Bu adımda güncellemek istediğimiz yer imlerini içeren Word belgesini yükleyeceğiz. Belgenin belirli bir dizinde saklandığını varsayarsak, belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu gerçek dizin yolu ile.

## 2. Adım: Yer işaretine erişin

Yer imi verilerini güncellemek için önce belgedeki belirli yer işaretine erişmemiz gerekir. Her yer iminin kendisiyle ilişkilendirilmiş benzersiz bir adı vardır. "MyBookmark1" adlı bir yer imine erişmek için aşağıdaki kodu kullanın:

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

Yer imi adının belgenizdeki adla eşleştiğinden emin olun. Gereksinimlerinize göre değiştirebilirsiniz.

## 3. Adım: Yer imi özelliklerini ve içeriğini güncelleyin

Yer imine eriştiğinizde özelliklerini ve içeriğini güncelleyebilirsiniz. Aşağıdaki kod parçacığında yer imi adını ve metnini güncelleyeceğiz:

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

Yer imi adını ve yeni metni ihtiyaçlarınıza göre özelleştirebilirsiniz. Yukarıdaki kod, yer imini "RenamedBookmark" olarak yeniden adlandırır ve metin içeriğini günceller.

## 4. Adım: Güncellenen belgeyi kaydedin

Yer imi verilerini güncelledikten sonra, değiştirilen belgeyi kaydetmeniz gerekir. Belgeyi kaydetmek için aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

Bu kod, değiştirilen belgeyi "UpdatedDocument.docx" adıyla orijinal belgeyle aynı dizine kaydedecektir.

### Aspose.Words for .NET kullanarak Yer İşareti Verilerini Güncellemek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu gerçek dizin yolu ile.

## Çözüm

Tebrikler! Aspose.Words for .NET kullanarak yer imi verilerini nasıl güncelleyeceğinizi başarıyla öğrendiniz. Bu öğreticide sağlanan adım adım kılavuzu izleyerek, artık bu özelliği C# uygulamalarınıza dahil edebilmeli ve Word belgeleri içindeki yer imlerini programlı olarak değiştirebilmelisiniz.
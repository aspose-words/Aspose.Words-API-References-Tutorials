---
title: Doc'tan Docx'e
linktitle: Doc'tan Docx'e
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini .doc'tan Docx formatına nasıl dönüştüreceğinizi öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/doc-to-docx/
---

Bu öğreticide, .doc formatındaki bir Word belgesini Docx formatına dönüştürmek için Aspose.Words for .NET kullanma sürecini adım adım anlatacağız. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınız konusunda size rehberlik edeceğiz.

Başlamak için, geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Geliştirme Ortamını Kurma

Kodlamaya başlamadan önce, uygun bir geliştirme ortamına sahip olduğunuzdan emin olun. Visual Studio'yu veya tercih ettiğiniz C# IDE'yi açın ve yeni bir proje oluşturun.

## 2. Adım: Referans Ekleme ve Ad Alanlarını İçe Aktarma

Aspose.Words for .NET'i kullanmak için projenizdeki kütüphaneye referanslar eklemeniz gerekir. Projenizdeki Referanslar klasörüne sağ tıklayın, "Add Reference" öğesini seçin ve Aspose.Words for .NET kitaplığını kurduğunuz konuma göz atın. Uygun sürümü seçin ve referansı eklemek için "Tamam"a tıklayın.

Ardından, gerekli ad alanlarını C# dosyanızın üstüne alın:

```csharp
using Aspose.Words;
```

## 3. Adım: Belge Nesnesini Başlatma

 Bu adımda,`Document` .doc biçimindeki kaynak belgenizin yolunu içeren nesne. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu gerçek dizin yolu ile ve`"Document.doc"` kaynak belgenizin adıyla. İşte kod parçacığı:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## Adım 4: Belgeyi Docx Formatına Dönüştürme

 Artık başlattığınıza göre`Document`nesne, dönüştürme işlemine devam edebilirsiniz. Aspose.Words for .NET, özelleştirme için çeşitli seçenekler ve ayarlar sunar, ancak temel dönüştürme için ek parametre gerekmez.

## Adım 5: Dönüştürülen Belgeyi Kaydetme

 Dönüştürülen belgeyi Docx biçiminde kaydetmek için, aramanız gerekir.`Save` yöntemi`Document` nesne. Çıkış belgesi için yol ve dosya adı sağlayın. Bu örnekte, onu şu şekilde kaydedeceğiz:`"BaseConversions.DocToDocx.docx"`. İşte kod parçacığı:

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak .doc formatındaki bir Word belgesini başarıyla Docx formatına dönüştürdünüz.

### Aspose.Words for .NET kullanan Doc To Docx için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.





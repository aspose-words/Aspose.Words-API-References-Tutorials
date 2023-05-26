---
title: Docx'ten Rtf'ye
linktitle: Docx'ten Rtf'ye
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini Docx'ten RTF formatına nasıl dönüştüreceğinizi öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-rtf/
---

Bu adım adım öğreticide, Docx formatındaki bir Word belgesini RTF'ye dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Akıştan Belgeyi Okuma

İlk önce, Docx belgesini okumak için bir akış açın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## 2. Adım: Belgeyi Yükleme

Ardından, belgeyi akıştan yükleyin:

```csharp
Document doc = new Document(stream);
```

## 3. Adım: Akışı Kapatma

Belge belleğe yüklendiğinden akışı kapatabilirsiniz:

```csharp
stream.Close();
```

## Adım 4: Belge Üzerinde İşlemleri Gerçekleştirme

Bu noktada belge üzerinde istediğiniz işlemleri yapabilirsiniz.

## Adım 5: Belgeyi RTF Formatında Kaydetme

Belgeyi RTF biçiminde kaydetmek için bir bellek akışına kaydedin:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Adım 6: Akışı Geri Sarma

Bellek akışını bir dosyaya yazmadan önce konumunu sıfıra geri sarın:

```csharp
dstStream.Position = 0;
```

## Adım 7: Akışı Dosyaya Yazma

Son olarak, bellek akışını bir RTF dosyasına yazın:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

Bu kadar! Aspose.Words for .NET'i kullanarak Docx formatındaki bir Word belgesini başarıyla RTF'ye dönüştürdünüz.

### Aspose.Words for .NET kullanan Docx To Rtf için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Aspose.Words'ün bir belgeyi yüklemesi için salt okunur erişim yeterlidir.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//Akışı şimdi kapatabilirsiniz, belge bellekte olduğu için artık buna gerek yoktur.
	stream.Close();

	// ... belgeyle bir şeyler yapın.

	// Belgeyi farklı bir biçime dönüştürün ve akışa kaydedin.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Bir sonraki okuyucu için hazır olması için akış konumunu sıfıra geri sarın.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.
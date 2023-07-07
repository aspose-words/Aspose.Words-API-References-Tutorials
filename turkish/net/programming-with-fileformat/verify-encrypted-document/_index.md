---
title: Şifrelenmiş Word Belgesini Doğrulayın
linktitle: Şifrelenmiş Word Belgesini Doğrulayın
second_title: Aspose.Words for .NET API Referansı
description: Bir word belgesinin Aspose.Words for .NET ile şifrelenmiş olduğunu doğrulamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-fileformat/verify-encrypted-document/
---

Bu makale, Encrypted Word Document Verification özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgenin şifrelenip şifrelenmediğini nasıl kontrol edeceğinizi öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Dosya biçimini algıla

 Daha sonra,`DetectFileFormat` yöntemi`FileFormatUtil` dosya biçimi bilgilerini algılamak için sınıf. Bu örnekte, şifrelenmiş belgenin "Encrypted.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## 3. Adım: Belgenin şifrelenip şifrelenmediğini kontrol edin

 biz kullanıyoruz`IsEncrypted` mülkiyeti`FileFormatInfo` belgenin şifrelenip şifrelenmediğini kontrol etmek için nesne. Bu özellik döndürür`true` belge şifreliyse, aksi takdirde geri döner`false`. Sonucu konsolda gösteriyoruz.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Bu kadar ! Aspose.Words for .NET kullanılarak bir belgenin şifrelenip şifrelenmediğini başarıyla kontrol ettiniz.

### Aspose.Words for .NET ile şifrelenmiş belgeleri doğrulamak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Sıkça Sorulan Sorular

### S: Şifrelenmiş bir Word belgesini doğrulama adımları nelerdir?

Şifrelenmiş bir Word belgesini doğrulama adımları aşağıdaki gibidir:

Belge dizinini tanımlayın.

Dosya biçimini algıla.

Belgenin şifrelenip şifrelenmediğini kontrol edin.

### S: Belge dizinini nasıl ayarlayabilirim?
 Belgeler dizinini ayarlamak için değiştirmeniz gerekir`"YOUR DOCUMENT DIRECTORY"` aşağıdaki kodda belgeler dizininizin gerçek yolu ile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### S: Dosya formatı nasıl tespit edilir?
 kullanabilirsiniz`DetectFileFormat` yöntemi`FileFormatUtil` dosya biçimi bilgilerini algılamak için sınıf. Aşağıdaki örnekte, şifrelenmiş belgenin adının "Encrypted.docx" olduğunu ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### S: Belgenin şifrelenip şifrelenmediği nasıl kontrol edilir?
 kullanabilirsiniz`IsEncrypted` mülkiyeti`FileFormatInfo` belgenin şifrelenip şifrelenmediğini kontrol etmek için nesne. Bu özellik döndürür`true` belge şifreliyse, aksi takdirde geri döner`false`. Sonuç konsolda görüntülenir:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### S: Aspose.Words for .NET kullanılarak bir belgenin şifrelenip şifrelenmediği nasıl kontrol edilir?
Bu öğreticide belirtilen adımları izleyerek ve sağlanan kaynak kodunu çalıştırarak, bir belgenin Aspose.Words for .NET kullanılarak şifrelenip şifrelenmediğini kontrol edebilirsiniz.

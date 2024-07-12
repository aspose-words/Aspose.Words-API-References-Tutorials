---
title: Şifrelenmiş Word Belgesini Doğrulayın
linktitle: Şifrelenmiş Word Belgesini Doğrulayın
second_title: Aspose.Words Belge İşleme API'si
description: Bir word belgesinin Aspose.Words for .NET ile şifrelendiğini doğrulamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-fileformat/verify-encrypted-document/
---

Bu makale, Şifreli Word Belgesi Doğrulama özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına ilişkin adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda bir belgenin şifrelenip şifrelenmediğini nasıl kontrol edeceğinizi anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Dosya formatını tespit edin

 Daha sonra şunu kullanırız:`DetectFileFormat` yöntemi`FileFormatUtil` Dosya formatı bilgilerini tespit etmek için sınıf. Bu örnekte, şifrelenmiş belgenin "Encrypted.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## 3. Adım: Belgenin şifrelenip şifrelenmediğini kontrol edin

 biz kullanıyoruz`IsEncrypted` mülkiyeti`FileFormatInfo` belgenin şifrelenip şifrelenmediğini kontrol etmek için nesne. Bu özellik şunu döndürür:`true` belge şifrelenmişse, aksi halde geri döner`false`. Sonucu konsolda gösteriyoruz.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Bu kadar ! Aspose.Words for .NET kullanarak bir belgenin şifrelenip şifrelenmediğini başarıyla kontrol ettiniz.

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

Dosya formatını algıla.

Belgenin şifrelenip şifrelenmediğini kontrol edin.

### S: Belge dizinini nasıl ayarlayabilirim?
 Belgeler dizinini ayarlamak için değiştirmeniz gerekir`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolunu aşağıdaki kodla belirtin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### S: Dosya formatı nasıl tespit edilir?
 Şunu kullanabilirsiniz:`DetectFileFormat` yöntemi`FileFormatUtil` Dosya formatı bilgilerini tespit etmek için sınıf. Aşağıdaki örnekte, şifrelenmiş belgenin "Encrypted.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### S: Belgenin şifrelenip şifrelenmediği nasıl kontrol edilir?
 Şunu kullanabilirsiniz:`IsEncrypted` mülkiyeti`FileFormatInfo` belgenin şifrelenip şifrelenmediğini kontrol etmek için nesne. Bu özellik şunu döndürür:`true` belge şifrelenmişse, aksi halde geri döner`false`. Sonuç konsolda görüntülenir:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### S: Aspose.Words for .NET kullanılarak bir belgenin şifrelenip şifrelenmediği nasıl kontrol edilir?
Bu eğitimde bahsedilen adımları takip ederek ve verilen kaynak kodunu çalıştırarak, bir belgenin Aspose.Words for .NET kullanılarak şifrelenip şifrelenmediğini kontrol edebilirsiniz.

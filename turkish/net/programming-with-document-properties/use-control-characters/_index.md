---
title: Kontrol Karakterlerini Kullan
linktitle: Kontrol Karakterlerini Kullan
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile kontrol karakterlerini kullanmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/use-control-characters/
---

Bu eğitimde, Aspose.Words for .NET ile kontrol karakterlerini kullanmak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, metindeki kontrol karakterlerini değiştirmenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Kontrol karakterlerini kullanma

Bu adımda, bir metinde kontrol karakterlerini kullanacağız. Aşağıdaki kodu kullanın:

```csharp
const string text = "test\r";
// "\r" kontrol karakterini "\r\n" ile değiştirin.
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Bu kod bir tanımlar`text` "\r" (yeni satır) kontrol karakterini içeren dize ve`Replace` "\r\n" (yeni satır) kontrol karakteriyle değiştirme yöntemi. satır ve ardından bir satır sonu).

### Aspose.Words for .NET kullanarak Kontrol Karakterlerini Kullan için örnek kaynak kodu

```csharp

	const string text = "test\r";
	// "\r" kontrol karakterini "\r\n" ile değiştirin.
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Yukarıdaki kodu değiştirerek kendi projenizde kullanabilirsiniz.`text` kontrol karakterlerini içeren kendi metninizle dize.

Artık kontrol karakterlerini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek, kendi uygulamalarınızda kontrol karakterlerini kolayca değiştirebilirsiniz.
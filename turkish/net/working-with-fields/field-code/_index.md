---
title: Alan Kodu
linktitle: Alan Kodu
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinizde alan kodunu ve alan sonucunu almak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fields/field-code/
---

Aspose.Words for .NET'in "Get Field Code" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleme

İlk adım, alan kodlarını almak istediğiniz belgeyi yüklemektir.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

"Hyperlinks.docx" dosyasını kendi dosyanızın adıyla değiştirdiğinizden emin olun.

## 3. Adım: Belge Alanlarına Göz Atın

 biz bir`foreach` belgede bulunan tüm alanlar arasında döngü yapmak için döngü.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 Döngünün her yinelemesinde, alan kodunu kullanarak alırız.`GetFieldCode()` yöntem. Ayrıca alanın sonucunu bir değişkende saklarız.

### Aspose.Words for .NET ile Alan Kodu Al için Kaynak Kodu Örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Belge alanları arasında geçiş yapın.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Alanın kodu ve sonucuyla bir şeyler yapın.
}
```

Bu örnekte, bir belge yükledik ve ardından belgede bulunan tüm alanlar arasında geçiş yaptık. Her yinelemede, alanın kodunu ve sonucunu aldık. Kodu ve sonuç alanlarını gerektiği gibi işlemek için kendi mantığınızı ekleyebilirsiniz.

Bu, Aspose.Words for .NET ile "Get Field Code" özelliğini kullanma konusundaki kılavuzumuzu sonlandırıyor.
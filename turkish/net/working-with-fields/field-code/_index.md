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

### SSS

#### S: Aspose.Words for .NET kullanarak bir Word belgesine nasıl alan ekleyebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesine alan eklemek için`DocumentBuilder.InsertField` uygun alan kodunu belirten yöntem. Örneğin, kullanabilirsiniz`builder.InsertField("MERGEFIELD CustomerName")` belgeye bir birleştirme alanı eklemek için.

#### S: Aspose.Words for .NET kullanarak bir belgedeki alanları nasıl güncelleyebilirim?

 C: Aspose.Words for .NET kullanarak belge alanlarını güncellemek için`Document.UpdateFields` yöntem. Bu, birleştirme alanları, tarih alanları vb. gibi belgede bulunan tüm alanları güncelleyecektir.

#### S: Aspose.Words for .NET'te belirli bir alanın değerini nasıl alabilirim?

 C: Aspose.Words for .NET'te belirli bir alanın değerini almak için`Field.GetResult` yönteminde alanın dizinini belirterek`Document.Range.Fields` Toplamak. Örneğin, kullanabilirsiniz`string value = document.Range.Fields[0].GetResult()` belgedeki ilk alanın değerini almak için.

#### S: Aspose.Words for .NET kullanarak bir belgeden bir alanı nasıl kaldırabilirim?

 C: Aspose.Words for .NET kullanarak bir belgeden bir alanı kaldırmak için`Field.Remove` yöntemi belirten`Field` Kaldırmak istediğiniz nesne. Bu, alanı belgeden kaldıracaktır.
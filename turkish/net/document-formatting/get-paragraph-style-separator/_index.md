---
title: Paragraf Stili Ayırıcısını Alın
linktitle: Paragraf Stili Ayırıcısını Alın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile paragraf stili ayırıcıyı nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/get-paragraph-style-separator/
---

Bu eğitimde, Aspose.Words for .NET ile Get Paragraph Style Separator özelliğini nasıl kullanacağınız konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için, belgelerinizin dizini belirtin ve belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## 2. Adım: Paragraf Stili Ayırıcılarını Bulma

Şimdi belgedeki tüm paragraflarda dolaşacağız ve paragrafın stil ayırıcı olup olmadığını kontrol edeceğiz. İşte nasıl:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Aspose.Words for .NET kullanan Get Paragraph Style Separator için örnek kaynak kodu

Aspose.Words for .NET ile Get Paragraph Style Separator özelliğinin tam kaynak kodu burada:

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

Bu kodla, Aspose.Words for .NET kullanan bir belgede paragraf stili ayırıcılarını bulabileceksiniz.


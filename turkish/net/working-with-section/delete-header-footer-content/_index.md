---
title: Üstbilgi Altbilgi İçeriğini Sil
linktitle: Üstbilgi Altbilgi İçeriğini Sil
second_title: Aspose.Words Belge İşleme API'sı
description: Bu öğreticide, Aspose.Words for .NET ile bir Word belgesinden üstbilgi ve altbilgi içeriğinin nasıl kaldırılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-section/delete-header-footer-content/
---

Bu öğreticide, size Aspose.Words library for .NET kullanarak üstbilgi ve altbilgi içeriğini Word belgesinden nasıl kaldıracağınızı göstereceğiz. Üst bilgilerden ve alt bilgilerden içerik kaldırmak, bu öğeleri belgenizden sıfırlamak veya kaldırmak istediğinizde faydalı olabilir. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı
- Kaldırmak istediğiniz üst bilgileri ve alt bilgileri içeren bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin ve bölüme gidin
 Ardından, Word belgesini bir örneğine yükleyeceğiz.`Document` sınıf. 0 indeksini kullanarak belgenin ilk bölümüne erişeceğiz.

```csharp
// belgeyi yükle
Document doc = new Document(dataDir + "Document.docx");

// Bölüme erişin
Section section = doc.Sections[0];
```

## 3. Adım: Üst bilgi ve alt bilgi içeriğini silin
 Bölümden üstbilgi ve altbilgi içeriğini kaldırmak için`ClearHeadersFooters` yöntem.

```csharp
section.ClearHeadersFooters();
```

### Aspose.Words for .NET kullanarak Üstbilgi Altbilgi İçeriğini Sil için örnek kaynak kodu 

```csharp

//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinden üstbilgi ve altbilgi içeriğinin nasıl kaldırılacağını gördük. Üst bilgilerden ve alt bilgilerden içerik kaldırmak, bu belirli öğeleri belgenizden sıfırlamanıza veya kaldırmanıza olanak tanır. Özel ihtiyaçlarınıza göre bu özelliği özelleştirmekten ve kullanmaktan çekinmeyin.

### Üst bilgi alt bilgi içeriğini silmek için SSS

#### S: Aspose.Words for .NET'te belge dizini nasıl ayarlanır?

 A: Belgelerinizi içeren dizine giden yolu ayarlamak için değiştirmelisiniz.`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### S: Aspose.Words for .NET'te belge ve erişim bölümü nasıl yüklenir?

 A: Word belgesini bir örneğine yüklemek için`Document` sınıf denir`doc` ve 0 indeksini kullanarak belgenin ilk bölümüne erişmek için aşağıdaki kodu kullanabilirsiniz:

```csharp
// belgeyi yükle
Document doc = new Document(dataDir + "Document.docx");

// Bölüme erişin
Section section = doc.Sections[0];
```

#### S: Aspose.Words for .NET'te üst bilgi ve alt bilgi içeriği nasıl kaldırılır?

 C: Bölümden üstbilgi ve altbilgi içeriğini kaldırmak için,`ClearHeadersFooters` yöntem:

```csharp
section.ClearHeadersFooters();
```

#### S: Değiştirilen belge Aspose.Words for .NET'e nasıl kaydedilir?

A: Üstbilgi ve altbilgi içeriğini sildikten sonra, değiştirilen belgeyi aşağıdaki kodu kullanarak bir dosyaya kaydedebilirsiniz:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```
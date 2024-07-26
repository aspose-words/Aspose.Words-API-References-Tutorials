---
title: Üstbilgi Altbilgi İçeriğini Sil
linktitle: Üstbilgi Altbilgi İçeriğini Sil
second_title: Aspose.Words Belge İşleme API'si
description: Bu eğitimde Aspose.Words for .NET ile bir Word belgesinden üstbilgi ve altbilgi içeriğini nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-section/delete-header-footer-content/
---

Bu eğitimde size Aspose.Words for .NET kütüphanesini kullanarak Word belgesindeki üst bilgi ve alt bilgi içeriğini nasıl kaldıracağınızı göstereceğiz. Üstbilgilerden ve altbilgilerden içeriğin kaldırılması, bu öğeleri belgenizden sıfırlamak veya kaldırmak istediğinizde yararlı olabilir. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- .NET için Aspose.Words kütüphanesi projenizde yüklü
- Kaldırmak istediğiniz üstbilgileri ve altbilgileri içeren bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, Word belgenizin konumuna giden dizin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi yükleyin ve bölüme gidin
 Daha sonra, Word belgesini bir örneğine yükleyeceğiz.`Document` sınıf. Belgenin ilk bölümüne 0 indeksini kullanarak erişeceğiz.

```csharp
// Belgeyi yükleyin
Document doc = new Document(dataDir + "Document.docx");

// Bölüme erişin
Section section = doc.Sections[0];
```

## 3. Adım: Üstbilgi ve altbilgi içeriğini silin
 Üst bilgi ve alt bilgi içeriğini bölümden kaldırmak için şunu kullanacağız:`ClearHeadersFooters` yöntem.

```csharp
section.ClearHeadersFooters();
```

### Aspose.Words for .NET kullanarak Üst Bilgi Alt Bilgi İçeriğini Silmek için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinden üstbilgi ve altbilgi içeriğinin nasıl kaldırılacağını gördük. İçeriği üstbilgilerden ve altbilgilerden kaldırmak, bu belirli öğeleri belgenizden sıfırlamanıza veya kaldırmanıza olanak tanır. Bu özelliği özel ihtiyaçlarınıza göre özelleştirmekten ve kullanmaktan çekinmeyin.

### Üst bilgi alt bilgi içeriğini silmek için SSS

#### S: Aspose.Words for .NET'te belge dizini nasıl ayarlanır?

C: Belgelerinizi içeren dizinin yolunu ayarlamak için değiştirmeniz gerekir`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### S: Aspose.Words for .NET'te belge ve erişim bölümü nasıl yüklenir?

 A: Word belgesini bir örneğine yüklemek için`Document` sınıf çağrıldı`doc` ve 0 dizinini kullanarak belgenin ilk bölümüne erişmek için aşağıdaki kodu kullanabilirsiniz:

```csharp
// Belgeyi yükleyin
Document doc = new Document(dataDir + "Document.docx");

// Bölüme erişin
Section section = doc.Sections[0];
```

#### S: Aspose.Words for .NET'te üstbilgi ve altbilgi içeriği nasıl kaldırılır?

 C: Üstbilgi ve altbilgi içeriğini bölümden kaldırmak için`ClearHeadersFooters` yöntem:

```csharp
section.ClearHeadersFooters();
```

#### S: Değiştirilen belge Aspose.Words for .NET'e nasıl kaydedilir?

C: Üstbilgi ve altbilgi içeriğini sildikten sonra, değiştirilen belgeyi aşağıdaki kodu kullanarak bir dosyaya kaydedebilirsiniz:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```
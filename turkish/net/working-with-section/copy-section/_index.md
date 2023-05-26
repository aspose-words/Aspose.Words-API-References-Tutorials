---
title: Bölümü Kopyala
linktitle: Bölümü Kopyala
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir bölümün başka bir belgeye nasıl kopyalanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-section/copy-section/
---

Bu eğitimde, bir Word belgesindeki bir bölümün Aspose.Words .NET kitaplığını kullanarak başka bir belgeye nasıl kopyalanacağını açıklayacağız. Bir bölümün kopyalanması, belirli bir bölümü kaynak belgeden hedef belgeye aktarmanıza olanak tanır. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı
- Kopyalamak istediğiniz bölümü içeren bir kaynak belge
- Bölümü kopyalamak istediğiniz boş bir hedef belge

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, belgelerinizin bulunduğu dizin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Kaynak ve hedef belgeleri yükleyin
 Ardından, kaynak belgeyi örneğinin bir örneğine yükleyeceğiz.`Document` sınıf denir`srcDoc` . Ayrıca boş bir örnek oluşturacağız.`Document` sınıf denir`dstDoc` hedef belge için.

```csharp
// Kaynak belgeyi yükleyin
Document srcDoc = new Document(dataDir + "Document.docx");

// Boş bir hedef belge oluştur
Document dstDoc = new Document();
```

## 3. Adım: Bölümü hedef belgeye kopyalayın
Bölümü kaynak belgeden hedef belgeye kopyalamak için kullanacağız`ImportNode` kaynak bölümü içe aktarma ve onu hedef belgeye ekleme yöntemi.

```csharp
// Kaynak bölümünü edinin
Section sourceSection = srcDoc.Sections[0];

// Bölümü hedef belgeye kopyalayın
Section newSection = (Section)dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
```

## 4. Adım: Hedef belgeyi kaydedin
Son olarak, kopyalanan bölümle birlikte hedef belgeyi bir dosyaya kaydedeceğiz.

```csharp
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");
```

### Aspose.Words for .NET kullanan Copy Section için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document.docx");
Document dstDoc = new Document();
Section sourceSection = srcDoc.Sections[0];
Section newSection = (Section) dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");

```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki bir bölümün başka bir belgeye nasıl kopyalanacağını gördük. Bölümleri kopyalamak, belirli bölümleri bir kaynak belgeden bir hedef belgeye kolayca aktarmanıza olanak tanır. Belgelerinizin bölümlerini verimli bir şekilde düzenlemek ve değiştirmek için bu yöntemi kullanmaktan çekinmeyin.
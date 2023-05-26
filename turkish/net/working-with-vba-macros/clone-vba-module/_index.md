---
title: Vba Modülünü Klonla
linktitle: Vba Modülünü Klonla
second_title: Aspose.Words for .NET API Referansı
description: Bu eğitimde, Aspose.Words for .NET ile bir Word belgesinden bir VBA modülünün nasıl kopyalanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-vba-macros/clone-vba-module/
---

Bu öğreticide, size Aspose.Words .NET kitaplığını kullanarak bir Word belgesinden bir VBA modülünü makrolarla nasıl klonlayacağınızı anlatacağız. Bir VBA modülünü klonlamak, VBA kodunu bir kaynak belgeden başka bir belgeye yeniden kullanmanıza veya kopyalamanıza olanak tanır. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı
- Klonlamak istediğiniz modülü içeren bir VBA projesi içeren bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Kaynak belgeyi yükleyin
Ardından, klonlamak istediğimiz VBA projesini ve modülü içeren kaynak Word belgesini yükleyeceğiz.

```csharp
// Kaynak belgeyi yükleyin
Document doc = new Document(dataDir + "VBA project.docm");
```

## 3. Adım: VBA projesiyle yeni bir belge oluşturun ve modülü klonlayın
Boş bir VBA projesi ile yeni bir belge oluşturacağız ve belirtilen modülü kaynak belgeden klonlayacağız.

```csharp
// Boş bir VBA projesiyle yeni bir belge oluşturun
Document destDoc = new Document { VbaProject = new VbaProject() };

// Modülü klonlayın
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## 4. Adım: Hedef belgeyi kaydedin
Son olarak, klonlanmış VBA modülü ile hedef belgeyi bir dosyaya kaydedeceğiz.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Aspose.Words for .NET kullanan Clone Vba Module için örnek kaynak kodu 
```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak makrolarla bir Word belgesinden bir VBA modülünün nasıl kopyalanacağını gördük. VBA modüllerini klonlamak, bir kaynak belgedeki VBA kodunu başka bir belgede kolayca yeniden kullanmanızı sağlar. Makrolarınızı farklı belgelerde düzenlemek ve yönetmek için bu özelliği kullanmaktan çekinmeyin.

---
title: Vba Projesi Oluştur
linktitle: Vba Projesi Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET ile bir Word belgesinde VBA projesi oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-vba-macros/create-vba-project/
---

Bu öğreticide, size Aspose.Words .NET kitaplığını kullanarak bir Word belgesinde nasıl VBA projesi oluşturacağınızı anlatacağız. Bir VBA projesi oluşturmak, Word belgenize özel VBA kodu eklemenizi sağlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yeni bir VBA belgesi ve projesi oluşturun
 Ardından, örnekleyerek yeni bir belge oluşturacağız.`Document` sınıfı ve boş bir VBA projesini başlatarak`VbaProject` sınıf.

```csharp
// Yeni bir belge oluştur
Document doc = new Document();

// Yeni bir VBA projesi oluştur
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## 3. Adım: Yeni bir modül oluşturun ve makro kaynak kodunu belirtin
 Örnekleyerek yeni bir modül oluşturacağız.`VbaModule` sınıf ve makro adını, türünü (prosedürel modül) ve kaynak kodunu belirterek.

```csharp
// Yeni bir modül oluştur
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Modülü VBA projesine ekleyin
doc.VbaProject.Modules.Add(module);
```

## 4. Adım: Belgeyi kaydedin
Son olarak oluşturduğumuz VBA projesi ile belgeyi bir dosya içerisinde kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Aspose.Words for .NET kullanarak Create Vba Project için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Yeni bir modül oluşturun ve bir makro kaynak kodu belirtin.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// VBA projesine modül ekleyin.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde VBA projesi oluşturmayı gördük. Bir VBA projesi oluşturmak, Word belgenize VBA kodu eklemenizi ve özelleştirmenizi sağlar. Görevleri otomatikleştirmek veya Word belgelerinize özel işlevler eklemek için bu özelliği kullanmaktan çekinmeyin.

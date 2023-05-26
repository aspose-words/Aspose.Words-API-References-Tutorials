---
title: Bölüm Ekle
linktitle: Bölüm Ekle
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine nasıl bölüm ekleyeceğinizi öğrenin. Belgenizi yapılandırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-section/add-section/
---

Bu eğitimde, Aspose.Words for .NET kütüphanesini kullanarak bir Word belgesine nasıl yeni bir bölüm ekleyeceğinizi anlatacağız. Bölümler eklemek, belgenizi daha verimli bir şekilde düzenlemenize ve yapılandırmanıza yardımcı olur. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Bir belge ve oluşturucu oluşturun
 İlk olarak, bir örneğini oluşturacağız`Document` sınıf ve ilgili`DocumentBuilder` belgeyi oluşturmak için yapıcı.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye içerik ekleyin
 Sonra, kullanacağız`DocumentBuilder`belgeye içerik eklemek için yapıcı. Bu örnekte, iki satır metin ekliyoruz.

```csharp
builder.Writeln("Hello1");
builder.Writeln("Hello2");
```

## 3. Adım: Yeni bir bölüm ekleyin
 Belgeye yeni bir bölüm eklemek için, örneğini oluşturacağız.`Section` sınıfına ekleyin ve`Sections` belgenin toplanması.

```csharp
Section sectionToAdd = new Section(doc);
doc.Sections.Add(sectionToAdd);
```

### Aspose.Words for .NET kullanan Add Section için örnek kaynak kodu 

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.Writeln("Hello1");
	builder.Writeln("Hello2");
	Section sectionToAdd = new Section(doc);
	doc.Sections.Add(sectionToAdd);

```
## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesine nasıl yeni bölüm ekleneceğini gördük. Belirtilen adımları izleyerek, bölümler ekleyerek belgenizi kolayca düzenleyebilir ve yapılandırabilirsiniz. Bölüm içeriğini ve özelliklerini özel ihtiyaçlarınıza göre özelleştirmekten çekinmeyin.
---
title: Alan Düzeyinde Yerel Ayarı Belirtin
linktitle: Alan Düzeyinde Yerel Ayarı Belirtin
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Word belgelerinde alan düzeyinde yerelleştirmeyi nasıl belirteceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/specify-locale-at-field-level/
---

Aspose.Words for .NET özelliğini kullanarak yerelleştirmeyi alan düzeyinde belirlemeye izin veren aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. Bu kodu kullanmadan önce Aspose.Words kütüphanesini projenize dahil ettiğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Düzenlenen belgenin kaydedileceği belgeler dizininizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: Bir belge oluşturucu oluşturun

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Burada bir örneğini oluşturuyoruz`DocumentBuilder` Belgeye alanlar eklememize izin verecek sınıf.

## 3. Adım: Belirli bir konuma sahip bir tarih alanı ekleyin

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Bir tür alanı eklemek için belge oluşturucuyu kullanıyoruz`FieldType.FieldDate` belgenin içine. ayarlayarak`LocaleId` mülkiyet`1049`, bu alan için Rusça yerelleştirmeyi belirtiyoruz.

## 4. Adım: Değiştirilen belgeyi kaydedin

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Son olarak, değiştirilen belgeyi belirtilen konumla belirtilen bir dosyaya kaydediyoruz.

### Aspose.Words for .NET ile alan düzeyinde yerelleştirmeyi belirtmek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Bu, Aspose.Words for .NET kullanan bir belgede alan düzeyinde yerelleştirmeyi belirtmek için örnek bir kaynak koduydu. Bu kodu, Word belgelerinize belirli konumlara sahip tarih alanları eklemek için kullanabilirsiniz.

### SSS

#### S: Aspose.Words for .NET'te alan düzeyinde yerel ayarı nasıl belirtebilirim?

 C: Aspose.Words for .NET'te yerel ayarı alan seviyesinde belirtmek için`FieldOptions` sınıf ve onun`FieldLocale` İstenen yerel ayarı ayarlamak için özellik. Örneğin, kullanabilirsiniz`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` Fransızca (Fransa) yerel ayarını belirtmek için.

#### S: Aspose.Words for .NET'te her alan için farklı bir yerel ayar belirlemek mümkün müdür?

 C: Evet, Aspose.Words for .NET'te her alan için farklı bir yerel ayar belirtmek mümkündür. kullanabilirsiniz`FieldOptions.FieldLocale` Özelliği, farklı bir yerel ayar atamak için belirli bir alanı oluşturmadan veya güncellemeden önce.

#### S: Aspose.Words for .NET'te bir alan için halihazırda kullanılan yerel ayarı nasıl edinebilirim?

 C: Aspose.Words for .NET'te bir alan için halihazırda kullanılan yerel ayarı almak için, alanın`Field.LocaleId` mülk. Bu, alanla ilişkili yerel tanımlayıcıyı almanıza olanak tanır.
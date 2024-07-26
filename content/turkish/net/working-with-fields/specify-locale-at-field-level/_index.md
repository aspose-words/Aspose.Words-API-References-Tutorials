---
title: Alan Düzeyinde Yerel Ayarı Belirtin
linktitle: Alan Düzeyinde Yerel Ayarı Belirtin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinde alan düzeyinde yerelleştirmeyi nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/specify-locale-at-field-level/
---

Burada, Aspose.Words for .NET özelliğini kullanarak alan düzeyinde yerelleştirmeyi belirlemeye olanak tanıyan aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. Bu kodu kullanmadan önce projenize Aspose.Words kütüphanesini eklediğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Düzenlenen belgenin kaydedileceği belge dizininize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: Belge oluşturucu oluşturun

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Burada bir örneğini oluşturuyoruz.`DocumentBuilder` belgeye alan eklememize izin verecek sınıf.

## 3. Adım: Belirli bir konuma sahip bir tarih alanı ekleyin

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Bir tür alanı eklemek için belge oluşturucuyu kullanıyoruz`FieldType.FieldDate` belgenin içine. Ayarlayarak`LocaleId`mülkiyet`1049`, bu alan için Rusça yerelleştirmesini belirtiyoruz.

## 4. Adım: Değiştirilen belgeyi kaydedin

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Son olarak, değiştirilen belgeyi belirtilen konumla belirtilen bir dosyaya kaydediyoruz.

### Aspose.Words for .NET ile alan düzeyinde yerelleştirmeyi belirlemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Bu, Aspose.Words for .NET kullanılarak bir belgede alan düzeyinde yerelleştirmeyi belirten örnek bir kaynak koduydu. Word belgelerinize belirli konumlara sahip tarih alanları eklemek için bu kodu kullanabilirsiniz.

### SSS'ler

#### S: Aspose.Words for .NET'te alan düzeyindeki yerel ayarı nasıl belirleyebilirim?

 C: Aspose.Words for .NET'te yerel ayarı alan düzeyinde belirtmek için`FieldOptions` sınıf ve onun`FieldLocale` İstenilen yerel ayarı ayarlama özelliği. Örneğin şunları kullanabilirsiniz:`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` Fransızca (Fransa) yerel ayarını belirtmek için.

#### S: Aspose.Words for .NET'te her alan için farklı bir yerel ayar belirlemek mümkün müdür?

 C: Evet, Aspose.Words for .NET'te her alan için farklı bir yerel ayar belirlemek mümkündür. Şunu kullanabilirsiniz:`FieldOptions.FieldLocale` Belirli bir alanı oluşturmadan veya güncellemeden önce, ona farklı bir yerel ayar atamak için özelliği kullanın.

#### S: Aspose.Words for .NET'te bir alan için halihazırda kullanılan yerel ayarı nasıl edinebilirim?

 C: Aspose.Words for .NET'te bir alanın halihazırda kullanılan yerel ayarını almak için alanın yerel ayarını kullanabilirsiniz.`Field.LocaleId`mülk. Bu, alanla ilişkili yerel ayar tanımlayıcısını almanıza olanak tanır.
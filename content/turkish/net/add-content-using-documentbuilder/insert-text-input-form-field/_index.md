---
title: Word Belgesine Metin Giriş Formu Alanı Ekle
linktitle: Word Belgesine Metin Giriş Formu Alanı Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET'i kullanarak Word belgelerine metin girişi form alanı eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-text-input-form-field/
---
Bu adım adım kılavuzda, C# kaynak kodunu kullanarak Word belgelerinize metin girişi form alanları eklemek ve değiştirmek için Aspose.Words for .NET'teki Metin Girişi Form Alanı Ekle özelliğini nasıl kullanacağınızı keşfedeceğiz. Metin girişi form alanları, kullanıcıların bir belgeye özel metin girmesine olanak tanır ve bu da onları etkileşimli formlar ve anketler oluşturmak için ideal kılar. Aşağıdaki talimatları izleyerek, belgelerinize zahmetsizce metin giriş formu alanları ekleyip özelleştirebileceksiniz. Başlayalım!

## Aspose.Words for .NET'te Metin Giriş Formu Alanı Ekle özelliğine giriş

Aspose.Words for .NET'teki Metin Giriş Formu Alanı Ekle özelliği, metin giriş form alanlarını program aracılığıyla Word belgelerinize eklemenizi sağlar. Bu form alanları, kullanıcıların özel metin veya veri girebileceği etkileşimli bir öğe sağlar.

## Özelliğin kullanımına ilişkin gereksinimleri anlama

Uygulamaya devam etmeden önce aşağıdaki gereksinimleri karşıladığınızdan emin olun:

1. Aspose.Words for .NET kütüphanesi projenizde yüklü.
2. Temel C# programlama dili bilgisi.
3. Mevcut bir Word belgesine veya yeni bir belgeye metin giriş formu alanı eklemek için.

Sorunsuz bir şekilde ilerlemek için bu önkoşullara sahip olduğunuzdan emin olun.

## C# kaynak kodunu kullanarak Metin Girişi Form Alanı Ekle'yi uygulamaya yönelik adım adım kılavuz

Sağlanan C# kaynak kodunu kullanarak Metin Giriş Formu Alanı Ekle özelliğini uygulamak için aşağıdaki adımları izleyin:

### 1. Adım: Belgeyi ve belge oluşturucuyu başlatma

Başlamak için belgeyi ve belge oluşturucuyu başlatın. Belge oluşturucu, Aspose.Words for .NET tarafından sağlanan ve Word belgelerini programlı olarak oluşturmamıza ve işlememize olanak tanıyan güçlü bir araçtır. Aşağıdaki kod parçacığını kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Adım 2: Metin Giriş Formu Alanını Ekleme

 Daha sonra metin giriş formu alanını belgeye ekleyeceğiz.`InsertTextInput` yöntem. Bu yöntem, form alanının adı, form alanının türü (bu durumda,`TextFormFieldType.Regular`), varsayılan değer ve maksimum uzunluk. İşte bir örnek:

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

Yukarıdaki kod, "TextInput" adında, varsayılan değeri "Hello" olan ve maksimum uzunluk sınırlaması olmayan bir metin giriş formu alanı ekleyecektir.

### 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi kullanarak belgeyi istediğiniz konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

Bu kod, belgeyi, eklenen metin giriş formu alanıyla birlikte belirtilen konuma kaydedecektir.

### Aspose.Words for .NET kullanarak Metin Giriş Formu Alanı Ekleme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine metin giriş formu alanlarını nasıl ekleyeceğinizi ve özelleştireceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak artık belgelerinize etkileşimli öğeler ekleyerek kullanıcıların özel metin veya veri girmesine olanak sağlayabilirsiniz.

### Word belgesine metin giriş formu alanı eklemek için SSS

#### S: Aspose.Words for .NET'teki Metin Giriş Formu Alanı Ekle özelliğinin amacı nedir?

C: Aspose.Words for .NET'teki Metin Giriş Formu Alanı Ekle özelliği, Word belgelerinize programlı olarak metin giriş formu alanları eklemenizi sağlar. Bu form alanları, kullanıcıların özel metin veya verileri doğrudan belgeye girmesine olanak tanır; bu da onları etkileşimli formlar, anketler veya soru formları oluşturmak için ideal kılar.

#### S: Metin Giriş Formu Alanı Ekle özelliğini kullanmanın önkoşulları nelerdir?

C: Metin Giriş Formu Alanı Ekle özelliğini uygulamadan önce aşağıdaki önkoşulları sağlamanız gerekir:
1. Aspose.Words for .NET kütüphanesi projenizde yüklü.
2. C# programlama dili hakkında temel bilgiler.
3. Mevcut bir Word belgesi veya metin giriş formu alanını eklemek istediğiniz yeni bir belge.

#### S: Metin giriş formu alanını nasıl özelleştiririm?

 C: Metin giriş formu alanını, çağrı sırasında belirli parametreler sağlayarak özelleştirebilirsiniz.`InsertTextInput`yöntem. Örneğin form alanı için adı, varsayılan değeri ve maksimum uzunluğu gerektiği gibi ayarlayabilirsiniz.

#### S: Tek bir belgeye birden çok metin giriş formu alanı ekleyebilir miyim?

 C: Evet, tek bir belgeye birden fazla metin giriş formu alanı ekleyebilirsiniz. Sadece aramanız yeterli`InsertTextInput` Birden çok form alanı eklemek için farklı adlara ve yapılandırmalara sahip bir yöntem.

#### S: Kullanıcılar belgedeki metin giriş formu alanıyla nasıl etkileşim kurabilir?

C: Metin giriş formu alanı belgeye eklendikten sonra kullanıcılar form alanına tıklayıp özel metin girmek için yazmaya başlayabilir. Form alanı, içeriği doğrudan belge içinde düzenlemelerine olanak tanır.
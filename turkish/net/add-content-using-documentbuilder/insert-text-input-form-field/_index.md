---
title: Word Belgesine Metin Giriş Formu Alanı Ekleme
linktitle: Word Belgesine Metin Giriş Formu Alanı Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Bu adım adım kılavuz ile Word belgelerine metin giriş formu alanı eklemek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-text-input-form-field/
---
Bu adım adım kılavuzda, C# kaynak kodunu kullanarak Word belgelerinize metin giriş formu alanları eklemek ve değiştirmek için Aspose.Words for .NET'teki Metin Giriş Formu Alanı Ekle özelliğinin nasıl kullanılacağını keşfedeceğiz. Metin giriş formu alanları, kullanıcıların bir belgeye özel metin girmesine izin vererek onları etkileşimli formlar ve anketler oluşturmak için ideal hale getirir. Aşağıdaki talimatları izleyerek metin giriş formu alanlarını belgelerinize zahmetsizce ekleyebilir ve özelleştirebilirsiniz. Başlayalım!

## Aspose.Words for .NET'te Metin Giriş Formu Alanı Ekle özelliğine giriş

Aspose.Words for .NET'teki Metin Giriş Formu Alanı Ekle özelliği, Word belgelerinize programlı olarak metin giriş formu alanları eklemenizi sağlar. Bu form alanları, kullanıcıların özel metin veya veri girebileceği etkileşimli bir öğe sağlar.

## Özelliği kullanmak için gereklilikleri anlama

Uygulamaya devam etmeden önce aşağıdaki gereksinimleri karşıladığınızdan emin olun:

1. Aspose.Words for .NET kitaplığı projenizde yüklü.
2. C# programlama dili hakkında temel bilgi.
3. Metin giriş formu alanına mevcut bir Word belgesi veya yeni bir belge ekleyin.

Sorunsuz ilerlemek için bu ön koşullara sahip olduğunuzdan emin olun.

## C# kaynak kodunu kullanarak Metin Giriş Formu Alanı Ekle'yi uygulamaya yönelik adım adım kılavuz

Sağlanan C# kaynak kodunu kullanarak Metin Giriş Formu Alanı Ekle özelliğini uygulamak için aşağıdaki adımları izleyin:

### 1. Adım: Belge ve belge oluşturucuyu başlatma

Başlamak için belgeyi ve belge oluşturucuyu başlatın. Belge oluşturucu, Aspose.Words for .NET tarafından sağlanan ve Word belgelerini programlı olarak oluşturmamıza ve değiştirmemize izin veren güçlü bir araçtır. Aşağıdaki kod parçacığını kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### 2. Adım: Metin Giriş Formu Alanını Ekleme

 Ardından, metin giriş formu alanını kullanarak belgeye ekleyeceğiz.`InsertTextInput` yöntem. Bu yöntem, form alanının adı, form alanının türü (bu durumda,`TextFormFieldType.Regular`), varsayılan değer ve maksimum uzunluk. İşte bir örnek:

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

Yukarıdaki kod, "TextInput" adında, varsayılan "Merhaba" değeri olan ve maksimum uzunluk kısıtlaması olmayan bir metin giriş formu alanı ekleyecektir.

### 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

Bu kod, belirtilen konuma eklenen metin giriş formu alanıyla birlikte belgeyi kaydedecektir.

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

Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine metin girişi form alanlarını nasıl ekleyeceğinizi ve özelleştireceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan C# kaynak kodunu kullanarak, artık belgelerinize etkileşimli öğeler ekleyerek kullanıcıların özel metin veya veri girmelerini sağlayabilirsiniz.

### Word belgesine metin giriş formu alanı eklemek için SSS

#### S: Aspose.Words for .NET'teki Metin Giriş Formu Alanı Ekle özelliğinin amacı nedir?

C: Aspose.Words for .NET'teki Metin Giriş Formu Alanı Ekle özelliği, Word belgelerinize programlı bir şekilde metin giriş formu alanları eklemenizi sağlar. Bu form alanları, kullanıcıların özel metin veya verileri doğrudan belgeye girmelerine olanak tanıyarak onları etkileşimli formlar, anketler veya anketler oluşturmak için ideal hale getirir.

#### S: Metin Giriş Formu Alanı Ekle özelliğini kullanmanın ön koşulları nelerdir?

C: Metin Giriş Formu Alanı Ekle özelliğini uygulamadan önce aşağıdaki ön koşulları sağlamanız gerekir:
1. Aspose.Words for .NET kitaplığı projenizde yüklü.
2. C# programlama dili hakkında temel bilgi.
3. Metin giriş formu alanını eklemek istediğiniz mevcut bir Word belgesi veya yeni bir belge.

#### S: Metin giriş formu alanını nasıl özelleştiririm?

 A: Metin giriş formu alanını, çağrılırken belirli parametreler sağlayarak özelleştirebilirsiniz.`InsertTextInput`yöntem. Örneğin, form alanı için adı, varsayılan değeri ve maksimum uzunluğu gerektiği gibi ayarlayabilirsiniz.

#### S: Tek bir belgeye birden çok metin giriş formu alanı ekleyebilir miyim?

 C: Evet, tek bir belgeye birden çok metin giriş formu alanı ekleyebilirsiniz. basitçe`InsertTextInput` birden çok form alanı eklemek için farklı adlara ve yapılandırmalara sahip yöntem.

#### S: Kullanıcılar belgedeki metin giriş formu alanıyla nasıl etkileşim kurabilir?

Y: Metin giriş formu alanı belgeye eklendiğinde, kullanıcılar form alanına tıklayıp özel metin girmek için yazmaya başlayabilir. Form alanı, içeriği doğrudan belge içinde düzenlemelerine olanak tanır.
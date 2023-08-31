---
title: Word Belgesine Onay Kutusu Form Alanı Ekle
linktitle: Word Belgesine Onay Kutusu Form Alanı Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine onay kutusu form alanlarının nasıl ekleneceğini öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
Bu kapsamlı eğitimde, Aspose.Words for .NET'i kullanarak bir Word belgesine onay kutusu form alanını nasıl ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, özelleştirilebilir özelliklere sahip onay kutusu form alanlarını belgelerinize ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Onay Kutusu Form Alanı Ekleme
Daha sonra, bir onay kutusu form alanı eklemek için DocumentBuilder sınıfının InsertCheckBox yöntemini kullanın. Bağımsız değişken olarak adı, işaretli durumu, varsayılan durumu ve boyut parametrelerini sağlayın:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## 3. Adım: Belgeyi Kaydedin
Onay kutusu form alanını ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Aspose.Words for .NET kullanarak Onay Kutusu Form Alanı Ekle için Örnek Kaynak Kodu
Aspose.Words for .NET'i kullanarak bir onay kutusu form alanı eklemek için gereken kaynak kodun tamamı aşağıda verilmiştir:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine onay kutusu form alanının nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve verilen kaynak kodunu kullanarak artık belgelerinizi etkileşimli onay kutusu form alanlarıyla geliştirebilirsiniz.

### SSS'ler

#### S: Tek bir belgeye birden çok onay kutusu form alanı ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET'i kullanarak bir Word belgesine gerektiği kadar onay kutusu form alanı ekleyebilirsiniz. Birden fazla etkileşimli onay kutusu eklemek için ekleme işlemini tekrarlamanız yeterlidir.

#### S: Onay kutusu form alanının başlangıç durumunu (işaretli veya işaretsiz) ayarlayabilir miyim?

C: Evet, onay kutusu form alanının başlangıç durumu üzerinde tam kontrole sahipsiniz. Kontrol edilen durum parametresini doğru veya yanlış olarak ayarlayarak, onay kutusunun başlangıçta işaretli mi yoksa işaretsiz mi olduğunu tanımlayabilirsiniz.

#### S: Onay kutusu form alanları PDF gibi diğer dosya formatlarıyla uyumlu mudur?

C: Evet, Aspose.Words for .NET kullanılarak eklenen onay kutusu form alanları, DOCX ve PDF dahil çeşitli dosya formatlarıyla uyumludur. Bu, etkileşimli onay kutularını korurken belgelerinizi farklı formatlarda dışa aktarmanıza olanak tanır.

#### S: Onay kutusu form alanının boyutunu ayarlayabilir miyim?

C: Kesinlikle! InsertCheckBox yöntemindeki size parametresini kullanarak onay kutusu form alanının boyutunu belirtebilirsiniz. Bu, onay kutusunun boyutlarını tasarım tercihlerinize göre kontrol etmenizi sağlar.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mudur?

C: Evet, Aspose.Words for .NET hem masaüstü hem de web uygulamalarına uygun, çok yönlü bir kütüphanedir. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kütüphaneyi zahmetsizce entegre edebilirsiniz.
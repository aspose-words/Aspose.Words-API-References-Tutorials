---
title: Word Belgesinde Onay Kutusu Form Alanı Ekleme
linktitle: Word Belgesinde Onay Kutusu Form Alanı Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerine onay kutusu form alanlarının nasıl ekleneceğini öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine nasıl onay kutusu form alanı ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgelerinize özelleştirilebilir özelliklere sahip onay kutusu form alanları ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Onay Kutusu Form Alanı Ekleyin
Ardından, bir onay kutusu form alanı eklemek için DocumentBuilder sınıfının InsertCheckBox yöntemini kullanın. Adı, kontrol edilen durumu, varsayılan durumu ve boyut parametrelerini bağımsız değişken olarak sağlayın:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## 3. Adım: Belgeyi Kaydedin
Onay kutusu form alanını ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Aspose.Words for .NET kullanarak Onay Kutusu Form Alanı Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir onay kutusu form alanı eklemek için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine nasıl onay kutusu form alanı ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, etkileşimli onay kutusu form alanlarıyla artık belgelerinizi geliştirebilirsiniz.

### SSS

#### S: Tek bir belgeye birden çok onay kutusu form alanı ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET kullanarak bir Word belgesine gerektiği kadar onay kutusu form alanı ekleyebilirsiniz. Birden çok etkileşimli onay kutusu eklemek için ekleme işlemini tekrarlamanız yeterlidir.

#### S: Onay kutusu form alanının başlangıç durumunu (işaretli veya işaretsiz) ayarlayabilir miyim?

C: Evet, onay kutusu form alanının başlangıç durumu üzerinde tam denetime sahipsiniz. Denetlenen durum parametresini doğru veya yanlış olarak ayarlayarak, onay kutusunun başlangıçta işaretli mi yoksa işaretsiz mi olacağını belirleyebilirsiniz.

#### S: Onay kutusu form alanları, PDF gibi diğer dosya formatlarıyla uyumlu mu?

C: Evet, Aspose.Words for .NET kullanılarak eklenen onay kutusu form alanları, DOCX ve PDF dahil olmak üzere çeşitli dosya biçimleriyle uyumludur. Bu, etkileşimli onay kutularını korurken belgelerinizi farklı biçimlerde dışa aktarmanıza olanak tanır.

#### S: Onay kutusu form alanının boyutunu ayarlayabilir miyim?

C: Kesinlikle! InsertCheckBox yöntemindeki size parametresini kullanarak onay kutusu form alanının boyutunu belirleyebilirsiniz. Bu, onay kutusunun boyutlarını tasarım tercihlerinize göre kontrol etmenizi sağlar.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mu?

C: Evet, Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun çok yönlü bir kitaplıktır. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kitaplığı zahmetsizce entegre edebilirsiniz.
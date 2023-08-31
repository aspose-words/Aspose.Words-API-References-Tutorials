---
title: Word Belgesine Kayan Görüntü Ekleme
linktitle: Word Belgesine Kayan Görüntü Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerine kayan görüntüleri nasıl ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-floating-image/
---
Bu kapsamlı örnekte, Aspose.Words for .NET kullanarak bir Word belgesine kayan bir görüntünün nasıl ekleneceğini öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgelerinize özelleştirilebilir konumlandırma ve kaydırma seçenekleriyle resimler ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Bir Kayan Görüntü Ekleyin
Ardından, kayan bir görüntü eklemek için DocumentBuilder sınıfının InsertImage yöntemini kullanın. Görüntü dosyası yolu, göreli yatay ve dikey konum, genişlik, yükseklik ve kaydırma seçeneklerini parametre olarak sağlayın:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## 3. Adım: Belgeyi Kaydedin
Kayan görüntüyü ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Aspose.Words for .NET kullanarak Kayan Görüntü Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak kayan bir görüntü eklemek için eksiksiz kaynak kodu burada:
Kayan resimler, belge metninden bağımsız olarak konumlandırılabilen logolar, resimler veya dekoratif öğeler eklemek gibi çeşitli senaryolar için kullanışlıdır.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Görüntü dosyası yolu ve istenen konumlandırma ve sarma seçenekleri dahil olmak üzere kodu, özel gereksinimlerinize göre ayarlamayı unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine kayan bir görüntünün nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık belgelerinizi görsel olarak çekici ve özelleştirilebilir kayan görüntülerle geliştirebilirsiniz.

### Word belgesine kayan resim eklemek için SSS

#### S: Tek bir belgeye birden çok kayan görüntü ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET'i kullanarak bir Word belgesine istediğiniz kadar kayan görüntü ekleyebilirsiniz. Birden fazla görsel olarak çekici görüntü eklemek için ekleme işlemini tekrarlamanız yeterlidir.

#### S: Kayan görüntü için hangi kaydırma seçenekleri mevcuttur?

Y: Aspose.Words for .NET, kayan görüntüler için Kare, Sıkı, Açık, TopBottom ve Yok gibi çeşitli kaydırma seçenekleri sunar. Bu seçenekler, metnin kayan görüntüyle nasıl etkileşime gireceğini belirler.

#### S: Kayan görüntünün boyutunu ayarlayabilir miyim?

C: Kesinlikle! InsertImage yöntemindeki ilgili parametreleri kullanarak kayan görüntünün genişliğini ve yüksekliğini belirleyebilirsiniz. Bu, tasarım tercihlerinize göre görüntünün boyutlarını kontrol etmenizi sağlar.

#### S: Kayan görüntüyü belgedeki belirli bir öğeye göre konumlandırabilir miyim?

C: Evet, Aspose.Words for .NET yüzen görüntüyü kenar boşluğu, sayfa, paragraf veya tablo gibi belirli öğelere göre konumlandırmanıza izin verir. İstenen yerleşimi elde etmek için uygun göreli yatay ve dikey konum parametrelerini seçebilirsiniz.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mu?

C: Evet, Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun çok yönlü bir kitaplıktır. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kitaplığı zahmetsizce entegre edebilirsiniz.

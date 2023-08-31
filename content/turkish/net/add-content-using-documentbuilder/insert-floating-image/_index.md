---
title: Word Belgesine Kayan Görüntü Ekle
linktitle: Word Belgesine Kayan Görüntü Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine kayan görüntülerin nasıl eklendiğini öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-floating-image/
---
Bu kapsamlı örnekte, Aspose.Words for .NET kullanarak bir Word belgesine kayan bir görüntünün nasıl ekleneceğini öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, özelleştirilebilir konumlandırma ve kaydırma seçeneklerine sahip görselleri belgelerinize ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Kayan Görüntü Ekleme
Daha sonra, kayan bir görüntü eklemek için DocumentBuilder sınıfının InsertImage yöntemini kullanın. Görüntü dosyası yolunu, göreceli yatay ve dikey konumu, genişliği, yüksekliği ve kaydırma seçeneklerini parametre olarak sağlayın:

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
Aspose.Words for .NET'i kullanarak kayan bir görüntü eklemek için tam kaynak kodunu burada bulabilirsiniz:
Kayan görüntüler, belge metninden bağımsız olarak konumlandırılabilen logolar, resimler veya dekoratif öğeler eklemek gibi çeşitli senaryolar için kullanışlıdır.

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

Kodu, görüntü dosyası yolu ve istediğiniz konumlandırma ve sarma seçenekleri de dahil olmak üzere özel gereksinimlerinize göre ayarlamayı unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine kayan görüntünün nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak artık belgelerinizi görsel olarak çekici ve özelleştirilebilir kayan görüntülerle geliştirebilirsiniz.

### Word belgesine kayan resim eklemeye ilişkin SSS

#### S: Tek bir belgeye birden fazla kayan görüntü ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET'i kullanarak bir Word belgesine gerektiği kadar kayan görüntü ekleyebilirsiniz. Birden fazla görsel açıdan çekici görüntü eklemek için ekleme işlemini tekrarlamanız yeterlidir.

#### S: Kayan görüntü için hangi sarma seçenekleri mevcut?

C: Aspose.Words for .NET, kayan görüntüler için Kare, Sıkı, Geçiş, TopBottom ve Yok dahil olmak üzere çeşitli sarma seçenekleri sunar. Bu seçenekler metnin kayan görüntüyle nasıl etkileşime gireceğini belirler.

#### S: Kayan görüntünün boyutunu ayarlayabilir miyim?

C: Kesinlikle! InsertImage yöntemindeki ilgili parametreleri kullanarak kayan görüntünün genişliğini ve yüksekliğini belirleyebilirsiniz. Bu, görüntünün boyutlarını tasarım tercihlerinize göre kontrol etmenize olanak tanır.

#### S: Kayan görüntüyü belgedeki belirli bir öğeye göre konumlandırabilir miyim?

C: Evet, Aspose.Words for .NET, kayan görüntüyü kenar boşluğu, sayfa, paragraf veya tablo gibi belirli öğelere göre konumlandırmanıza olanak tanır. İstenilen yerleşimi elde etmek için uygun göreceli yatay ve dikey konum parametrelerini seçebilirsiniz.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mudur?

C: Evet, Aspose.Words for .NET hem masaüstü hem de web uygulamalarına uygun, çok yönlü bir kütüphanedir. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kütüphaneyi zahmetsizce entegre edebilirsiniz.

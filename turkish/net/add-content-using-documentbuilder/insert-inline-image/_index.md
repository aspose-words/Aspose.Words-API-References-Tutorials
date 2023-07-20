---
title: Word Belgesine Satır İçi Görüntü Ekleme
linktitle: Word Belgesine Satır İçi Görüntü Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerine satır içi görüntüleri nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-inline-image/
---
Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine satır içi görüntülerin nasıl ekleneceğini öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgelerinizin metnine doğrudan resim ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Bir Satır İçi Görüntü Ekleyin
Ardından, belgeye bir satır içi görüntü eklemek için DocumentBuilder sınıfının InsertImage yöntemini kullanın. Görüntü dosyası yolunu bir parametre olarak sağlayın:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 3. Adım: Belgeyi Kaydedin
Satır içi görüntüyü ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Aspose.Words for .NET kullanarak Satır İçi Görüntü Ekleme için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir satır içi görüntü eklemek için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine satır içi görüntülerin nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık belgelerinizin metnine sorunsuz bir şekilde resim ekleyebilirsiniz.

Satır içi görüntüler, doğrudan belgenin akışına çizimler, logolar veya diğer görsel öğeler eklemek gibi çeşitli senaryolar için kullanışlıdır.

### Word belgesine satır içi resim eklemek için SSS

#### S: Word belgesindeki satır içi görüntüleri yeniden boyutlandırabilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak satır içi görüntüleri yeniden boyutlandırabilirsiniz. Görüntüyü ekledikten sonra, görüntüyü temsil eden Shape nesnesinin genişlik ve yükseklik özelliklerini ayarlayarak boyutunu değiştirebilirsiniz.

#### S: Erişilebilirlik amacıyla satır içi resimlere alternatif metin eklemek mümkün müdür?

C: Evet, erişilebilirliği artırmak için satır içi resimlere alternatif metin ekleyebilirsiniz. Aspose.Words for .NET, görsellere alternatif metin eklenmesini destekleyerek ekran okuyucuların ve diğer yardımcı teknolojilerin görsel içeriği görme engelli kullanıcılara tanımlamasına olanak tanır.

#### S: Satır içi görüntülere biçimlendirme veya stiller uygulayabilir miyim?

C: Kesinlikle! Aspose.Words for .NET, satır içi görüntüler için kapsamlı biçimlendirme seçenekleri sunar. Belgenizin görsel tasarımına uyması için görüntülere çeşitli stiller, kenarlıklar, efektler ve diğer biçimlendirme niteliklerini uygulayabilirsiniz.

#### S: Aspose.Words for .NET, bir akıştan veya bayt dizisinden görüntülerin eklenmesini destekliyor mu?

C: Evet, Aspose.Words for .NET kullanarak akışlardan veya bayt dizilerinden satır içi görüntüler ekleyebilirsiniz. Bu, harici kaynaklardan yüklenen görüntülerle veya dinamik olarak oluşturulmuş görüntülerle çalışmanıza olanak tanır.

#### S: Metin içeriğinde belirli konumlara resim ekleyebilir miyim?

C: Evet, Aspose.Words for .NET içindeki DocumentBuilder sınıfı, satır içi görüntülerin ekleme konumu üzerinde hassas kontrol sağlar. Metin içinde görüntünün eklenmesi gereken tam konumu belirtebilirsiniz.
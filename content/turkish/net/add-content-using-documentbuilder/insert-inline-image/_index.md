---
title: Word Belgesine Satır İçi Görüntü Ekleme
linktitle: Word Belgesine Satır İçi Görüntü Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine satır içi görsellerin nasıl eklendiğini öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-inline-image/
---
Bu kapsamlı eğitimde, Aspose.Words for .NET kullanarak satır içi görüntüleri bir Word belgesine nasıl ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, görselleri doğrudan belgelerinizin metnine ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Satır İçi Resim Ekleme
Daha sonra, belgeye satır içi görüntü eklemek için DocumentBuilder sınıfının InsertImage yöntemini kullanın. Görüntü dosyası yolunu parametre olarak belirtin:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 3. Adım: Belgeyi Kaydedin
Satır içi görüntüyü ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Aspose.Words for .NET kullanarak Satır İçi Görüntü Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET'i kullanarak satır içi görüntü eklemek için tam kaynak kodunu burada bulabilirsiniz:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET'i kullanarak satır içi görüntüleri bir Word belgesine nasıl ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak artık belgelerinizin metnine sorunsuz bir şekilde görseller ekleyebilirsiniz.

Satır içi görüntüler, illüstrasyonların, logoların veya diğer görsel öğelerin doğrudan belge akışına eklenmesi gibi çeşitli senaryolar için kullanışlıdır.

### Word belgesine satır içi resim eklemeyle ilgili SSS

#### S: Word belgesindeki satır içi görüntüleri yeniden boyutlandırabilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak satır içi görselleri yeniden boyutlandırabilirsiniz. Görüntüyü ekledikten sonra, görüntüyü temsil eden Shape nesnesinin genişlik ve yükseklik özelliklerini ayarlayarak boyutunu değiştirebilirsiniz.

#### S: Erişilebilirlik amacıyla satır içi görsellere alternatif metin eklemek mümkün müdür?

C: Evet, erişilebilirliği artırmak için satır içi görsellere alternatif metin ekleyebilirsiniz. Aspose.Words for .NET, görsellere alternatif metin eklenmesini destekleyerek ekran okuyucuların ve diğer yardımcı teknolojilerin görsel içeriğini görme engelli kullanıcılara tanımlamasına olanak tanır.

#### S: Satır içi görsellere format veya stil uygulayabilir miyim?

C: Kesinlikle! Aspose.Words for .NET, satır içi görüntüler için kapsamlı formatlama seçenekleri sunar. Belgenizin görsel tasarımına uyacak şekilde görüntülere çeşitli stiller, kenarlıklar, efektler ve diğer biçimlendirme nitelikleri uygulayabilirsiniz.

#### S: Aspose.Words for .NET bir akıştan veya bayt dizisinden görüntü eklemeyi destekliyor mu?

C: Evet, Aspose.Words for .NET'i kullanarak akışlardan veya bayt dizilerinden satır içi görüntüler ekleyebilirsiniz. Bu, harici kaynaklardan yüklenen görüntülerle veya dinamik olarak oluşturulan görüntülerle çalışmanıza olanak tanır.

#### S: Metin içeriğinin belirli konumlarına resim ekleyebilir miyim?

C: Evet, Aspose.Words for .NET'teki DocumentBuilder sınıfı, satır içi görüntülerin ekleme konumu üzerinde hassas kontrol sağlar. Metin içinde görüntünün eklenmesi gereken tam konumu belirtebilirsiniz.
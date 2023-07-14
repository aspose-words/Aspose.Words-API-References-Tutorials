---
title: Yazar Alanı Ekle
linktitle: Yazar Alanı Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Word belgelerinize YAZAR alanı eklemeyi öğrenin. Belgelerinizi kişiselleştirmek için yazarın adını belirtin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-author-field/
---


Aspose.Words for .NET'in "YAZAR alanı ekle" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturarak ve ilk paragrafı getirerek başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3. Adım: YAZAR alanını girin

 biz kullanıyoruz`AppendField()` paragrafa YAZAR alanı ekleme yöntemi.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Daha sonra alanın konfigürasyonunu yaparız.`AuthorName` yazarın adını belirtmek için özellik.

```csharp
field. AuthorName = "Test1";
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile YAZAR alanı eklemek için kaynak kodu örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// YAZAR alanını girin.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

Bu örnekte yeni bir belge oluşturduk, YAZAR alanı ekledik, yazar adını yapılandırdık ve belgeyi belirtilen dosya adıyla kaydettik.

Bu, Aspose.Words for .NET ile "YAZAR Alanı Girin" özelliğinin kullanımına ilişkin kılavuzumuzu sonlandırıyor.

### SSS

#### S: Aspose.Words'te yazar alanı nedir?

A: Aspose.Words'teki Yazar Alanı, yazarın adını bir Word belgesine otomatik olarak ekleyen ve güncelleyen özel bir alandır. Genellikle belgeyi kimin oluşturduğunu veya değiştirdiğini belirtmek için kullanılır.

#### S: Bir Word belgesindeki yazar alanı Aspose.Words ile nasıl güncellenir?

C: Bir Word belgesindeki yazar alanı, geçerli yazarın adını yansıtacak şekilde güncellenebilir. Bunun için Document sınıfında bulunan UpdateFields yöntemini kullanabilirsiniz. Bu yöntem, yazar alanı da dahil olmak üzere belgedeki tüm alanları güncelleyecektir.

#### S: Bir Word belgesinde yazar alanının biçimini özelleştirmek mümkün müdür?

C: Evet, bir Word belgesinde yazar alanının biçimini özelleştirmek mümkündür. Varsayılan olarak, yazar alanı yalnızca yazarın adını görüntüler. Ancak, Aspose.Words'te bulunan biçimlendirme seçeneklerini kullanarak değişiklik tarihi ve saati gibi ek bilgiler ekleyebilirsiniz.

#### S: Yazar alanı, yazarın adında sonradan yapılan değişikliklere duyarlı mı?

C: Evet, yazar alanı, yazar adında sonradan yapılacak değişikliklere karşı hassastır. Belge özelliklerinde yazar adını değiştirirseniz, belge alanları güncellenirken yazar alanı otomatik olarak yeni adla güncellenir.
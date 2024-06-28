---
title: Yazar Alanı Ekle
linktitle: Yazar Alanı Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinize YAZAR alanını nasıl ekleyeceğinizi öğrenin. Belgelerinizi kişiselleştirmek için yazarın adını belirtin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-author-field/
---


Aşağıda Aspose.Words for .NET'in "YAZAR alanı ekle" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturup ilk paragrafı getirerek başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3. Adım: AUTHOR alanını ekleyin

 biz kullanıyoruz`AppendField()` Paragrafa bir YAZAR alanı ekleme yöntemi.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Daha sonra alanın ayarlarını yapılandırıyoruz.`AuthorName` Yazarın adını belirtme özelliği.

```csharp
field. AuthorName = "Test1";
```

 Son olarak şunu diyoruz:`Update()` Alanı güncelleme yöntemi.

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

// YAZAR alanını ekleyin.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

Bu örnekte yeni bir belge oluşturduk, bir YAZAR alanı ekledik, yazar adını yapılandırdık ve belgeyi belirtilen dosya adıyla kaydettik.

Bu, Aspose.Words for .NET ile "YAZAR Alanı Ekle" özelliğinin kullanımına ilişkin kılavuzumuzu tamamlıyor.

### SSS'ler

#### S: Aspose.Words'te yazar alanı nedir?

C: Aspose.Words'teki Yazar Alanı, yazarın adını bir Word belgesine otomatik olarak ekleyen ve güncelleyen özel bir alandır. Genellikle belgeyi kimin oluşturduğunu veya değiştirdiğini belirtmek için kullanılır.

#### S: Aspose.Words ile bir Word belgesindeki yazar alanı nasıl güncellenir?

C: Bir Word belgesindeki yazar alanı, geçerli yazarın adını yansıtacak şekilde güncelleştirilebilir. Bunun için Document sınıfında bulunan UpdateFields metodunu kullanabilirsiniz. Bu yöntem, yazar alanı da dahil olmak üzere belgedeki tüm alanları güncelleyecektir.

#### S: Bir Word belgesindeki yazar alanının biçimini özelleştirmek mümkün müdür?

C: Evet, bir Word belgesindeki yazar alanının biçimini özelleştirmek mümkündür. Varsayılan olarak yazar alanı yalnızca yazarın adını görüntüler. Ancak Aspose.Words'te bulunan biçimlendirme seçeneklerini kullanarak değişiklik tarihi ve saati gibi ek bilgiler ekleyebilirsiniz.

#### S: Yazar alanı, yazarın adında daha sonra yapılan değişikliklere duyarlı mıdır?

C: Evet, yazar alanı, yazar adında daha sonra yapılan değişikliklere duyarlıdır. Belge özelliklerinde yazar adını değiştirirseniz, belge alanları güncellenirken yazar alanı yeni adla otomatik olarak güncellenecektir.
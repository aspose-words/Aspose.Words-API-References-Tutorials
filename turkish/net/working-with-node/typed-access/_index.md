---
title: Yazılı Erişim
linktitle: Yazılı Erişim
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te tabloları işlemek için yazılı erişimi nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-node/typed-access/
---

Yazılı Erişim özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını gösteren aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce, Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Bu, Aspose.Words kitaplığının içe aktarılmasını ve gerekli ad alanlarının kaynak dosyanıza eklenmesini içerir.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 2. Adım: Yeni bir belge oluşturun
 Bu adımda, kullanarak yeni bir belge oluşturacağız.`Document` sınıf.

```csharp
Document doc = new Document();
```

## 3. Adım: Bölüme ve gövdeye erişin
Belge içerisinde yer alan tablolara ulaşmak için öncelikle belgenin ilgili bölümüne ve gövdesine erişmemiz gerekmektedir.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## 4. Adım: Tablolara hızlı ve yazılı erişim
Artık belgenin gövdesine sahip olduğumuza göre, gövdede bulunan tüm tablolara erişmek için hızlı ve yazılı erişimi kullanabiliriz.

```csharp
TableCollection tables = body.Tables;
```

## 5. Adım: Tablolara göz atın
 kullanarak`foreach` döngü, tüm tablolar arasında döngü yapabilir ve her tablo üzerinde belirli işlemler gerçekleştirebiliriz.

```csharp
foreach(Table table in tables)
{
     // Tablonun ilk satırına hızlı ve yazılı erişim.
     table.FirstRow?.Remove();

     // Tablonun son satırına hızlı ve yazılı erişim.
     table.LastRow?.Remove();
}
```

Bu örnekte, Aspose.Words tarafından sağlanan hızlı ve yazılı erişimi kullanarak her tablonun ilk ve son satırını siliyoruz.

### Aspose.Words for .NET ile Yazılı Erişim için Örnek Kaynak Kodu

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	// Gövdede bulunan tüm Tablo alt düğümlerine hızlı erişim.
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		// Tablonun ilk satırına hızlı erişim.
		table.FirstRow?.Remove();

		// Tablonun son satırına hızlı erişim.
		table.LastRow?.Remove();
	}
            
```

Bu, Aspose.Words for .NET ile tablolara yazılı erişim için eksiksiz bir örnek koddur. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun.

---

---
title: Aspose.Words for Java'da Belgeleri Metin Dosyaları Olarak Kaydetme
linktitle: Belgeleri Metin Dosyaları Olarak Kaydetme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da belgeleri metin dosyaları olarak nasıl kaydedeceğinizi öğrenin. Java kodu örneklerini içeren adım adım kılavuzumuzu izleyin.
type: docs
weight: 24
url: /tr/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Aspose.Words for Java'da Belgeleri Metin Dosyaları Olarak Kaydetmeye Giriş

Bu eğitimde Aspose.Words for Java kütüphanesini kullanarak belgeleri metin dosyaları olarak nasıl kaydedeceğimizi inceleyeceğiz. Aspose.Words, Word belgeleriyle çalışmak için güçlü bir Java API'sidir ve belgeleri düz metin de dahil olmak üzere farklı formatlarda kaydetmek için çeşitli seçenekler sunar. Bunu başarmak için gereken adımları ele alacağız ve yol boyunca örnek Java kodu sunacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Words for Java kütüphanesi projenize entegre edilmiştir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).
- Java programlamanın temel bilgisi.

## 1. Adım: Bir Belge Oluşturun

Bir belgeyi metin dosyası olarak kaydetmek için öncelikle Aspose.Words'ü kullanarak bir belge oluşturmamız gerekir. Biraz içeriğe sahip bir belge oluşturmak için basit bir Java kod pasajı:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

Bu kodda yeni bir belge oluşturuyoruz ve ona farklı dillerdeki metinler de dahil olmak üzere bazı metinler ekliyoruz.

## 2. Adım: Metin Kaydetme Seçeneklerini Tanımlayın

Daha sonra belgenin metin dosyası olarak nasıl kaydedileceğini belirten metin kaydetme seçeneklerini tanımlamamız gerekiyor. Bidi işaretleri ekleme, liste girintisi ve daha fazlası gibi çeşitli ayarları yapılandırabiliriz. İki örneğe bakalım:

### Örnek 1: Bidi İşaretlerini Ekleme

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 Bu örnekte, bir oluşturuyoruz`TxtSaveOptions` nesneyi ayarlayın ve`AddBidiMarks`mülkiyet`true` metin çıktısına bidi işaretlerini dahil etmek için.

### Örnek 2: Liste Girintisi için Sekme Karakterini Kullanma

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Burada, liste girintisi için 1 sayısıyla bir sekme karakteri kullanacak şekilde kaydetme seçeneklerini yapılandırıyoruz.

## 3. Adım: Belgeyi Metin Olarak Kaydetme

Artık metin kaydetme seçeneklerini tanımladığımıza göre belgeyi metin dosyası olarak kaydedebiliriz. Aşağıdaki kod bunun nasıl yapılacağını gösterir:

```java
doc.save("output.txt", saveOptions);
```

 Yer değiştirmek`"output.txt"` metin dosyasını kaydetmek istediğiniz istenen dosya yolu ile.

## Aspose.Words for Java'da Belgeleri Metin Dosyaları Olarak Kaydetmek İçin Tam Kaynak Kodu

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Üç düzeyde girintiye sahip bir liste oluşturun.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Üç düzeyde girintiye sahip bir liste oluşturun.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Çözüm

Bu eğitimde Aspose.Words for Java'da belgeleri metin dosyaları olarak nasıl kaydedeceğimizi öğrendik. Belge oluşturma, metin kaydetme seçeneklerini tanımlama ve belgeyi metin biçiminde kaydetme adımlarını ele aldık. Aspose.Words, belgeleri kaydetme konusunda kapsamlı esneklik sağlayarak çıktıyı özel gereksinimlerinize göre uyarlamanıza olanak tanır.

## SSS'ler

### Metin çıktısına bidi işaretlerini nasıl eklerim?

 Metin çıktısına bidi işaretleri eklemek için`AddBidiMarks` mülkiyeti`TxtSaveOptions` ile`true`. Örneğin:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Liste girinti karakterini özelleştirebilir miyim?

 Evet, liste girinti karakterini yapılandırarak özelleştirebilirsiniz.`ListIndentation` mülkiyeti`TxtSaveOptions`. Örneğin, liste girintisi amacıyla bir sekme karakteri kullanmak için aşağıdakileri yapabilirsiniz:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words for Java çok dilli metinleri işlemeye uygun mu?

Evet, Aspose.Words for Java çok dilli metinlerin işlenmesi için uygundur. Çeşitli dilleri ve karakter kodlamalarını desteklediğinden, farklı dillerdeki belgelerle çalışmak için çok yönlü bir seçimdir.

### Aspose.Words for Java için daha fazla belge ve kaynağa nasıl erişebilirim?

 Aspose.Words for Java ile ilgili kapsamlı belgeleri ve kaynakları Aspose belgelendirme web sitesinde bulabilirsiniz:[Aspose.Words for Java Belgelendirmesi](https://reference.aspose.com/words/java/).

### Aspose.Words for Java'yı nereden indirebilirim?

 Aspose.Words for Java kütüphanesini Aspose web sitesinden indirebilirsiniz:[Aspose.Words for Java'yı indirin](https://releases.aspose.com/words/java/).
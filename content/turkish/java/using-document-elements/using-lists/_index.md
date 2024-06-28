---
title: Aspose.Words for Java'da Listeleri Kullanma
linktitle: Listeleri Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Bu adım adım eğitimle Aspose.Words for Java'da listeleri kullanmayı öğrenin. Belgelerinizi etkili bir şekilde düzenleyin ve biçimlendirin.
type: docs
weight: 18
url: /tr/java/using-document-elements/using-lists/
---

Bu kapsamlı eğitimde, Microsoft Word belgeleriyle programlı olarak çalışmak için güçlü bir API olan Aspose.Words for Java'da listelerin nasıl etkili bir şekilde kullanılacağını keşfedeceğiz. Listeler, belgelerinizdeki içeriği yapılandırmak ve düzenlemek için gereklidir. Listelerle çalışmanın iki önemli yönünü ele alacağız: her bölümde listeleri yeniden başlatmak ve liste düzeylerini belirlemek. Hadi dalalım!

## Aspose.Words for Java'ya Giriş

Listelerle çalışmaya başlamadan önce Aspose.Words for Java'yı tanıyalım. Bu API, geliştiricilere Java ortamında Word belgeleri oluşturma, değiştirme ve işleme araçları sağlar. Basit belge oluşturmadan karmaşık biçimlendirme ve içerik yönetimine kadar çeşitli görevler için çok yönlü bir çözümdür.

### Ortamınızı Kurma

 Başlamak için, geliştirme ortamınızda Aspose.Words for Java'nın kurulu ve kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/words/java/). 

## Listelerin Her Bölümde Yeniden Başlatılması

Çoğu senaryoda belgenizin her bölümünde listeleri yeniden başlatmanız gerekebilir. Bu, raporlar, kılavuzlar veya akademik makaleler gibi birden fazla bölümden oluşan yapılandırılmış belgeler oluşturmak için yararlı olabilir.

Aspose.Words for Java kullanarak bunu nasıl başaracağınıza ilişkin adım adım kılavuzu burada bulabilirsiniz:

### Belgenizi Başlatın: 
Yeni bir belge nesnesi oluşturarak başlayın.

```java
Document doc = new Document();
```

### Numaralı Liste Ekle: 
Belgenize numaralı bir liste ekleyin. Varsayılan numaralandırma stilini kullanacağız.

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### Liste Ayarlarını Yapılandırın: 
\Listenin her bölümde yeniden başlatılmasını etkinleştirin.

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### DocumentBuilder Kurulumu: 
Belgenize içerik eklemek için bir DocumentBuilder oluşturun.

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### Liste Öğelerini Ekle: 
Belgenize liste öğeleri eklemek için bir döngü kullanın. 15. maddeden sonra bölüm sonu ekleyeceğiz.

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### Belgenizi Kaydedin: 
Belgeyi istediğiniz seçeneklerle kaydedin.

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

Bu adımları izleyerek, her bölümde yeniden başlayan listeler içeren, net ve düzenli içerik yapısını koruyan belgeler oluşturabilirsiniz.

## Liste Düzeylerini Belirleme

Aspose.Words for Java, liste düzeylerini belirlemenize olanak tanır; bu, özellikle belgenizde farklı liste formatlarına ihtiyaç duyduğunuzda kullanışlıdır. Bunu nasıl yapacağımızı inceleyelim:

### Belgenizi Başlatın: 
Yeni bir belge nesnesi oluşturun.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Numaralı Liste Oluşturun: 
Microsoft Word'den numaralandırılmış bir liste şablonu uygulayın.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### Liste Seviyelerini Belirleyin: 
Farklı liste düzeylerini yineleyin ve içerik ekleyin.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Madde İşaretli Liste Oluşturun: 
Şimdi madde işaretli bir liste oluşturalım.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### Madde İşaretli Liste Seviyelerini Belirleyin: 
Numaralandırılmış listeye benzer şekilde düzeyleri belirtin ve içerik ekleyin.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Liste Biçimlendirmesini Durdur: 
Liste biçimlendirmesini durdurmak için listeyi null olarak ayarlayın.

```java
builder.getListFormat().setList(null);
```

### Belgenizi Kaydedin: 
Belgeyi kaydedin.

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

Bu adımları izleyerek, belgelerinizdeki listelerin biçimlendirmesini kontrol etmenize olanak tanıyan özel liste düzeylerine sahip belgeler oluşturabilirsiniz.

## Kaynak Kodunu Tamamlayın
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        // IsRestartAtEachSection yalnızca uyumluluk OoxmlComplianceCore.Ecma376'dan yüksekse yazılacaktır.
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Microsoft Word liste şablonlarından birine dayalı numaralandırılmış bir liste oluşturun.
        //ve bunu belge oluşturucunun geçerli paragrafına uygulayın.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // Bu listede dokuz seviye var, hepsini deneyelim.
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Microsoft Word liste şablonlarından birini temel alan madde işaretli bir liste oluşturun.
        //ve bunu belge oluşturucunun geçerli paragrafına uygulayın.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Bu, liste biçimlendirmesini durdurmanın bir yoludur.
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Şablona dayalı bir liste oluşturun.
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // İlk listeyi yeniden kullanmak için orijinal liste formatının bir kopyasını oluşturarak numaralandırmayı yeniden başlatmamız gerekir.
        List list2 = doc.getLists().addCopy(list1);
        // Yeni listeyi, yeni bir başlangıç numarası ayarlamak da dahil olmak üzere herhangi bir şekilde değiştirebiliriz.
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## Çözüm

Tebrikler! Aspose.Words for Java'da listelerle etkili bir şekilde nasıl çalışılacağını öğrendiniz. Listeler, belgelerinizdeki içeriği düzenlemek ve sunmak için çok önemlidir. Her bölümde listeleri yeniden başlatmanız veya liste seviyelerini belirtmeniz gerekip gerekmediğini Aspose.Words for Java, profesyonel görünümlü belgeler oluşturmak için ihtiyacınız olan araçları sağlar.

Artık belge oluşturma ve biçimlendirme görevlerinizi geliştirmek için bu özellikleri güvenle kullanabilirsiniz. Herhangi bir sorunuz varsa veya daha fazla yardıma ihtiyacınız varsa, bizimle iletişime geçmekten çekinmeyin.[Topluluk forumu aspose](https://forum.aspose.com/) destek için.

## SSS

### Aspose.Words for Java'yı nasıl yüklerim?
 Aspose.Words for Java'yı şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/java/) ve belgelerdeki kurulum talimatlarını izleyin.

### Listelerin numaralandırma biçimini özelleştirebilir miyim?
Evet, Aspose.Words for Java, liste numaralandırma formatlarını özelleştirmek için kapsamlı seçenekler sunar. Ayrıntılar için API belgelerine başvurabilirsiniz.

### Aspose.Words for Java en son Word belge standartlarıyla uyumlu mu?
Evet, Aspose.Words for Java'yı ISO 29500 de dahil olmak üzere çeşitli Word belge standartlarıyla uyumlu olacak şekilde yapılandırabilirsiniz.

### Aspose.Words for Java'yı kullanarak tablolar ve görseller içeren karmaşık belgeler oluşturabilir miyim?
Kesinlikle! Aspose.Words for Java; tablolar, resimler ve daha fazlasını içeren gelişmiş belge formatını destekler. Örnekler için belgelere bakın.

### Aspose.Words for Java için nereden geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

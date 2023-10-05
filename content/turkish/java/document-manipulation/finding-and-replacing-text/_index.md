---
title: Aspose.Words for Java'da Metin Bulma ve Değiştirme
linktitle: Metni Bulma ve Değiştirme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java ile Word belgelerindeki metni nasıl bulacağınızı ve değiştireceğinizi öğrenin. Kod örnekleri içeren adım adım kılavuz. Java belge işleme becerilerinizi geliştirin.
type: docs
weight: 15
url: /tr/java/document-manipulation/finding-and-replacing-text/
---

## Aspose.Words for Java'da Metin Bulma ve Değiştirmeye Giriş

Aspose.Words for Java, Word belgeleriyle programlı olarak çalışmanıza olanak tanıyan güçlü bir Java API'sidir. Word belgeleriyle uğraşırken en sık yapılan görevlerden biri metni bulmak ve değiştirmektir. İster şablonlardaki yer tutucuları güncellemeniz, ister daha karmaşık metin düzenlemeleri yapmanız gerekiyorsa Aspose.Words for Java, hedeflerinize verimli bir şekilde ulaşmanıza yardımcı olabilir.

## Önkoşullar

Metni bulma ve değiştirmeyle ilgili ayrıntılara dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

- Java Geliştirme Ortamı
- Aspose.Words for Java kütüphanesi
- Çalışmak için örnek bir Word belgesi

 Aspose.Words for Java kütüphanesini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/java/).

## Basit Metni Bulma ve Değiştirme

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// DocumentBuilder'ı oluşturun
DocumentBuilder builder = new DocumentBuilder(doc);

// Metni bul ve değiştir
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

 Bu örnekte bir Word belgesi yüklüyoruz, bir`DocumentBuilder` ve şunu kullanın:`replace` Belgede "eski metin"i bulma ve "yeni metin" ile değiştirme yöntemi.

## Normal İfadeleri Kullanma

Düzenli ifadeler, metin arama ve değiştirme için güçlü kalıp eşleştirme yetenekleri sağlar. Aspose.Words for Java, daha gelişmiş bulma ve değiştirme işlemleri için normal ifadeleri destekler.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// DocumentBuilder'ı oluşturun
DocumentBuilder builder = new DocumentBuilder(doc);

// Metni bulmak ve değiştirmek için normal ifadeleri kullanma
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu örnekte, belgedeki metni bulmak ve değiştirmek için normal ifade modelini kullanıyoruz.

## Alanların İçindeki Metni Yoksayma

Aspose.Words'ü, bulma ve değiştirme işlemlerini gerçekleştirirken alanların içindeki metni yok sayacak şekilde yapılandırabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// FindReplaceOptions örneği oluşturun ve IgnoreFields'ı true olarak ayarlayın
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Metni değiştirirken seçenekleri kullan
doc.getRange().replace("text-to-replace", "new-text", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, birleştirme alanları gibi alanların içindeki metnin değiştirilmesini engellemek istediğinizde kullanışlıdır.

## Düzeltmelerin İçindeki Metni Yoksayma

Aspose.Words'ü bulma ve değiştirme işlemleri sırasında revizyonların içindeki metni yok sayacak şekilde yapılandırabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// FindReplaceOptions örneği oluşturun ve IgnoreDeleted'ı true olarak ayarlayın
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Metni değiştirirken seçenekleri kullan
doc.getRange().replace("text-to-replace", "new-text", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, izlenen değişikliklerde silinmek üzere işaretlenen metnin değiştirilmesini hariç tutmanıza olanak tanır.

## Revizyon Ekleme İçindeki Metni Yoksayma

Aspose.Words'ü bulma ve değiştirme işlemleri sırasında revizyon eklemelerin içindeki metni yok sayacak şekilde yapılandırabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// FindReplaceOptions örneği oluşturun ve IgnoreInserted'ı true olarak ayarlayın
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Metni değiştirirken seçenekleri kullan
doc.getRange().replace("text-to-replace", "new-text", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, izlenen değişikliklere eklenmiş olarak işaretlenen metnin değiştirilmesini hariç tutmanıza olanak tanır.

## Metni HTML ile Değiştirmek

Metni HTML içeriğiyle değiştirmek için Aspose.Words for Java'yı kullanabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// Özel değiştirme geri çağrısıyla FindReplaceOptions örneği oluşturma
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Metni değiştirirken seçenekleri kullan
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

 Bu örnekte özel bir tane kullanıyoruz`ReplaceWithHtmlEvaluator` metni HTML içeriğiyle değiştirmek için.

## Üstbilgi ve Altbilgilerdeki Metni Değiştirme

Word belgenizin üstbilgileri ve altbilgileri içindeki metni bulabilir ve değiştirebilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// Üstbilgi ve altbilgi koleksiyonunu edinin
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Metni değiştirmek istediğiniz üst bilgi veya alt bilgi türünü seçin (örneğin, HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// FindReplaceOptions örneği oluşturun ve bunu alt bilgi aralığına uygulayın
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, özellikle üstbilgi ve altbilgilerde metin değişiklikleri yapmanıza olanak tanır.

## Üstbilgi ve Altbilgi Sıralarındaki Değişiklikler Gösteriliyor

Belgenizdeki üstbilgi ve altbilgi sıralarındaki değişiklikleri göstermek için Aspose.Words'ü kullanabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// İlk bölümü edinin
Section firstPageSection = doc.getFirstSection();

// FindReplaceOptions örneği oluşturun ve bunu belgenin aralığına uygulayın
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Üstbilgi ve altbilgi sıralarını etkileyen metni değiştirin
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, belgenizdeki üstbilgi ve altbilgi sıralarıyla ilgili değişiklikleri görselleştirmenize olanak tanır.

## Metni Alanlarla Değiştirmek

Aspose.Words for Java'yı kullanarak metni alanlarla değiştirebilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// FindReplaceOptions örneği oluşturun ve alanlar için özel bir değiştirme geri çağrısı ayarlayın
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Metni değiştirirken seçenekleri kullan
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

 Bu örnekte metni alanlarla değiştiriyoruz ve alan türünü belirtiyoruz (örn.`FieldType.FIELD_MERGE_FIELD`).

## Bir Değerlendiriciyle Değiştirme

Değiştirilen metni dinamik olarak belirlemek için özel bir değerlendirici kullanabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// FindReplaceOptions örneği oluşturun ve özel bir değiştirme geri çağrısı ayarlayın
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Metni değiştirirken seçenekleri kullan
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu örnekte özel bir değerlendirici kullanıyoruz (`MyReplaceEvaluator`) metni değiştirmek için.

## Regex ile değiştirme

Aspose.Words for Java, normal ifadeleri kullanarak metni değiştirmenize olanak tanır.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// Metni bulmak ve değiştirmek için normal ifadeleri kullanma
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu örnekte, belgedeki metni bulmak ve değiştirmek için normal ifade modelini kullanıyoruz.

## Değiştirme Modelleri İçinde Tanıma ve Değiştirmeler

Aspose.Words for Java'yı kullanarak değiştirme kalıplarını tanıyabilir ve değişiklik yapabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

//UseSubstitutions'ın true olarak ayarlandığı bir FindReplaceOptions örneği oluşturun
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Metni bir desenle değiştirirken seçenekleri kullanın
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, daha gelişmiş değiştirmeler için değiştirme modelleri dahilinde değişiklik yapmanıza olanak tanır.

## Bir String ile Değiştirmek

Aspose.Words for Java'yı kullanarak metni basit bir dizeyle değiştirebilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// Metni bir dizeyle değiştir
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu örnekte, belgedeki "değiştirilecek metin"i "yeni dize" ile değiştiriyoruz.

## Eski Sırayı Kullanma

Bul ve değiştir işlemlerini gerçekleştirirken eski sırayı kullanabilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// FindReplaceOptions örneği oluşturun ve UseLegacyOrder'ı true olarak ayarlayın
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Metni değiştirirken seçenekleri kullan
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, bulma ve değiştirme işlemleri için eski sırayı kullanmanıza olanak tanır.

## Tablodaki Metni Değiştirme

Word belgenizdeki tabloların içindeki metni bulabilir ve değiştirebilirsiniz.

```java
// Belgeyi yükleyin
Document doc = new Document("your-document.docx");

// Belirli bir tablo alın (örneğin, ilk tablo)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Tablodaki metni değiştirmek için FindReplaceOptions'ı kullanın
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Değiştirilen belgeyi kaydet
doc.save("modified-document.docx");
```

Bu, özellikle tablolar içinde metin değişiklikleri yapmanıza olanak tanır.

## Çözüm

Aspose.Words for Java, Word belgeleri içindeki metni bulmak ve değiştirmek için kapsamlı yetenekler sağlar. Normal ifadeler, alan manipülasyonları veya özel değerlendiriciler kullanarak basit metin değişiklikleri veya daha gelişmiş işlemler gerçekleştirmeniz gerekip gerekmediğini, Aspose.Words for Java ihtiyacınızı karşılar. Bu güçlü Java kütüphanesinin tüm potansiyelinden yararlanmak için Aspose tarafından sağlanan kapsamlı belgeleri ve örnekleri incelediğinizden emin olun.

## SSS'ler

### Aspose.Words for Java'yı nasıl indirebilirim?

 Aspose.Words for Java'yı web sitesinden şu adresi ziyaret ederek indirebilirsiniz:[bu bağlantı](https://releases.aspose.com/words/java/).

### Metin değişimi için normal ifadeleri kullanabilir miyim?

Evet, Aspose.Words for Java'da metin değişimi için normal ifadeleri kullanabilirsiniz. Bu, daha gelişmiş ve esnek bulma ve değiştirme işlemlerini gerçekleştirmenize olanak tanır.

### Değiştirme sırasında alanların içindeki metni nasıl yok sayabilirim?

 Değiştirme sırasında alanların içindeki metni yok saymak için`IgnoreFields` mülkiyeti`FindReplaceOptions` ile`true`Bu, birleştirme alanları gibi alanların içindeki metnin değiştirme işleminin dışında tutulmasını sağlar.

### Üstbilgi ve altbilgilerin içindeki metni değiştirebilir miyim?

 Evet, Word belgenizin üstbilgileri ve altbilgileri içindeki metni değiştirebilirsiniz. Sadece uygun üstbilgi veya altbilgiye erişin ve`replace` istenilen yöntemle`FindReplaceOptions`.

### UseLegacyOrder seçeneği ne işe yarar?

`UseLegacyOrder` seçenek`FindReplaceOptions` Bulma ve değiştirme işlemlerini gerçekleştirirken eski sırayı kullanmanıza olanak tanır. Bu, eski sipariş davranışının istendiği belirli senaryolarda yararlı olabilir.
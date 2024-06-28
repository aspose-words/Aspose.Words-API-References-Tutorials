---
title: Aspose.Words for Java'da OLE Nesnelerini ve ActiveX Kontrollerini Kullanma
linktitle: OLE Nesnelerini ve ActiveX Denetimlerini Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da OLE nesnelerini ve ActiveX kontrollerini kullanmayı öğrenin. Kolayca etkileşimli belgeler oluşturun. Şimdi başla!
type: docs
weight: 21
url: /tr/java/using-document-elements/using-ole-objects-and-activex/
---
Bu eğitimde Aspose.Words for Java'da OLE (Nesne Bağlama ve Gömme) nesneleri ve ActiveX kontrolleriyle nasıl çalışılacağını keşfedeceğiz. OLE nesneleri ve ActiveX kontrolleri, elektronik tablolar, multimedya dosyaları veya etkileşimli kontroller gibi harici içerikleri gömerek veya bağlayarak belgelerinizi geliştirmenize olanak tanıyan güçlü araçlardır. Kod örneklerini incelerken bu adımları takip edin ve bu özellikleri etkili bir şekilde nasıl kullanabileceğimizi öğrenin.

### Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Words for Java : Java projenizde Aspose.Words kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).

2. Java Geliştirme Ortamı : Sisteminizde çalışan bir Java geliştirme ortamının kurulu olması gerekir.

### OLE Nesnesi Ekleme

Bir Word belgesine bir OLE nesnesi ekleyerek başlayalım. Basit bir Word belgesi oluşturacağız ve ardından bir web sayfasını temsil eden bir OLE nesnesi ekleyeceğiz.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

Bu kodda yeni bir belge oluşturup Aspose web sitesini görüntüleyen bir OLE nesnesi ekliyoruz. URL'yi istediğiniz içerikle değiştirebilirsiniz.

### OlePackage ile OLE Nesnesi Ekleme

Şimdi OlePackage kullanarak OLE nesnesinin nasıl ekleneceğini inceleyelim. Bu, harici dosyaları belgenize OLE nesneleri olarak yerleştirmenize olanak tanır.

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

Bu örnekte, OlePackage kullanarak bir OLE nesnesi ekliyoruz ve böylece harici dosyaları gömülü nesneler olarak eklemenize olanak sağlıyoruz.

### OLE Nesnesini Simge Olarak Ekleme

Şimdi bir OLE nesnesinin simge olarak nasıl eklendiğini görelim. Bu, gömülü bir dosyayı temsil eden bir simgeyi görüntülemek istediğinizde kullanışlıdır.

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

Bu kodda, gömülü içeriğin görsel olarak daha çekici bir temsilini sağlayan bir simge olarak bir OLE nesnesi ekliyoruz.

### ActiveX Denetimi Özelliklerini Okuma

Şimdi odağımızı ActiveX kontrollerine kaydıralım. Bir Word belgesindeki ActiveX denetimlerinin özelliklerinin nasıl okunacağını öğreneceğiz.

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

Bu kodda, bir Word belgesindeki şekilleri yineliyoruz, ActiveX kontrollerini belirliyoruz ve bunların özelliklerini alıyoruz.

### Çözüm

Tebrikler! Aspose.Words for Java'da OLE nesneleri ve ActiveX kontrolleriyle nasıl çalışılacağını öğrendiniz. Bu özellikler, dinamik ve etkileşimli belgeler oluşturmaya yönelik bir olasılıklar dünyasının kapılarını açar.

### SSS

### Word belgesindeki OLE nesnelerinin amacı nedir? 
   - OLE nesneleri, dosyalar veya web sayfaları gibi harici içeriği bir Word belgesine yerleştirmenize veya bağlamanıza olanak tanır.

### Belgemdeki OLE nesnelerinin görünümünü özelleştirebilir miyim? 
   - Evet, simgelerin ve dosya adlarının ayarlanması da dahil olmak üzere OLE nesnelerinin görünümünü özelleştirebilirsiniz.

### ActiveX denetimleri nedir ve belgelerimi nasıl geliştirebilirler? 
   - ActiveX kontrolleri, Word belgelerinize form kontrolleri veya multimedya oynatıcılar gibi işlevler ekleyebilen etkileşimli öğelerdir.

### Aspose.Words for Java kurumsal düzeyde belge otomasyonuna uygun mu? 
   - Evet, Aspose.Words for Java, Java uygulamalarında belge oluşturmayı ve düzenlemeyi otomatikleştirmek için güçlü bir kütüphanedir.

### Aspose.Words for Java'ya nereden erişebilirim? 
   -  Aspose.Words for Java'yı şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/java/).

Aspose.Words for Java'yı bugün kullanmaya başlayın ve belge otomasyonu ve özelleştirmenin tüm potansiyelini ortaya çıkarın!

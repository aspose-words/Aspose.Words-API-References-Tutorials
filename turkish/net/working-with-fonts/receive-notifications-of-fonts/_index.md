---
title: Yazı Tiplerinin Bildirimlerini Alın
linktitle: Yazı Tiplerinin Bildirimlerini Alın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanırken eksik veya değiştirilmiş yazı tipi bildirimlerini nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/receive-notifications-of-fonts/
---

Bu öğreticide, Aspose.Words for .NET kullanırken yazı tipi bildirimlerini nasıl alacağınız konusunda size yol göstereceğiz. Yazı tipi bildirimleri, belgelerinizdeki eksik veya değiştirilen yazı tiplerini tespit etmenize ve yönetmenize olanak tanır. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin ve yazı tipi ayarlarını yapılandırın
 Ardından, kullanarak belgeyi yükleyeceğiz`Document` kullanarak yazı tipi ayarlarını sınıflandırın ve yapılandırın.`FontSettings` sınıf. Eksik yazı tipi olması durumunda kullanılacak varsayılan yazı tipini ayarlayacağız.

```csharp
//Belgeyi yükleyin ve yazı tipi ayarlarını yapılandırın
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## 3. Adım: Bildirim işleyiciyi ayarlayın
 Ardından, uygulayarak bir bildirim işleyicisi tanımlayacağız.`IWarningCallback` arayüz. Bu, belgeyi kaydederken yazı tipi uyarılarını toplamamıza izin verecektir.

```csharp
// Bildirim işleyicisini tanımlayın
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## 4. Adım: Yazı tipi ayarlarını uygulayın ve belgeyi kaydedin
Son olarak yazı tipi ayarlarını belgeye uygulayıp kaydedeceğiz. Yazı tipi uyarıları, daha önce tanımladığımız bildirim işleyicisi tarafından yakalanacaktır.

```csharp
// Yazı tipi ayarlarını uygulayın ve belgeyi kaydedin
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Aspose.Words for .NET kullanarak Yazı Tipi Bildirimlerini Almak için örnek kaynak kodu 
```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Eksik yazı tipi olması durumunda kullanılacak varsayılan yazı tipini seçebiliriz.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Test için Aspose.Words'ü sadece var olmayan bir klasördeki yazı tiplerini arayacak şekilde ayarlayacağız. Aspose.Words olmadığı için
// Belirtilen dizinde herhangi bir yazı tipi bulun, ardından oluşturma sırasında belgedeki yazı tipleri varsayılan ile alt uygun hale getirilecektir.
//FontSettings.DefaultFontName altında belirtilen yazı tipi. Geri aramamızı kullanarak bu subsuition'ı yakalayabiliriz.
fontSettings.SetFontsFolder(string.Empty, false);
// Belge kaydetme sırasında üretilen tüm uyarıları toplayan IWarningCallback'i uygulayan yeni bir sınıf oluşturun.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanırken yazı tipi bildirimlerinin nasıl alınacağını gördük. Yazı tipi bildirimleri, belgelerinizdeki eksik veya değiştirilen yazı tiplerini tespit etmenize ve yönetmenize olanak tanır. Belgelerinizde yazı tipi tutarlılığını sağlamak ve eksik yazı tipleri olması durumunda uygun eylemi gerçekleştirmek için bu özelliği kullanın.

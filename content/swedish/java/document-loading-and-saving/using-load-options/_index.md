---
title: Använda laddningsalternativ i Aspose.Words för Java
linktitle: Använda laddningsalternativ
second_title: Aspose.Words Java Document Processing API
description: Bemästra laddningsalternativ i Aspose.Words för Java. Anpassa dokumentladdning, hantera kryptering, konvertera former, ange Word-versioner och mer för effektiv Java-dokumentbehandling.
type: docs
weight: 11
url: /sv/java/document-loading-and-saving/using-load-options/
---

## Introduktion till att arbeta med laddningsalternativ i Aspose.Words för Java

den här handledningen kommer vi att utforska hur man arbetar med laddningsalternativ i Aspose.Words för Java. Ladda alternativ låter dig anpassa hur dokument laddas och bearbetas. Vi kommer att täcka olika scenarier, inklusive att uppdatera smutsiga fält, ladda krypterade dokument, konvertera former till Office Math, ställa in MS Word-versionen, ange en tillfällig mapp, hantera varningar och konvertera metafiler till PNG. Låt oss dyka in steg för steg.

## Uppdatera Dirty Fields

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 Det här kodavsnittet visar hur man uppdaterar smutsiga fält i ett dokument. De`setUpdateDirtyFields(true)` metod används för att säkerställa att smutsiga fält uppdateras under dokumentladdning.

## Ladda krypterade dokument

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 Här laddar vi ett krypterat dokument med ett lösenord. De`LoadOptions` constructor accepterar dokumentlösenordet, och du kan också ange ett nytt lösenord när du sparar dokumentet med`OdtSaveOptions`.

## Konvertera Shape till Office Math

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 Den här koden visar hur man konverterar former till Office Math-objekt under dokumentladdning. De`setConvertShapeToOfficeMath(true)`metoden möjliggör denna konvertering.

## Ställ in MS Word-version

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 Du kan ange MS Word-versionen för dokumentladdning. I det här exemplet ställer vi in versionen till Microsoft Word 2010 med hjälp av`setMswVersion`.

## Använd tillfällig mapp

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 Genom att ställa in den tillfälliga mappen med`setTempFolder`, kan du styra var temporära filer lagras under dokumentbehandling.

## Varning Återuppringning

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // Hantera varningar när de uppstår när dokument laddas.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

Den här koden visar hur man ställer in en varningsåteruppringning för att hantera varningar under dokumentladdning. Du kan anpassa programmets beteende när varningar uppstår.

## Konvertera metafiler till PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 För att konvertera metafiler (t.ex. WMF) till PNG-bilder under dokumentladdning, kan du använda`setConvertMetafilesToPng(true)` metod.

## Komplett källkod för att arbeta med laddningsalternativ i Aspose.Words för Java

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
}
@Test
public void setMsWordVersion() throws Exception {
	// Skapa ett nytt LoadOptions-objekt, som kommer att ladda dokument enligt MS Word 2019-specifikationen som standard
	// och ändra laddningsversionen till Microsoft Word 2010.
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//Skriver ut varningar och deras detaljer när de uppstår när dokument laddas.
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## Slutsats

I den här handledningen har vi fördjupat oss i olika aspekter av att arbeta med Load Options i Aspose.Words för Java. Inläsningsalternativ spelar en avgörande roll för att anpassa hur dokument laddas och bearbetas, vilket gör att du kan skräddarsy din dokumentbehandling efter dina specifika behov. Låt oss sammanfatta de viktigaste punkterna i den här guiden:

## FAQ's

### Hur kan jag hantera varningar under dokumentladdning?

 Du kan ställa in en varningsåteruppringning som visas i`warningCallback()` metoden ovan. Anpassa`DocumentLoadingWarningCallback` klass för att hantera varningar enligt din applikations krav.

### Kan jag konvertera former till Office Math-objekt när jag laddar ett dokument?

 Ja, du kan konvertera former till Office Math-objekt genom att använda`loadOptions.setConvertShapeToOfficeMath(true)`.

### Hur anger jag MS Word-versionen för dokumentladdning?

 Använda`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` för att ange MS Word-versionen för dokumentladdning.

###  Vad är syftet med`setTempFolder` method in Load Options?

 De`setTempFolder`metoden låter dig ange mappen där temporära filer lagras under dokumentbearbetningen.
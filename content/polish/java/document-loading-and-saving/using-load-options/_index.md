---
title: Korzystanie z opcji ładowania w Aspose.Words dla Java
linktitle: Korzystanie z opcji ładowania
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Opanowanie opcji ładowania w Aspose.Words dla Java. Dostosuj ładowanie dokumentów, obsługuj szyfrowanie, konwertuj kształty, ustawiaj wersje programu Word i nie tylko, aby wydajnie przetwarzać dokumenty Java.
type: docs
weight: 11
url: /pl/java/document-loading-and-saving/using-load-options/
---

## Wprowadzenie do pracy z opcjami ładowania w Aspose.Words dla Java

tym samouczku omówimy, jak pracować z opcjami ładowania w Aspose.Words dla Java. Opcje ładowania umożliwiają dostosowanie sposobu ładowania i przetwarzania dokumentów. Omówimy różne scenariusze, w tym aktualizację brudnych pól, ładowanie zaszyfrowanych dokumentów, konwertowanie kształtów do Office Math, ustawianie wersji MS Word, określanie folderu tymczasowego, obsługę ostrzeżeń i konwertowanie metaplików do formatu PNG. Zanurzmy się krok po kroku.

## Zaktualizuj brudne pola

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 Ten fragment kodu demonstruje, jak zaktualizować uszkodzone pola w dokumencie. The`setUpdateDirtyFields(true)` Metoda ta służy do zapewnienia aktualizacji brudnych pól podczas ładowania dokumentu.

## Załaduj zaszyfrowany dokument

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 Tutaj ładujemy zaszyfrowany dokument za pomocą hasła. The`LoadOptions` konstruktor akceptuje hasło dokumentu, możesz także określić nowe hasło podczas zapisywania dokumentu za pomocą`OdtSaveOptions`.

## Konwertuj kształt na Office Math

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 Ten kod ilustruje sposób konwertowania kształtów na obiekty pakietu Office Math podczas ładowania dokumentu. The`setConvertShapeToOfficeMath(true)`Metoda umożliwia tę konwersję.

## Ustaw wersję MS Word

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 Możesz określić wersję MS Word do ładowania dokumentu. W tym przykładzie ustawiliśmy wersję na Microsoft Word 2010 za pomocą`setMswVersion`.

## Użyj folderu tymczasowego

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 Ustawiając folder tymczasowy za pomocą`setTempFolder`możesz kontrolować miejsce przechowywania plików tymczasowych podczas przetwarzania dokumentu.

## Ostrzeżenie o oddzwonieniu

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // Postępuj z ostrzeżeniami pojawiającymi się podczas ładowania dokumentu.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

Ten kod demonstruje, jak skonfigurować wywołanie zwrotne z ostrzeżeniem w celu obsługi ostrzeżeń podczas ładowania dokumentu. Możesz dostosować zachowanie aplikacji w przypadku wystąpienia ostrzeżeń.

## Konwertuj metapliki na PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 Aby przekonwertować metapliki (np. WMF) na obrazy PNG podczas ładowania dokumentu, możesz użyć metody`setConvertMetafilesToPng(true)` metoda.

## Kompletny kod źródłowy do pracy z opcjami ładowania w Aspose.Words dla Java

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
	// Utwórz nowy obiekt LoadOptions, który domyślnie będzie ładować dokumenty zgodnie ze specyfikacją MS Word 2019
	// i zmień wersję ładującą na Microsoft Word 2010.
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
		//Drukuje ostrzeżenia i ich szczegóły pojawiające się podczas ładowania dokumentu.
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

## Wniosek

W tym samouczku zagłębiliśmy się w różne aspekty pracy z opcjami ładowania w Aspose.Words dla Java. Opcje ładowania odgrywają kluczową rolę w dostosowywaniu sposobu ładowania i przetwarzania dokumentów, umożliwiając dostosowanie przetwarzania dokumentów do konkretnych potrzeb. Podsumujmy najważniejsze punkty omówione w tym przewodniku:

## Często zadawane pytania

### Jak mogę obsługiwać ostrzeżenia podczas ładowania dokumentu?

 Możesz ustawić ostrzegawcze wywołanie zwrotne, jak pokazano w`warningCallback()` metoda powyżej. Dostosuj`DocumentLoadingWarningCallback` klasa do obsługi ostrzeżeń zgodnie z wymaganiami aplikacji.

### Czy podczas ładowania dokumentu mogę konwertować kształty na obiekty pakietu Office Math?

 Tak, możesz konwertować kształty na obiekty Office Math za pomocą`loadOptions.setConvertShapeToOfficeMath(true)`.

### Jak określić wersję programu MS Word do ładowania dokumentu?

 Używać`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` aby określić wersję MS Word do ładowania dokumentu.

###  Jaki jest cel`setTempFolder` method in Load Options?

 The`setTempFolder`Metoda pozwala określić folder, w którym będą przechowywane pliki tymczasowe podczas przetwarzania dokumentu.
---
title: Zapisywanie dokumentów w formacie OOXML w Aspose.Words dla Java
linktitle: Zapisywanie dokumentów w formacie OOXML
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak zapisywać dokumenty w formacie OOXML za pomocą Aspose.Words dla Java. Bez wysiłku zabezpiecz, optymalizuj i dostosowuj swoje pliki.
type: docs
weight: 20
url: /pl/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Wprowadzenie do zapisywania dokumentów w formacie OOXML w Aspose.Words dla Java

W tym przewodniku przyjrzymy się, jak zapisywać dokumenty w formacie OOXML przy użyciu Aspose.Words dla Java. OOXML (Office Open XML) to format pliku używany w programie Microsoft Word i innych aplikacjach biurowych. Omówimy różne opcje i ustawienia zapisywania dokumentów w formacie OOXML.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że w swoim projekcie masz skonfigurowaną bibliotekę Aspose.Words for Java.

## Zapisywanie dokumentu z szyfrowaniem hasła

Możesz zaszyfrować dokument hasłem, zapisując go w formacie OOXML. Oto jak możesz to zrobić:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Załaduj dokument
Document doc = new Document("Document.docx");

// Utwórz OoxmlSaveOptions i ustaw hasło
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Zapisz dokument z szyfrowaniem
doc.save("EncryptedDoc.docx", saveOptions);
```

## Ustawianie zgodności z OOXML

Podczas zapisywania dokumentu możesz określić poziom zgodności z OOXML. Można na przykład ustawić wartość ISO 29500:2008 (ścisła). Oto jak:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Załaduj dokument
Document doc = new Document("Document.docx");

// Optymalizuj pod kątem programu Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Utwórz OoxmlSaveOptions i ustaw poziom zgodności
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Zapisz dokument z ustawieniem zgodności
doc.save("ComplianceDoc.docx", saveOptions);
```

## Aktualizowanie właściwości ostatniego zapisanego czasu

Możesz zaktualizować właściwość „Ostatnio zapisany czas” dokumentu podczas jego zapisywania. Oto jak:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Załaduj dokument
Document doc = new Document("Document.docx");

// Utwórz OoxmlSaveOptions i włącz aktualizację właściwości Last Saved Time
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Zapisz dokument ze zaktualizowaną właściwością
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Zachowanie starszych znaków kontrolnych

Jeśli dokument zawiera starsze znaki kontrolne, możesz zachować je podczas zapisywania. Oto jak:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Załaduj dokument ze starszymi znakami kontrolnymi
Document doc = new Document("LegacyControlChars.doc");

//Utwórz OoxmlSaveOptions w formacie FLAT_OPC i włącz zachowanie starszych znaków kontrolnych
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Zapisz dokument ze starszymi znakami kontrolnymi
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Ustawianie poziomu kompresji

Poziom kompresji można dostosować podczas zapisywania dokumentu. Na przykład możesz ustawić SUPER_FAST, aby uzyskać minimalną kompresję. Oto jak:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Załaduj dokument
Document doc = new Document("Document.docx");

// Utwórz OoxmlSaveOptions i ustaw poziom kompresji
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Zapisz dokument z określonym poziomem kompresji
doc.save("FastCompressionDoc.docx", saveOptions);
```

Oto niektóre z kluczowych opcji i ustawień, których możesz użyć podczas zapisywania dokumentów w formacie OOXML przy użyciu Aspose.Words dla Java. Zachęcamy do zapoznania się z większą liczbą opcji i dostosowania procesu zapisywania dokumentów w razie potrzeby.

## Kompletny kod źródłowy do zapisywania dokumentów w formacie OOXML w Aspose.Words dla Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## Wniosek

tym obszernym przewodniku omówiliśmy, jak zapisywać dokumenty w formacie OOXML przy użyciu Aspose.Words dla Java. Niezależnie od tego, czy chcesz zaszyfrować dokumenty hasłami, zapewnić zgodność z określonymi standardami OOXML, zaktualizować właściwości dokumentu, zachować starsze znaki kontrolne lub dostosować poziomy kompresji, Aspose.Words zapewnia wszechstronny zestaw narzędzi spełniających Twoje wymagania.

## Często zadawane pytania

### Jak usunąć ochronę hasłem z dokumentu chronionego hasłem?

Aby usunąć ochronę hasłem z dokumentu chronionego hasłem, możesz otworzyć dokument z poprawnym hasłem, a następnie zapisać go bez podawania hasła w opcjach zapisywania. Spowoduje to zapisanie dokumentu bez ochrony hasłem.

### Czy mogę ustawić niestandardowe właściwości podczas zapisywania dokumentu w formacie OOXML?

 Tak, możesz ustawić niestandardowe właściwości dokumentu przed zapisaniem go w formacie OOXML. Skorzystaj z`BuiltInDocumentProperties`I`CustomDocumentProperties` klasy do ustawiania różnych właściwości, takich jak autor, tytuł, słowa kluczowe i właściwości niestandardowe.

### Jaki jest domyślny poziom kompresji podczas zapisywania dokumentu w formacie OOXML?

 Domyślny poziom kompresji podczas zapisywania dokumentu w formacie OOXML przy użyciu Aspose.Words dla Java to`NORMAL` . Możesz zmienić poziom kompresji na`SUPER_FAST` Lub`MAXIMUM` według potrzeb.
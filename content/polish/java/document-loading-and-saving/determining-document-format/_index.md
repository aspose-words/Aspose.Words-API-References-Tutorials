---
title: Określanie formatu dokumentu w Aspose.Words dla Java
linktitle: Określanie formatu dokumentu
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak wykrywać formaty dokumentów w Javie za pomocą Aspose.Words. Zidentyfikuj DOC, DOCX i inne. Efektywnie organizuj pliki.
type: docs
weight: 25
url: /pl/java/document-loading-and-saving/determining-document-format/
---

## Wprowadzenie do określania formatu dokumentu w Aspose.Words dla Java

Podczas pracy z przetwarzaniem dokumentów w Javie bardzo ważne jest określenie formatu plików, z którymi masz do czynienia. Aspose.Words dla Java zapewnia zaawansowane funkcje identyfikowania formatów dokumentów, a my przeprowadzimy Cię przez ten proces.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

- [Aspose.Words dla Javy](https://releases.aspose.com/words/java/)
- Zestaw Java Development Kit (JDK) zainstalowany w systemie
- Podstawowa znajomość programowania w języku Java

## Krok 1: Konfiguracja katalogu

Najpierw musimy skonfigurować niezbędne katalogi, aby skutecznie uporządkować nasze pliki. Stworzymy katalogi dla różnych typów dokumentów.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// Utwórz katalogi, jeśli jeszcze nie istnieją.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

Stworzyliśmy katalogi dla obsługiwanych, nieznanych, zaszyfrowanych i starszych typów dokumentów.

## Krok 2: Wykrywanie formatu dokumentu

Teraz wykryjmy format dokumentów w naszych katalogach. Aby to osiągnąć, użyjemy Aspose.Words dla Java.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // Wyświetl typ dokumentu
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // W razie potrzeby dodaj przypadki dla innych formatów dokumentów
    }

    // Obsługuj zaszyfrowane dokumenty
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // Obsługuj inne typy dokumentów
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

W tym fragmencie kodu iterujemy po plikach, wykrywamy ich formaty i organizujemy je w odpowiednich katalogach.

## Kompletny kod źródłowy do określania formatu dokumentu w Aspose.Words dla Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // Utwórz katalogi, jeśli jeszcze nie istnieją.
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            // Wyświetl typ dokumentu
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## Wniosek

Określanie formatów dokumentów w Aspose.Words dla Java jest niezbędne do wydajnego przetwarzania dokumentów. Wykonując czynności opisane w tym przewodniku, możesz zidentyfikować typy dokumentów i odpowiednio z nimi postępować w aplikacjach Java.

## Często zadawane pytania

### Jak zainstalować Aspose.Words dla Java?

 Możesz pobrać Aspose.Words dla Java z[Tutaj](https://releases.aspose.com/words/java/) i postępuj zgodnie z dostarczonymi instrukcjami instalacji.

### Jakie są obsługiwane formaty dokumentów?

Aspose.Words dla Java obsługuje różne formaty dokumentów, w tym DOC, DOCX, RTF, HTML i inne. Pełną listę można znaleźć w dokumentacji.

### Jak mogę wykryć zaszyfrowane dokumenty za pomocą Aspose.Words dla Java?

 Możesz skorzystać z`FileFormatUtil.detectFileFormat()` metoda wykrywania zaszyfrowanych dokumentów, jak pokazano w tym przewodniku.

### Czy są jakieś ograniczenia podczas pracy ze starszymi formatami dokumentów?

Starsze formaty dokumentów, takie jak MS Word 6 lub Word 95, mogą mieć ograniczenia w zakresie funkcji i zgodności z nowoczesnymi aplikacjami. W razie potrzeby rozważ aktualizację lub konwersję tych dokumentów.

### Czy mogę zautomatyzować wykrywanie formatu dokumentu w mojej aplikacji Java?

Tak, możesz zautomatyzować wykrywanie formatu dokumentu, integrując dostarczony kod z aplikacją Java. Umożliwia to przetwarzanie dokumentów w oparciu o wykryte formaty.
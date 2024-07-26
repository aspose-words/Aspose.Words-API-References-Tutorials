---
title: Wykryj format pliku dokumentu
linktitle: Wykryj format pliku dokumentu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wykrywać formaty plików dokumentów za pomocą Aspose.Words dla .NET, korzystając z tego obszernego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-fileformat/detect-file-format/
---
## Wstęp

W dzisiejszym cyfrowym świecie efektywne zarządzanie różnymi formatami dokumentów ma kluczowe znaczenie. Niezależnie od tego, czy obsługujesz formaty Word, PDF, HTML czy inne formaty, umiejętność prawidłowego wykrywania i przetwarzania tych plików może zaoszczędzić dużo czasu i wysiłku. W tym samouczku przyjrzymy się, jak wykryć formaty plików dokumentów za pomocą Aspose.Words dla .NET. Ten przewodnik przeprowadzi Cię przez wszystko, co musisz wiedzieć, od wymagań wstępnych po szczegółowy przewodnik krok po kroku.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.Words dla .NET: Możesz go pobrać z[Tutaj](https://releases.aspose.com/words/net/) . Upewnij się, że masz ważną licencję. Jeśli nie, możesz zdobyć[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).
- Visual Studio: każda najnowsza wersja będzie działać poprawnie.
- .NET Framework: Upewnij się, że masz zainstalowaną odpowiednią wersję.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw w swoim projekcie:

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

Podzielmy przykład na wiele kroków, aby ułatwić jego śledzenie.

## Krok 1: Skonfiguruj katalogi

Najpierw musimy skonfigurować katalogi, w których pliki będą sortowane na podstawie ich formatu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Utwórz katalogi, jeśli jeszcze nie istnieją.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## Krok 2: Uzyskaj listę plików

Następnie otrzymamy listę plików z katalogu, z wyłączeniem wszelkich uszkodzonych dokumentów.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Krok 3: Wykryj formaty plików

Teraz iterujemy po każdym pliku i wykrywamy jego format za pomocą Aspose.Words.

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // Wyświetl typ dokumentu
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## Wniosek

Wykrywanie formatów plików dokumentów przy użyciu Aspose.Words dla .NET jest prostym procesem. Konfigurując katalogi, uzyskując listę plików i wykorzystując Aspose.Words do wykrywania formatów plików, możesz efektywnie organizować swoje dokumenty i zarządzać nimi. Takie podejście nie tylko oszczędza czas, ale także zapewnia prawidłową obsługę różnych formatów dokumentów.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do programowej pracy z dokumentami programu Word. Umożliwia programistom tworzenie, modyfikowanie i konwertowanie dokumentów w różnych formatach.

### Czy Aspose.Words może wykryć zaszyfrowane dokumenty?
Tak, Aspose.Words może wykryć, czy dokument jest zaszyfrowany i możesz odpowiednio z nim postępować.

### Jakie formaty może wykryć Aspose.Words?
Aspose.Words może wykryć szeroką gamę formatów, w tym DOC, DOCX, RTF, HTML, MHTML, ODT i wiele innych.

### Jak mogę uzyskać tymczasową licencję na Aspose.Words?
 Możesz uzyskać tymczasową licencję od[Zakup Aspose](https://purchase.aspose.com/temporary-license/) strona.

### Gdzie mogę znaleźć dokumentację Aspose.Words?
 Można znaleźć dokumentację Aspose.Words[Tutaj](https://reference.aspose.com/words/net/).

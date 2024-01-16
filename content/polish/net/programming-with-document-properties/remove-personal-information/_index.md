---
title: Usuń dane osobowe
linktitle: Usuń dane osobowe
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący usuwania danych osobowych z dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-properties/remove-personal-information/
---

tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby usunąć dane osobowe z dokumentu za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia usunięcie z dokumentu wrażliwych danych osobowych, takich jak dane identyfikacyjne autora.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Załaduj dokument

Na tym etapie prześlemy dokument Word, z którego chcemy usunąć dane osobowe. Aby załadować dokument, użyj poniższego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką katalogu, w którym znajduje się dokument.

## Krok 3: Usuń dane osobowe

 Teraz umożliwimy usunięcie danych osobowych, ustawiając`RemovePersonalInformation`własność do`true`. Użyj następującego kodu:

```csharp
doc.RemovePersonalInformation = true;
```

Ten kod aktywuje usunięcie danych osobowych z dokumentu.

## Krok 4: Zapisywanie dokumentu

Na koniec zapiszemy dokument z usuniętymi danymi osobowymi. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Ten kod zapisuje dokument z usuniętymi danymi osobowymi w nowym pliku.

### Przykładowy kod źródłowy do usuwania danych osobowych przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Pamiętaj, aby określić poprawną ścieżkę dokumentu w pliku`dataDir` zmienny.

Nauczyłeś się teraz, jak usunąć dane osobowe z dokumentu za pomocą Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo usunąć poufne informacje ze swoich dokumentów.
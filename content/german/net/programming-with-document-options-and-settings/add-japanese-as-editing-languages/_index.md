---
title: Japanisch als Bearbeitungssprache hinzufügen
linktitle: Japanisch als Bearbeitungssprache hinzufügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Hinzufügen von Japanisch als Bearbeitungssprache mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie Japanisch als Bearbeitungssprache mit Aspose.Words für .NET hinzufügen und implementieren. Mit dieser Funktion können Sie beim Laden eines Dokuments Spracheinstellungen festlegen und Japanisch als Bearbeitungssprache hinzufügen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, das keine Standardbearbeitungssprache enthält und dem wir Japanisch hinzufügen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Legen Sie die Spracheinstellungen fest, die beim Laden des Dokuments verwendet werden.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Schritt 3: Überprüfen der Standardsprache

Nach dem Laden des Dokuments prüfen wir, ob die Standardbearbeitungssprache korrekt auf Japanisch eingestellt wurde. Verwenden Sie den folgenden Code, um die fernöstliche Sprach-ID zu erhalten:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Der Code prüft, ob die fernöstliche Sprachkennung mit der des Japanischen übereinstimmt. Je nach Ergebnis gibt er eine entsprechende Meldung aus.

### Beispielquellcode zum Hinzufügen von Japanisch als Bearbeitungssprache mit Aspose.Words für .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Legen Sie die Spracheinstellungen fest, die beim Laden des Dokuments verwendet werden.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```


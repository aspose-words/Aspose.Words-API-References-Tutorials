---
title: Russisch als Standardbearbeitungssprache festlegen
linktitle: Russisch als Standardbearbeitungssprache festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen von Russisch als Standardbearbeitungssprache eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Russisch als Standardbearbeitungssprache mit Aspose.Words für .NET festzulegen. Mit dieser Funktion können Sie die Standardsprache beim Laden eines Dokuments festlegen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, für das wir Russisch als Standardbearbeitungssprache festlegen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Überprüfen der Standardsprache

Nach dem Hochladen des Dokuments prüfen wir, ob die Standardsprache korrekt auf Russisch eingestellt wurde. Verwenden Sie den folgenden Code, um die Standardsprachen-ID abzurufen:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Der Code prüft, ob die Sprach-ID mit der russischen übereinstimmt. Je nach Ergebnis wird eine entsprechende Meldung angezeigt.

### Beispielquellcode zum Festlegen von Russisch als Standardbearbeitungssprache mit Aspose.Words für .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET Russisch als Standardbearbeitungssprache für ein Dokument festlegen. Indem Sie der Schritt-für-Schritt-Anleitung folgen
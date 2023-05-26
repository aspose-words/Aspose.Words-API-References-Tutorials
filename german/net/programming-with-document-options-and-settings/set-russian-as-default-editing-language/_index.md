---
title: Legen Sie Russisch als Standardbearbeitungssprache fest
linktitle: Legen Sie Russisch als Standardbearbeitungssprache fest
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen von Russisch als Standardbearbeitungssprache eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Russisch als Standardbearbeitungssprache mit Aspose.Words für .NET festzulegen. Mit dieser Funktion können Sie beim Laden eines Dokuments die Standardsprache festlegen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, für das wir Russisch als Standardbearbeitungssprache festlegen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Überprüfen der Standardsprache

Nach dem Hochladen des Dokuments prüfen wir, ob die Standardsprache korrekt auf Russisch eingestellt ist. Verwenden Sie den folgenden Code, um die Standardsprachen-ID abzurufen:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Der Code prüft, ob die Sprach-ID mit der von Russisch übereinstimmt. Je nach Ergebnis wird eine entsprechende Meldung angezeigt.

### Beispielquellcode für „Russisch als Standardbearbeitungssprache festlegen“ mit Aspose.Words für .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben jetzt erfahren, wie Sie mit Aspose.Words für .NET Russisch als Standardbearbeitungssprache für ein Dokument festlegen. Indem Sie der Schritt-Anleitung folgen
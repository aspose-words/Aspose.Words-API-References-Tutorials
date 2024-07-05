---
title: Persönliche Informationen entfernen
linktitle: Persönliche Informationen entfernen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Entfernen persönlicher Informationen aus einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/remove-personal-information/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um mit Aspose.Words für .NET persönliche Informationen aus einem Dokument zu entfernen. Mit dieser Funktion können Sie vertrauliche persönliche Informationen aus einem Dokument entfernen, z. B. Autorenidentifikationsdaten.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument hoch, aus dem wir die persönlichen Daten entfernen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Persönliche Daten löschen

 Nun aktivieren wir die Entfernung personenbezogener Daten, indem wir die`RemovePersonalInformation`Eigentum an`true`. Verwenden Sie den folgenden Code:

```csharp
doc.RemovePersonalInformation = true;
```

Dieser Code aktiviert die Löschung der personenbezogenen Daten im Dokument.

## Schritt 4: Speichern des Dokuments

Zum Schluss speichern wir das Dokument, ohne die persönlichen Daten zu entfernen. Verwenden Sie dazu den folgenden Code:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Dieser Code speichert das Dokument mit den entfernten persönlichen Informationen in einer neuen Datei.

### Beispielquellcode zum Entfernen persönlicher Informationen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET persönliche Informationen aus einem Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie vertrauliche Informationen problemlos aus Ihren eigenen Dokumenten entfernen.
---
title: Persönliche Daten entfernen
linktitle: Persönliche Daten entfernen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Entfernen persönlicher Informationen aus einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/remove-personal-information/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um mit Aspose.Words für .NET persönliche Informationen aus einem Dokument zu entfernen. Mit dieser Funktion können Sie vertrauliche persönliche Informationen aus einem Dokument entfernen, beispielsweise Daten zur Autoridentifikation.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument hoch, aus dem wir die persönlichen Daten entfernen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Persönliche Daten löschen

 Jetzt aktivieren wir das Entfernen personenbezogener Daten, indem wir das festlegen`RemovePersonalInformation` Eigentum zu`true`. Verwenden Sie den folgenden Code:

```csharp
doc.RemovePersonalInformation = true;
```

Dieser Code aktiviert das Löschen personenbezogener Daten im Dokument.

## Schritt 4: Speichern des Dokuments

Abschließend speichern wir das Dokument mit entfernten persönlichen Daten. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Dieser Code speichert das Dokument mit den entfernten persönlichen Informationen in einer neuen Datei.

### Beispielquellcode zum Entfernen persönlicher Informationen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben jetzt erfahren, wie Sie mit Aspose.Words für .NET persönliche Informationen aus einem Dokument entfernen. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie vertrauliche Informationen ganz einfach aus Ihren eigenen Dokumenten entfernen.
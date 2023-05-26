---
title: Formularfelder Holen Sie sich eine Sammlung von Formularfeldern
linktitle: Formularfelder Holen Sie sich eine Sammlung von Formularfeldern
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Formularfeldsammlungen in Word-Dokumenten abrufen und bearbeiten.
type: docs
weight: 10
url: /de/net/working-with-formfields/form-fields-get-form-fields-collection/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Sammlung von Formularfeldern aus einem Word-Dokument abrufen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` -Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben, das Formularfelder enthält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## Schritt 2: Abrufen der Formularfeldsammlung

 Als nächstes greifen Sie auf zu`FormFields` Eigentum der`Range` Objekt im Dokument, um die Sammlung von Formularfeldern abzurufen:

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

 Jetzt haben Sie die Sammlung von Formularfeldern aus dem Word-Dokument im gespeichert`formFields` Variable.

## Schritt 3: Auf die Formularfelder zugreifen und diese bearbeiten

Sie können die Formularfeldsammlung durchlaufen und verschiedene Vorgänge für jedes Formularfeld ausführen, z. B. Werte abrufen oder festlegen, Formatierungen ändern oder Informationen extrahieren.

```csharp
foreach (FormField formField in formFields)
{
    // Greifen Sie auf jedes Formularfeld zu und bearbeiten Sie es
    // ...
}
```

## Schritt 4: Speichern des Dokuments

Abschließend speichern Sie ggf. das geänderte Dokument:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Das ist es! Sie haben die Sammlung von Formularfeldern mit Aspose.Words für .NET erfolgreich aus einem Word-Dokument abgerufen.

### Beispielquellcode für Formularfelder. Holen Sie sich eine Sammlung von Formularfeldern mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// Greifen Sie nach Bedarf auf die Formularfelder zu und bearbeiten Sie sie
// ...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.
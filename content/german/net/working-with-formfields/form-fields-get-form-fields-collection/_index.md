---
title: Formularfelder Sammlung von Formularfeldern abrufen
linktitle: Formularfelder Sammlung von Formularfeldern abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Sammlung von Formularfeldern in Word-Dokumenten abrufen und bearbeiten.
type: docs
weight: 10
url: /de/net/working-with-formfields/form-fields-get-form-fields-collection/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Sammlung von Formularfeldern aus einem Word-Dokument abrufen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Sie Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet haben. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst den`Document` Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben, das die Formularfelder enthält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## Schritt 2: Abrufen der Formularfelder-Sammlung

 Als nächstes greifen Sie auf die`FormFields` Eigentum der`Range` Objekt im Dokument, um die Sammlung der Formularfelder abzurufen:

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

 Nun haben Sie die Sammlung der Formularfelder aus dem Word-Dokument im`formFields` Variable.

## Schritt 3: Zugriff auf und Bearbeitung der Formularfelder

Sie können die Sammlung der Formularfelder durchlaufen und für jedes Formularfeld verschiedene Vorgänge ausführen, z. B. Werte abrufen oder festlegen, die Formatierung ändern oder Informationen extrahieren.

```csharp
foreach (FormField formField in formFields)
{
    // Zugriff auf jedes Formularfeld und dessen Bearbeitung
    // ...
}
```

## Schritt 4: Speichern des Dokuments

Speichern Sie abschließend ggf. das geänderte Dokument:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Das ist es! Sie haben die Sammlung von Formularfeldern erfolgreich aus einem Word-Dokument mit Aspose.Words für .NET abgerufen.

### Beispielquellcode für Formularfelder. Formularfeldersammlung mit Aspose.Words für .NET abrufen

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// Greifen Sie nach Bedarf auf die Formularfelder zu und bearbeiten Sie sie
// ...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und ihn entsprechend Ihren spezifischen Anforderungen ändern.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words auf die Sammlung der Formularfelder zugreifen?

 A: Um auf die Sammlung von Formularfeldern in Aspose.Words zuzugreifen, können Sie das`Document.FormFields` Eigenschaft. Diese Eigenschaft gibt die vollständige Sammlung der im Dokument vorhandenen Formularfelder zurück.

#### F: Wie kann ich durch die Formularfelder iterieren und für jedes davon Operationen ausführen?

 A: Sie können Formularfelder durchlaufen mit einem`foreach` Schleife auf der`Document.FormFields` Sammlung. Bei jeder Iteration können Sie auf Eigenschaften zugreifen und bestimmte Vorgänge am Formularfeld ausführen.

#### F: Kann ich die Sammlung der Formularfelder filtern, um nur bestimmte Feldtypen zu erhalten?

A: Ja, Sie können die Sammlung der Formularfelder mithilfe geeigneter Bedingungen in Ihrer Iterationsschleife filtern. Sie können beispielsweise den Feldtyp jedes Elements überprüfen und nur die Felder bearbeiten, die Ihren Kriterien entsprechen.

#### F: Wie kann ich ein bestimmtes Formularfeld aus der Sammlung entfernen?

 A: Um ein bestimmtes Formularfeld aus der Sammlung zu entfernen, können Sie das`FormField.Remove` Methode, die das zu entfernende Feld angibt. Diese Methode entfernt das Formularfeld aus der Sammlung.

#### F: Ist es möglich, die Eigenschaften eines Formularfelds in Aspose.Words zu ändern?

A: Ja, Sie können die Eigenschaften eines Formularfelds in Aspose.Words ändern, indem Sie auf seine einzelnen Eigenschaften zugreifen. Sie können beispielsweise den Namen, den Wert oder die Optionen eines Formularfelds mithilfe der entsprechenden Eigenschaften ändern.
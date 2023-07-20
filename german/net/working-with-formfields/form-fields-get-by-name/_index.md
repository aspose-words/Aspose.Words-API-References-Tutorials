---
title: Formularfelder nach Namen abrufen
linktitle: Formularfelder nach Namen abrufen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Formularfelder in Word-Dokumenten nach Namen abrufen und ändern.
type: docs
weight: 10
url: /de/net/working-with-formfields/form-fields-get-by-name/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Formularfelder nach Namen aus einem Word-Dokument abrufen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie[Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` -Objekt, indem Sie den Pfad zu Ihrem Quelldokument angeben, das Formularfelder enthält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Schritt 2: Formularfelder abrufen

 Als nächstes greifen Sie auf zu`FormFields` Eigentum der`Range` Objekt im Dokument, um alle Formularfelder abzurufen:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Sie können Formularfelder entweder nach Index oder nach Namen abrufen. In diesem Beispiel rufen wir ein Formularfeld mit beiden Methoden ab:

```csharp
FormField formField1 = documentFormFields[3]; //Abrufen nach Index
FormField formField2 = documentFormFields["Text2"]; // Abrufen mit Namen
```

## Schritt 3: Formularfeldeigenschaften ändern

 Nachdem Sie die Formularfelder abgerufen haben, können Sie deren Eigenschaften nach Bedarf ändern. In diesem Beispiel ändern wir die Schriftgröße von`formField1` bis 20 und die Schriftfarbe von`formField2` zu rot:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Schritt 4: Speichern des Dokuments

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Das ist es! Sie haben erfolgreich Formularfelder nach Namen abgerufen und ihre Eigenschaften in einem Word-Dokument mit Aspose.Words für .NET geändert.

### Beispielquellcode für „Formularfelder nach Namen abrufen“ mit Aspose.Words für .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.

### FAQs

#### F: Wie kann ich in Aspose.Words ein Formularfeld nach Namen abrufen?

 A: Um ein Formularfeld nach Namen in Aspose.Words abzurufen, können Sie das verwenden`Document.Range.FormFields[name]` Methode. Diese Methode gibt das Formularfeld zurück, das dem angegebenen Namen entspricht.

#### F: Was passiert, wenn das Formularfeld mit dem angegebenen Namen im Dokument nicht vorhanden ist?

 A: Wenn das Formularfeld mit dem angegebenen Namen nicht im Dokument vorhanden ist, wird das`Document.Range.FormFields[name]` Die Methode wird zurückgegeben`null`Sie können dieses Ergebnis überprüfen, um Fälle zu behandeln, in denen das Formularfeld nicht gefunden wird.

#### F: Wie kann ich die Eigenschaften eines gefundenen Formularfelds ändern?

A: Sobald Sie ein Formularfeld nach Namen erhalten, können Sie auf seine einzelnen Eigenschaften zugreifen, um sie zu bearbeiten. Sie können beispielsweise den Wert des Felds ändern, seine Sichtbarkeit aktivieren oder deaktivieren oder andere Eigenschaften nach Bedarf ändern.

#### F: Kann ich in einem Dokument mehrere Formularfelder mit demselben Namen erhalten?

 A: Ja, es ist möglich, in einem Dokument mehrere Formularfelder mit demselben Namen zu haben. In diesem Fall ist die`Document.Range.FormFields[name]` Die Methode gibt das erste gefundene Formularfeld mit dem angegebenen Namen zurück. Wenn Sie über mehrere Formularfelder mit demselben Namen verfügen, müssen Sie dies bei der Bearbeitung der Felder berücksichtigen.

#### F: Wie kann ich alle Formularfelder in einem Dokument durchlaufen?

 A: Um alle Formularfelder in einem Dokument zu durchlaufen, können Sie a verwenden`foreach` Schleife auf der`Document.Range.FormFields` Sammlung. Dadurch können Sie auf jedes Formularfeld einzeln zugreifen und Vorgänge für jedes Feld ausführen.
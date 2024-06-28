---
title: Felder im Dokument konvertieren
linktitle: Felder im Dokument konvertieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Konvertieren von Dokumentfeldern in Text mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/convert-fields-in-document/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Verwendung der ConvertFieldsInDocument-Funktion der Aspose.Words für .NET-Software. Wir erläutern den für diese Funktion erforderlichen C#-Quellcode im Detail und stellen Beispiel-Markdown-Ausgabeformate bereit.

## Schritt 1: Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.Words für .NET ist auf Ihrem Entwicklungscomputer installiert.
- Ein Word-Dokument mit verknüpften Feldern, die Sie in Text konvertieren möchten.
- Ein Dokumentverzeichnis, in dem Sie das transformierte Dokument speichern können.

## Schritt 2: Einrichten der Umgebung
Stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung ordnungsgemäß für die Verwendung von Aspose.Words für .NET konfiguriert haben. Importieren Sie die erforderlichen Namespaces und legen Sie den Pfad zu Ihrem Dokumentenverzeichnis fest.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Laden Sie das Dokument
 Benutzen Sie die`Document` Klasse von Aspose.Words, um das Word-Dokument zu laden, das die verknüpften Felder enthält, die Sie konvertieren möchten.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## Schritt 4: Konvertieren Sie gebundene Felder in Text
 Benutzen Sie die`Unlink()` Methode zum Konvertieren aller im Dokument vorkommenden Felder vom Typ „IF“ in Text. Mit dieser Methode werden verknüpfte Felder in ihren Textinhalt umgewandelt.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## Schritt 5: Speichern Sie das transformierte Dokument
 Benutzen Sie die`Save()` Methode zum Speichern des Dokuments mit den in Text konvertierten Feldern im angegebenen Dokumentverzeichnis.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Beispielquellcode für ConvertFieldsInDocument mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die ConvertFieldsInDocument-Funktion:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// Übergeben Sie die entsprechenden Parameter, um alle im Dokument vorkommenden IF-Felder (einschließlich Kopf- und Fußzeilen) in Text umzuwandeln.
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// Speichern Sie das Dokument mit den transformierten Feldern auf der Festplatte
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Abschluss
Die ConvertFieldsInDocument-Funktion von Aspose.Words für .NET ist ein leistungsstarkes Tool zum Konvertieren verknüpfter Felder in einem Word-Dokument in Text. 

### FAQs

#### F: Was ist eine Feldkonvertierung in Aspose.Words?

A: Eine Feldkonvertierung in Aspose.Words bezieht sich auf die Möglichkeit, Daten aus einem Feld in einem Word-Dokument mithilfe verschiedener Formate oder Datentypen umzuwandeln. Dadurch können Sie die Darstellung oder Struktur der Daten im endgültigen Dokument ändern.

#### F: Wie konvertiere ich Felder in einem Word-Dokument mit Aspose.Words?

A: Um Felder in einem Word-Dokument mit Aspose.Words zu konvertieren, können Sie die folgenden Schritte ausführen:

1. Importieren Sie die Document-Klasse aus dem Aspose.Words-Namespace.
2. Erstellen Sie eine Instanz von Document, indem Sie Ihr vorhandenes Dokument laden.
3. Verwenden Sie die UpdateFields-Methode, um alle Felder im Dokument zu aktualisieren und die Konvertierungen durchzuführen.

#### F: Welche Arten von Konvertierungen sind in Aspose.Words möglich?

A: Aspose.Words unterstützt verschiedene Arten der Konvertierung in Feldern, z. B. das Konvertieren von Datumsformaten, das Konvertieren von Zahlenformaten, das Konvertieren von Textformaten, das Konvertieren von Währungsformaten, das Konvertieren von Prozentformaten und noch mehr. Eine vollständige Liste der unterstützten Konvertierungstypen finden Sie in der Aspose.Words-Dokumentation.

#### F: Verändert das Konvertieren von Feldern die Originaldaten im Word-Dokument?

A: Nein, das Konvertieren von Feldern in Aspose.Words hat keinen Einfluss auf die Originaldaten im Word-Dokument. Die Konvertierung wird beim Aktualisieren von Feldern angewendet, die Originaldaten bleiben jedoch erhalten. Dadurch ist sichergestellt, dass Sie jederzeit zum Originalzustand des Dokuments zurückkehren können.

#### F: Ist es möglich, Feldkonvertierungen in Aspose.Words anzupassen?

A: Ja, es ist möglich, Feldkonvertierungen in Aspose.Words anzupassen, indem bestimmte Formatierungscodes verwendet oder die verfügbaren Konvertierungsoptionen angepasst werden. Sie können benutzerdefinierte Formate für Datumsangaben, Zahlen, Texte usw. definieren, um Ihren spezifischen Anforderungen gerecht zu werden.
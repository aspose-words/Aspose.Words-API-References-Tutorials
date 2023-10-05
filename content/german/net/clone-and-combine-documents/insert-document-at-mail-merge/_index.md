---
title: Dokument beim Seriendruck einfügen
linktitle: Dokument beim Seriendruck einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument beim Seriendruck in ein anderes einfügen.
type: docs
weight: 10
url: /de/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie beim Seriendruck mithilfe der Funktion „Dokument beim Seriendruck einfügen“ von Aspose.Words für .NET ein Dokument in ein anderes Dokument einfügen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und das Einfügen des Dokuments durchzuführen.

## Schritt 1: Laden des Hauptdokuments

Geben Sie zunächst das Verzeichnis für Ihre Dokumente an und laden Sie das Hauptdokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Schritt 2: Konfigurieren Sie den Serienbrief

Nun konfigurieren wir den Serienbrief und geben den Feld-Merge-Callback an, um ein Dokument in ein anderes Dokument einzufügen. Hier ist wie:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Schritt 3: Ausführen des Seriendrucks

Wir führen den Seriendruck durch, indem wir die Namen der Seriendruckfelder und die entsprechenden Daten angeben. Hier ist wie:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Beispielquellcode für „Dokument beim Seriendruck einfügen“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Dokument in Serienbrief einfügen“ von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Das Hauptdokument enthält ein Zusammenführungsfeld namens „Document_1“.
// Die entsprechenden Daten für dieses Feld enthalten einen vollständig qualifizierten Pfad zum Dokument.
// Das sollte in dieses Feld eingefügt werden.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Mit diesem Code können Sie beim Seriendruck mit Aspose.Words für .NET ein Dokument in ein anderes Dokument einfügen. Das resultierende Dokument wird unter einem neuen Namen gespeichert


## Abschluss

In diesem Tutorial haben wir untersucht, wie man ein Dokument während des Seriendrucks mithilfe der Funktion „Dokument beim Seriendruck einfügen“ von Aspose.Words für .NET in ein anderes Dokument einfügt. Durch die Konfiguration des Seriendrucks und die Bereitstellung der erforderlichen Daten können Sie Dokumente dynamisch zusammenstellen, indem Sie verschiedene Dokumentvorlagen oder Abschnitte zusammenführen. Aspose.Words für .NET bietet eine flexible und leistungsstarke Möglichkeit zur Verwaltung komplexer Dokumentenerstellungsszenarien und macht es zu einem wertvollen Werkzeug zur Automatisierung von Dokumentenerstellungs- und -bearbeitungsaufgaben.

### FAQs

#### F: Welchen Zweck hat das Einfügen eines Dokuments in ein anderes Dokument beim Seriendruck?

A: Durch das Einfügen eines Dokuments in ein anderes Dokument während des Seriendrucks können Sie verschiedene Dokumentvorlagen oder Abschnitte dynamisch basierend auf den während des Seriendruckvorgangs bereitgestellten Daten kombinieren. Diese Funktion ist besonders nützlich, wenn Sie komplexe Dokumente zusammenstellen möchten, indem Sie verschiedene vordefinierte Vorlagen oder Abschnitte zu einem endgültigen Dokument zusammenführen.

#### F: Wie füge ich beim Seriendruck mit Aspose.Words für .NET ein Dokument in ein anderes Dokument ein?

A: Um ein Dokument während des Seriendrucks mit Aspose.Words für .NET in ein anderes Dokument einzufügen, führen Sie die folgenden Schritte aus:
1. Laden Sie das Hauptdokument, das als Basis dienen soll, in ein Document-Objekt.
2. Konfigurieren Sie den Serienbrief und geben Sie den Feld-Merge-Rückruf an, um das Einfügen von Dokumenten zu verarbeiten.
3. Führen Sie den Serienbrief mit den Namen der Seriendruckfelder und den entsprechenden Daten (Pfad zum einzufügenden Dokument) aus.

#### F: Wie kann ich das Einfügeverhalten beim Seriendruck anpassen?

A: Um das Einfügeverhalten beim Seriendruck anzupassen, können Sie einen benutzerdefinierten FieldMergingCallback implementieren, indem Sie von der IFieldMergingCallback-Schnittstelle erben. Dadurch können Sie steuern, wie die Dokumente entsprechend Ihren spezifischen Anforderungen eingefügt und zusammengeführt werden.

#### F: Kann ich beim Seriendruck mehrere Dokumente einfügen?

A: Ja, Sie können beim Seriendruck mehrere Dokumente einfügen, indem Sie für jedes Seriendruckfeld die entsprechenden Daten angeben. Geben Sie für jedes Briefvorlagenfeld, das das Einfügen eines Dokuments erfordert, den Pfad zum entsprechenden Dokument als Daten an.



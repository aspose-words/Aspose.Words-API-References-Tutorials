---
title: Schutztyp im Word-Dokument abrufen
linktitle: Schutztyp im Word-Dokument abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Schutztyp im Word-Dokument abrufen“ von Aspose.Words für .NET verwenden, um den Schutztyp eines Dokuments zu bestimmen.
type: docs
weight: 10
url: /de/net/document-protection/get-protection-type/
---
Willkommen zu dieser Schritt-für-Schritt-Anleitung, die den C#-Quellcode für die Funktion „Schutztyp abrufen“ von Aspose.Words für .NET erklärt. In diesem Artikel zeigen wir Ihnen, wie Sie mit dieser leistungsstarken Funktion den Schutztyp eines Dokuments bestimmen. Der Dokumentenschutz ist unerlässlich, um die Vertraulichkeit und Integrität Ihrer Dateien zu gewährleisten. Wir führen Sie durch die erforderlichen Schritte zur Integration von Aspose.Words für .NET und zur Verwendung der Funktion „Schutztyp abrufen“.

## Schritt 1: Laden des Dokuments

Der erste Schritt zur Verwendung der Funktion „Schutztyp abrufen“ besteht darin, das Dokument hochzuladen, an dem Sie arbeiten möchten. Sie können dies mithilfe der von Aspose.Words für .NET bereitgestellten Document-Klasse tun. Hier ist ein Beispielcode zum Laden eines Dokuments aus einer Datei:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Achten Sie darauf, den richtigen Pfad zu Ihrer Dokumentdatei anzugeben.

## Schritt 2: Abrufen des Schutztyps

Nachdem das Dokument hochgeladen wurde, können Sie die ProtectionType-Eigenschaft des Document-Objekts verwenden, um den auf das Dokument angewendeten Schutztyp abzurufen. So können Sie vorgehen:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Beispiel-Quellcode für „Get Protection Type“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Get Protection Type“ mit Aspose.Words für .NET:

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## Abschluss

In diesem Artikel haben wir erklärt, wie Sie die Funktion „Get Protection Type“ von Aspose.Words für .NET verwenden, um den Schutztyp eines Dokuments zu bestimmen. Wenn Sie die beschriebenen Schritte befolgen, können Sie diese Funktion problemlos in Ihre eigenen C#-Projekte integrieren und geschützte Dokumente effizient bearbeiten. Aspose.Words für .NET bietet große Flexibilität

### Häufig gestellte Fragen

#### F: Was ist die ProtectionType-Eigenschaft in Aspose.Words für .NET?

 A: Die`ProtectionType` -Eigenschaft in Aspose.Words für .NET ist eine Funktion, mit der Sie die Art des Schutzes bestimmen können, der auf ein Word-Dokument angewendet wird. Sie bietet Informationen zum Grad des Dokumentschutzes, z. B. ob das Dokument für Kommentare, Revisionen, Formulare oder andere Arten von Einschränkungen geschützt ist.

#### F: Wie kann ich mit Aspose.Words für .NET den Schutztyp eines Dokuments abrufen?

A: Um den Schutztyp eines Dokuments mit Aspose.Words für .NET abzurufen, können Sie diese Schritte ausführen:
1.  Laden Sie das Dokument mit dem`Document` Klasse.
2.  Greife auf ... zu`ProtectionType` Eigentum der`Document`Objekt, um den Schutztyp abzurufen.

#### F: Kann ich mithilfe der Eigenschaft ProtectionType feststellen, ob ein Dokument für Formulare oder Formularfelder geschützt ist?

 A: Ja, Sie können feststellen, ob ein Dokument für Formulare oder Formularfelder geschützt ist, indem Sie`ProtectionType` Eigenschaft in Aspose.Words für .NET. Wenn der Schutztyp auf`AllowOnlyFormFields`bedeutet, dass das Dokument geschützt ist und nur Formularfelder bearbeitet werden können.

#### F: Welche anderen Schutztypen kann die ProtectionType-Eigenschaft zurückgeben?

 A: Die`ProtectionType` -Eigenschaft in Aspose.Words für .NET kann verschiedene Schutztypen zurückgeben, darunter:
- `NoProtection`: Das Dokument ist nicht geschützt.
- `AllowOnlyRevisions`: Das Dokument ist geschützt und es können nur Änderungen vorgenommen werden.
- `AllowOnlyComments`: Das Dokument ist geschützt und es können nur Kommentare hinzugefügt werden.
- `AllowOnlyFormFields`: Das Dokument ist geschützt und nur Formularfelder können bearbeitet werden.
- `ReadOnly`: Das Dokument ist geschützt und schreibgeschützt.

#### F: Kann ich den Schutztyp eines Dokuments mit der Eigenschaft „ProtectionType“ ändern?

 A: Nein, die`ProtectionType`Eigenschaft in Aspose.Words für .NET ist eine schreibgeschützte Eigenschaft. Sie ermöglicht Ihnen, den aktuellen Schutztyp eines Dokuments abzurufen, bietet jedoch keine direkte Möglichkeit, den Schutztyp zu ändern. Um den Schutztyp zu ändern, müssen Sie andere Methoden und Eigenschaften verwenden, die in der`Document` Klasse, wie`Protect` oder`Unprotect`.

#### F: Ist es möglich, ein Dokument gleichzeitig mit mehreren Schutzarten zu schützen?

A: Nein, Aspose.Words für .NET erlaubt nur die Anwendung eines Schutztyps auf ein Dokument gleichzeitig. Sie können jedoch verschiedene Schutztypen kombinieren, indem Sie den Schutz aktivieren, einen Typ festlegen, den Schutz deaktivieren und ihn dann mit einem anderen Typ erneut aktivieren.


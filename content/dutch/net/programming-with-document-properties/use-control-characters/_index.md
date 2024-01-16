---
title: Gebruik controletekens
linktitle: Gebruik controletekens
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het gebruik van stuurtekens met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/use-control-characters/
---

In deze zelfstudie leiden we u door de C#-broncode voor het gebruik van besturingstekens met Aspose.Words voor .NET. Met deze functie kunt u controletekens in tekst manipuleren.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Controletekens gebruiken

In deze stap gaan we controletekens in een tekst gebruiken. Gebruik de volgende code:

```csharp
const string text = "test\r";
// Vervang het controleteken "\r" door "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Deze code definieert a`text` string die het controleteken "\r" (nieuwe regel) bevat en gebruikt de`Replace` methode om het te vervangen door het besturingsteken "\r\n" (nieuwe regel). regel gevolgd door een regeleinde).

### Voorbeeldbroncode voor gebruik van stuurtekens met Aspose.Words voor .NET

```csharp

	const string text = "test\r";
	// Vervang het controleteken "\r" door "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 U kunt de bovenstaande code in uw eigen project gebruiken door de`text` string met uw eigen tekst met controletekens.

Je hebt nu geleerd hoe je besturingstekens kunt gebruiken met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig besturingstekens in uw eigen toepassingen manipuleren.
---
title: Använd kontrolltecken
linktitle: Använd kontrolltecken
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att använda kontrolltecken med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/use-control-characters/
---

I den här handledningen går vi igenom C#-källkoden för att använda kontrolltecken med Aspose.Words för .NET. Denna funktion låter dig manipulera kontrolltecken i text.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Använda kontrolltecken

I det här steget kommer vi att använda kontrolltecken i en text. Använd följande kod:

```csharp
const string text = "test\r";
// Byt ut kontrolltecknet "\r" med "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Denna kod definierar en`text` sträng som innehåller kontrolltecknet "\r" (nyrad) och använder`Replace` metod för att ersätta det med kontrolltecknet "\r\n" (ny rad). rad följt av en radbrytning).

### Exempel på källkod för Använd kontrolltecken med Aspose.Words för .NET

```csharp

	const string text = "test\r";
	// Byt ut "\r" kontrolltecken med "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Du kan använda ovanstående kod i ditt eget projekt genom att ersätta`text` sträng med din egen text som innehåller kontrolltecken.

Du har nu lärt dig hur du använder kontrolltecken med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt manipulera kontrolltecken i dina egna applikationer.
---
title: Použijte řídicí znaky
linktitle: Použijte řídicí znaky
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce používáním řídicích znaků s Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/use-control-characters/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro použití řídicích znaků s Aspose.Words pro .NET. Tato funkce umožňuje manipulovat s řídicími znaky v textu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Použití řídicích znaků

V tomto kroku budeme v textu používat řídicí znaky. Použijte následující kód:

```csharp
const string text = "test\r";
// Nahraďte řídicí znak "\r" znakem "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

 Tento kód definuje a`text` řetězec obsahující řídicí znak "\r" (nový řádek) a používá`Replace` způsob, jak jej nahradit řídicím znakem "\r\n" (nový řádek). řádek následovaný zalomením řádku).

### Příklad zdrojového kódu pro použití řídicích znaků pomocí Aspose.Words pro .NET

```csharp

	const string text = "test\r";
	// Nahraďte řídicí znak "\r" znakem "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
 Výše uvedený kód můžete použít ve svém vlastním projektu nahrazením`text` řetězec s vlastním textem obsahujícím řídicí znaky.

Nyní jste se naučili používat řídicí znaky s Aspose.Words pro .NET. Podle podrobného průvodce v tomto kurzu můžete snadno manipulovat s řídicími znaky ve svých vlastních aplikacích.
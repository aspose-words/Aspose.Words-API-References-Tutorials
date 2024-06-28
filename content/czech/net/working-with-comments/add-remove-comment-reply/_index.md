---
title: Přidat Odebrat komentář Odpovědět
linktitle: Přidat Odebrat komentář Odpovědět
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se přidávat a odebírat odpovědi na komentáře v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-comments/add-remove-comment-reply/
---

tomto komplexním tutoriálu se naučíte přidávat a odstraňovat odpovědi na komentáře v dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete moci spravovat odpovědi na komentáře a upravovat je podle svých požadavků.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vložte dokument
Chcete-li začít, načtěte dokument, který obsahuje komentáře, pomocí třídy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Krok 2: Přístup k komentáři a správě odpovědí
Dále otevřete komentář z dokumentu pomocí metody GetChild s parametrem NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Chcete-li z komentáře odstranit odpověď, použijte metodu RemoveReply a zadejte požadovaný index odpovědi:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Chcete-li ke komentáři přidat novou odpověď, použijte metodu AddReply a zadejte jméno autora, iniciály autora, datum a čas a text odpovědi:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Krok 3: Uložte dokument
Po přidání nebo odstranění odpovědí na komentáře uložte dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Příklad zdrojového kódu pro Přidat a odebrat odpovědi na komentáře pomocí Aspose.Words for .NET
Zde je úplný zdrojový kód pro přidávání a odstraňování odpovědí na komentáře pomocí Aspose.Words pro .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak přidávat a odebírat odpovědi na komentáře v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete nyní spravovat odpovědi na komentáře a upravovat je podle svých požadavků.

Odpovědi na komentáře umožňují společné diskuse a zpětnou vazbu v rámci dokumentu. Experimentujte s různými autory odpovědí, iniciálami, daty a texty, abyste zlepšili spolupráci a komunikaci v rámci svých dokumentů.

### FAQ

#### Otázka: Jak mohu přidat komentář v Aspose.Words pro .NET?

 A: Chcete-li přidat komentář v Aspose.Words pro .NET, můžete použít`Comment.AddComment` metoda určující text komentáře a místo, kam jej chcete v dokumentu přidat.

#### Otázka: Jak mohu odstranit komentář v Aspose.Words pro .NET?

A: Chcete-li odstranit komentář v Aspose.Words pro .NET, můžete použít`Comment.Remove` způsob upřesňující`Comment` objekt, který chcete odstranit.

#### Otázka: Mohu odpovědět na komentář v Aspose.Words pro .NET?

 Odpověď: Ano, můžete odpovědět na komentář v Aspose.Words pro .NET pomocí`Comment.AddReply` metoda určující text odpovědi a místo, kam jej chcete v dokumentu přidat.

#### Otázka: Jak mohu získat přístup ke stávajícím komentářům v Aspose.Words for .NET?

 Odpověď: Ke stávajícím komentářům v Aspose.Words pro .NET můžete přistupovat pomocí`CommentCollection` vlastnictvím`Document` objekt. To vám umožní procházet všechny komentáře v dokumentu.

#### Otázka: Mohu upravit text komentáře v Aspose.Words pro .NET?

 Odpověď: Ano, můžete upravit text komentáře v Aspose.Words pro .NET přístupem k`Comment.Text` vlastnost odpovídající`Comment` objekt a upravovat text podle potřeby.
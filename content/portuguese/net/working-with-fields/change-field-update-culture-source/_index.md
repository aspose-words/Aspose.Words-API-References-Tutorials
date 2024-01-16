---
title: Alterar fonte de cultura de atualização de campo
linktitle: Alterar fonte de cultura de atualização de campo
second_title: API de processamento de documentos Aspose.Words
description: Alterar fonte de cultura de atualização de campo, guia passo a passo para modificar a fonte de cultura em Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/change-field-update-culture-source/
---

Neste tutorial, iremos guiá-lo através do processo de alteração da fonte de cultura de atualização de campo em documentos do Word usando Aspose.Words for .NET. Ao modificar a origem da cultura, você pode controlar a formatação da data durante as operações de atualização de campo e de mala direta. Forneceremos a você o código-fonte C# necessário e instruções passo a passo para fazer isso.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: crie um documento e o DocumentBuilder
Para começar, crie uma instância da classe Document e um objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir conteúdo com localidade específica
Em seguida, defina a localidade como alemão e insira campos com formatação de data:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

No código acima, definimos a localidade da fonte como Alemão (ID de localidade 1031) e inserimos dois campos com formatação de data específica.

## Etapa 3: alterar a origem da cultura de atualização de campo
Para alterar a origem da cultura de atualização de campo, use a classe FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

Neste exemplo, definimos a cultura usada durante a atualização do campo para ser escolhida a partir da cultura usada pelo campo.

## Etapa 4: realizar a mala direta
Execute uma operação de mala direta e especifique o valor de data para o campo "Data2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

Neste trecho de código, executamos a operação de mala direta e fornecemos um valor DateTime para o campo “Date2”.

## Etapa 5: salve o documento
Salve o documento modificado em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Exemplo de código-fonte para alterar a fonte da cultura de atualização de campo usando Aspose.Words para .NET
Aqui está o código-fonte completo para alterar a fonte da cultura de atualização de campo em documentos do Word usando Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como alterar a origem da cultura de atualização de campo em documentos do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode controlar a cultura usada para formatação de data durante operações de atualização de campo e mala direta. Personalize a fonte de cultura de acordo com suas necessidades para garantir datas precisas e consistentes.

### Perguntas frequentes

#### P: Como posso alterar a fonte da cultura de atualização do campo no Aspose.Words for .NET?

 R: Para alterar a fonte da cultura de atualização do campo no Aspose.Words for .NET, você pode usar o`Document.FieldOptions.CultureSource` propriedade e defina seu valor como`FieldCultureSource.FieldCode` ou`FieldCultureSource.CurrentThread` . Por exemplo, você pode usar`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` para usar a cultura definida no código do campo.

#### P: Como posso especificar uma cultura específica para atualizar campos no Aspose.Words for .NET?

R: Para especificar uma cultura específica para atualização de campos no Aspose.Words for .NET, você pode usar o`Document.FieldOptions.FieldUpdateCultureInfo` propriedade e definir o`CultureInfo` objeto correspondente à cultura desejada. Por exemplo, você pode usar`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` para especificar a cultura francesa (França).

#### P: É possível desabilitar a atualização automática de campos no Aspose.Words for .NET?

 R: Sim, é possível desabilitar a atualização automática de campos no Aspose.Words for .NET. Você pode usar o`Document.FieldOptions.UpdateFields` propriedade e configure-a para`false` para evitar que os campos sejam atualizados automaticamente. Isso permite controlar manualmente a atualização dos campos conforme necessário.

#### P: Como posso atualizar manualmente os campos do documento no Aspose.Words for .NET?

 R: Para atualizar manualmente os campos em um documento no Aspose.Words for .NET, você pode usar o`Field.Update` método para cada campo individualmente. Por exemplo, você pode usar`field.Update()` para atualizar o campo específico.
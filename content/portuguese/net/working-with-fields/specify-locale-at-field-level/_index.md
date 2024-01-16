---
title: Especifique a localidade no nível do campo
linktitle: Especifique a localidade no nível do campo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como especificar a localização em nível de campo em documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/specify-locale-at-field-level/
---

Aqui está um guia passo a passo para explicar o seguinte código-fonte C# que permite especificar a localização no nível do campo usando o recurso Aspose.Words for .NET. Certifique-se de incluir a biblioteca Aspose.Words em seu projeto antes de usar este código.

## Etapa 1: definir o caminho do diretório do documento

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Certifique-se de especificar o caminho correto para o diretório de documentos onde o documento editado será salvo.

## Passo 2: Crie um gerador de documentos

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Aqui estamos criando uma instância do`DocumentBuilder` classe que nos permitirá adicionar campos ao documento.

## Etapa 3: insira um campo de data com um local específico

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Usamos o gerador de documentos para inserir um campo do tipo`FieldType.FieldDate` no documento. Ao definir o`LocaleId`propriedade para`1049`, especificamos a localização russa para este campo.

## Etapa 4: salve o documento modificado

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Finalmente, salvamos o documento modificado com o local especificado em um arquivo especificado.

### Exemplo de código-fonte para especificar a localização em nível de campo com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Este foi um exemplo de código-fonte para especificar a localização no nível do campo em um documento usando Aspose.Words for .NET. Você pode usar este código para inserir campos de data com locais específicos em seus documentos do Word.

### Perguntas frequentes

#### P: Como posso especificar a localidade em nível de campo no Aspose.Words for .NET?

 R: Para especificar a localidade no nível do campo no Aspose.Words for .NET, você pode usar o`FieldOptions` classe e sua`FieldLocale` propriedade para definir a localidade desejada. Por exemplo, você pode usar`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` para especificar o código do idioma francês (França).

#### P: É possível especificar uma localidade diferente para cada campo no Aspose.Words for .NET?

 R: Sim, é possível especificar uma localidade diferente para cada campo no Aspose.Words for .NET. Você pode usar o`FieldOptions.FieldLocale` propriedade antes de criar ou atualizar um campo específico para atribuir a ele um código de idioma diferente.

#### P: Como posso obter a localidade usada atualmente para um campo no Aspose.Words for .NET?

 R: Para obter a localidade usada atualmente para um campo no Aspose.Words for .NET, você pode usar o campo`Field.LocaleId` propriedade. Isso permitirá que você obtenha o identificador de localidade associado ao campo.
---
title: Renomear campos de mesclagem
linktitle: Renomear campos de mesclagem
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, você aprenderá como renomear campos de mesclagem em um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/rename-merge-fields/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso de renomeação de campo de mesclagem do Aspose.Words for .NET. Siga cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Criando o documento e inserindo os campos de mesclagem

Começamos criando um novo documento e usando um`DocumentBuilder` para inserir os campos de mesclagem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Etapa 3: renomeando campos de mesclagem

Percorremos cada campo no intervalo do documento e, se for um campo de mesclagem, renomeamos o campo adicionando o "_Sufixo renomeado".

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Passo 4: Salvando o documento

 Por fim, chamamos o`Save()` método para salvar o documento modificado.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Exemplo de código-fonte para renomear campos de mesclagem com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e insira os campos de mesclagem.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Renomeie os campos de mesclagem.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Salve o documento.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Siga estas etapas para renomear campos de mesclagem em seu documento usando Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como posso renomear campos mesclados em um documento do Word usando Aspose.Words for .NET?

 R: Para renomear campos mesclados em um documento do Word usando Aspose.Words for .NET, você pode percorrer os campos do documento usando o`FieldMergingArgs` classe e use o`FieldMergingArgs.FieldName` método para renomear campos.

#### P: É possível renomear apenas alguns campos mesclados em um documento do Word com Aspose.Words for .NET?

R: Sim, é possível renomear apenas alguns campos mesclados em um documento do Word com Aspose.Words for .NET. Você pode filtrar quais campos renomear usando critérios específicos, como nome do campo ou outras propriedades relevantes. Então você pode renomear os campos correspondentes usando o`FieldMergingArgs.FieldName` método.

#### P: Como posso verificar se um campo mesclado foi renomeado com sucesso em um documento do Word com Aspose.Words for .NET?

 R: Para verificar se um campo mesclado foi renomeado com sucesso em um documento do Word com Aspose.Words for .NET, você pode usar o`FieldMergedArgs` aula e acesse o`FieldMergedArgs.IsMerged` propriedade para determinar se o campo foi renomeado com hit.

#### P: Quais são as consequências de renomear um campo mesclado em um documento do Word com Aspose.Words for .NET?

R: Quando você renomeia um campo mesclado em um documento do Word com Aspose.Words for .NET, ele altera o nome do campo no documento, o que pode afetar outras funcionalidades ou processos que dependem do nome do campo. Certifique-se de considerar essas possíveis consequências antes de renomear os campos mesclados.

#### P: É possível restaurar o nome original de um campo mesclado após renomeá-lo com Aspose.Words for .NET?

R: Sim, é possível restaurar o nome original de um campo mesclado após renomeá-lo com Aspose.Words for .NET. Você pode armazenar o nome original do campo em uma variável ou lista e usar essas informações para restaurar o nome original, se necessário.
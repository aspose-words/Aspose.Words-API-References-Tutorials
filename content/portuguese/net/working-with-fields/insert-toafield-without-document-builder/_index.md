---
title: Inserir campo TOA sem Document Builder
linktitle: Inserir campo TOA sem Document Builder
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para inserir o campo TOA sem o Document Builder usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-toafield-without-document-builder/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "TOA Field Insertion" do Aspose.Words for .NET. Siga cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando o Documento e o Parágrafo

Começamos criando um novo documento e inicializando um parágrafo.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Passo 3: Inserindo o campo TA

Usamos a classe FieldTA para inserir um campo TA no parágrafo.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Etapa 4: adicionar o parágrafo ao corpo do documento

Adicionamos o parágrafo que contém o campo TA ao corpo do documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Passo 5: Criando o parágrafo para o campo TOA

Criamos um novo parágrafo para o campo TOA.

```csharp
para = new Paragraph(doc);
```

## Passo 6: Inserindo o campo TOA

Usamos a classe FieldToa para inserir um campo TOA no parágrafo.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Passo 7: Adicionando o parágrafo ao corpo do documento

Adicionamos o parágrafo que contém o campo TOA ao corpo do documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Etapa 8: atualizar o campo TOA

 Por fim, chamamos o`Update()` método para atualizar o campo TOA.

```csharp
fieldToa.Update();
```

### Exemplo de código-fonte para inserção de campo TOA sem Document Builder com Aspose.Words for .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Queremos inserir campos TA e TOA assim:
// { TA \c 1 \l "Valor 0" }
// {TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Perguntas frequentes

#### P: Como personalizar a aparência do campo TOA inserido no documento Word com Aspose.Words for .NET?

R: Você pode personalizar a aparência do campo TOA inserido usando as propriedades do campo`FieldTOA` objeto para especificar opções de formatação.

#### P: Posso adicionar vários campos TOA em um único documento do Word usando Aspose.Words for .NET?

R: Sim, você pode adicionar vários campos TOA em um único documento do Word usando Aspose.Words for .NET. Basta repetir as etapas de inserção para cada campo.

#### P: Como posso verificar se um campo TOA foi inserido com sucesso em um documento do Word com Aspose.Words for .NET?

R: Para verificar se um campo TOA foi inserido com sucesso, você pode navegar pelo conteúdo do documento e procurar por instâncias de campo TOA.

#### P: A inserção de um campo TOA sem usar o DocumentBuilder afeta a formatação de documentos do Word com Aspose.Words for .NET?

R: Inserir um campo TOA sem usar o DocumentBuilder não afeta diretamente a formatação do documento do Word. No entanto, as opções de formatação do campo TOA podem impactar a formatação geral do documento.
---
title: Cultura de atualização de campo
linktitle: Cultura de atualização de campo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como atualizar a cultura de campo em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/field-update-culture/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Atualização de cultura de campo" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Criando o documento e o gerador de documentos

Começamos criando um novo documento e um gerador de documentos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passo 3: Inserindo o campo de hora

 Nós usamos o`InsertField()` método para inserir um campo de hora no documento.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Isso irá inserir um campo de hora no documento.

## Etapa 4: configurando a cultura de atualização de campo

Configuramos as opções de campo para especificar que a cultura de atualização de campo deve ser baseada no código de campo.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Essas opções determinam a cultura usada para atualização de campos.

### Exemplo de código-fonte para atualização de cultura de campo com Aspose.Words para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e o gerador de documentos.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira o campo de hora.
builder. InsertField(FieldType.FieldTime, true);

// Configure a cultura de atualização de campo.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Salve o documento.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

Neste exemplo, criamos um novo documento, inserimos um campo de hora e configuramos a cultura de atualização do campo. Em seguida, salvamos o documento com um nome de arquivo especificado.

Isso conclui nosso guia sobre como usar o recurso "Atualizar cultura de campo" com Aspose.Words for .NET.

### Perguntas frequentes

#### P: Qual é a cultura de atualização de campo no Aspose.Words?

R: A cultura de atualização de campo em Aspose.Words refere-se à cultura usada para formatar e atualizar valores de campo em um documento do Word. A cultura determina como números, datas e outros dados são apresentados nos campos quando são atualizados.

#### P: Como definir a cultura de atualização para campos em um documento do Word com Aspose.Words?

R: Para definir a cultura de atualização para campos em um documento do Word com Aspose.Words, você pode seguir estas etapas:

1. Importe a classe Document do namespace Aspose.Words.
2. Crie uma instância de Document carregando seu documento existente.
3. Use a propriedade Document.UpdateFieldsCultureInfo para definir a cultura de atualização dos campos.

#### P: Quais são as culturas suportadas para atualização de campos no Aspose.Words?

R: Aspose.Words oferece suporte a diferentes culturas para atualização de campos. Você pode especificar qualquer cultura compatível com o sistema operacional. Por exemplo, “en-US” para inglês americano, “fr-FR” para francês, “de-DE” para alemão, etc.

#### P: É possível definir uma cultura específica para um campo individual em vez de para todo o documento?

R: Sim, é possível definir uma cultura específica para um campo individual em vez de para todo o documento. Em Aspose.Words, cada campo possui uma propriedade Format que pode ser usada para definir a cultura de formatação específica para aquele campo. Isso permite controlar como esse campo é exibido e atualizado independentemente de outros campos do documento.

#### P: Como posso verificar a cultura de atualização de campo atualmente definida em um documento do Word?

R: Para verificar a cultura de atualização de campo atualmente definida em um documento do Word, você pode usar a propriedade Document.UpdateFieldsCultureInfo. Esta propriedade retorna o objeto CultureInfo que representa a cultura usada atualmente para definir atualizações de campo.
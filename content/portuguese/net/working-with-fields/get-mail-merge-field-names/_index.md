---
title: Obtenha nomes de campos de mala direta
linktitle: Obtenha nomes de campos de mala direta
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como obter nomes de campos de mala direta em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/get-mail-merge-field-names/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Obter nomes de campos de mesclagem" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregando o documento

A primeira etapa é carregar o documento onde deseja obter os nomes dos campos de mesclagem.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Certifique-se de substituir "SEU ARQUIVO DE DOCUMENTO" pelo nome do seu próprio arquivo.

## Etapa 3: obter nomes de campos de mesclagem

 Nós usamos o`GetFieldNames()` método para obter um array contendo os nomes dos campos de mesclagem presentes no documento.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 O`fieldNames` variável agora contém os nomes dos campos de mesclagem.

### Exemplo de código-fonte para obter nomes de campos de mesclagem com Aspose.Words para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Obtenha nomes de campos de mesclagem.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Exiba o número de campos de mesclagem.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Neste exemplo, carregamos um documento, obtivemos os nomes dos campos de mesclagem usando o`GetFieldNames()` método e exibiu o número de campos de mesclagem presentes no documento.

Isso conclui nosso guia sobre como usar o recurso "Obter nomes de campos de mesclagem" com Aspose.Words for .NET.

### Perguntas frequentes

#### Q1: O que é mala direta no Aspose.Words?

A mala direta no Aspose.Words é um processo para mesclar dados de uma fonte externa (por exemplo, planilha Excel ou banco de dados) com um modelo de documento do Word para criar documentos personalizados. Isso facilita a geração automatizada de cartas, relatórios e outros documentos similares.

#### P2: Como obtenho a lista de campos de mala direta disponíveis em um documento do Word?

Para obter a lista de campos de mala direta disponíveis em um documento do Word, você pode seguir estas etapas:

1. Importe as classes Document e MailMergeFieldNames do namespace Aspose.Words.
2. Crie uma instância de Document carregando seu documento do Word.
3. Use o método GetMailMergeFieldNames do objeto Document para obter a lista de campos de mala direta disponíveis.

Aqui está um exemplo de código para ilustrar o processo:

```csharp
// Importe os namespaces necessários
using Aspose.Words;
using Aspose.Words.MailMerging;

// Carregue o documento existente
Document document = new Document("FilePath");

// Obtenha uma lista de campos de mala direta
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Percorrer os campos de mala direta disponíveis
foreach (string fieldName in fieldNames)
{
     // Faça algo com o nome do campo
     Console.WriteLine(fieldName);
}
```
### Perguntas frequentes

#### P: O que é mala direta no Aspose.Words?

R: A mala direta no Aspose.Words é um processo para mesclar dados de uma fonte externa (por exemplo, planilha Excel ou banco de dados) com um modelo de documento do Word para criar documentos personalizados. Isso facilita a geração automatizada de cartas, relatórios e outros documentos similares.

#### P: Como obtenho a lista de campos de mala direta disponíveis em um documento do Word?

R: Para obter a lista de campos de mala direta disponíveis em um documento do Word, você pode seguir estas etapas:

1. Importe as classes Document e MailMergeFieldNames do namespace Aspose.Words.
2. Crie uma instância de Document carregando seu documento do Word.
3. Use o método GetMailMergeFieldNames do objeto Document para obter a lista de campos de mala direta disponíveis.

#### P: Posso obter campos de mala direta de uma fonte de dados externa, como uma planilha do Excel?

R: Sim, você pode obter os campos de mala direta de uma fonte de dados externa, como uma planilha do Excel. Para isso, você pode usar os recursos de vinculação de dados do Aspose.Words para estabelecer uma conexão com a fonte de dados e obter os nomes dos campos disponíveis.

#### P: É possível filtrar campos de mala direta com base em determinados critérios?

R: Sim, é possível filtrar campos de mala direta com base em determinados critérios. Você pode usar expressões regulares ou condições específicas para filtrar campos de mala direta e obter apenas aqueles que atendem aos seus critérios específicos.

#### P: Como posso manipular campos de mala direta no Aspose.Words?

R: Para manipular campos de mala direta em Aspose.Words, você pode usar os métodos e propriedades fornecidos pelos objetos Document e MailMergeField. Você pode adicionar, remover ou atualizar campos de mala direta, bem como recuperar e editar valores associados a campos.
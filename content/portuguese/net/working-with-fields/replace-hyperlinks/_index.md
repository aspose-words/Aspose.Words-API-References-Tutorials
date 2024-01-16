---
title: Substituir hiperlinks
linktitle: Substituir hiperlinks
second_title: API de processamento de documentos Aspose.Words
description: Substitua hiperlinks em documentos do Word usando Aspose.Words for .NET. Instruções passo a passo para substituir hiperlinks.
type: docs
weight: 10
url: /pt/net/working-with-fields/replace-hyperlinks/
---

Aqui está um guia passo a passo para explicar o seguinte código-fonte C# para substituir hiperlinks usando a funcionalidade Aspose.Words for .NET. Certifique-se de incluir a biblioteca Aspose.Words em seu projeto antes de usar este código.

## Etapa 1: definir o caminho do diretório do documento

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Certifique-se de especificar o caminho correto para o diretório de documentos que contém o`Hyperlinks.docx` arquivo.

## Passo 2: Carregue o documento que contém os hiperlinks

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Aqui estamos criando uma instância do`Document` classe do arquivo especificado.

## Etapa 3: navegue pelos campos para encontrar hiperlinks

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Alguns hiperlinks podem ser locais (links para marcadores dentro do documento), nós os ignoramos.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Este loop percorre todos os campos do documento procurando por campos do tipo`FieldType.FieldHyperlink` . Uma vez encontrado um campo deste tipo, verificamos se é um link local verificando o`SubAddress` propriedade. Caso contrário, substituímos o endereço do link por`"http://www.aspose.com"` e o resultado com`"Aspose - The .NET & Java Component Editor"`.

## Etapa 4: salve o documento modificado

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Finalmente, salvamos o documento modificado com os hiperlinks substituídos em um arquivo especificado.

### Exemplo de código-fonte para substituir hiperlinks por Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Alguns hiperlinks podem ser locais (links para marcadores dentro do documento), nós os ignoramos.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Este é um exemplo de código-fonte para substituir hiperlinks em um documento usando Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como posso substituir hiperlinks em um documento do Word usando Aspose.Words for .NET?

 R: Para substituir hiperlinks em um documento do Word usando Aspose.Words for .NET, você pode usar o`Document.Range.Replace`método que especifica o texto a ser pesquisado e o texto de substituição. Certifique-se de usar as opções apropriadas para definir os parâmetros de pesquisa e substituição.

#### P: É possível substituir apenas alguns hiperlinks em um documento do Word pelo Aspose.Words for .NET?

R: Sim, é possível substituir apenas alguns hiperlinks em um documento do Word pelo Aspose.Words for .NET. Você pode filtrar os hiperlinks a serem substituídos usando critérios específicos, como URL do link, texto do link ou qualquer outra propriedade relevante. Então você pode aplicar a substituição apenas aos hiperlinks correspondentes.

#### P: Como posso ignorar hiperlinks em cabeçalhos, rodapés ou notas de rodapé ao substituir por Aspose.Words for .NET?

R: Para ignorar hiperlinks em cabeçalhos, rodapés ou notas de rodapé ao substituir por Aspose.Words for .NET, você pode usar as opções de pesquisa avançada e especificar limites de pesquisa apropriados. Por exemplo, você pode limitar a pesquisa às seções principais do documento e excluir cabeçalhos, rodapés ou notas de rodapé.

#### P: É possível substituir hiperlinks por links internos para outras partes do documento?

 R: Sim, é possível substituir hiperlinks por links internos para outras partes do documento com Aspose.Words for .NET. Você pode usar âncoras ou IDs de texto para criar links internos e depois substituí-los usando o`Document.Range.Replace` método com as opções apropriadas.

#### P: A substituição de hiperlinks por Aspose.Words for .NET preserva as propriedades do link, como cores ou estilos?

R: Sim, ao substituir hiperlinks por Aspose.Words for .NET, as propriedades do link, como cores ou estilos, são mantidas. Você pode especificar as mesmas propriedades de formatação no texto de substituição para obter um resultado consistente.
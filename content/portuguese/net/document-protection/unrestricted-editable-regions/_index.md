---
title: Regiões editáveis irrestritas em documentos do Word
linktitle: Regiões editáveis irrestritas em documentos do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar áreas editáveis irrestritas em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-protection/unrestricted-editable-regions/
---
Neste tutorial, iremos guiá-lo através das etapas para usar o recurso de áreas editáveis irrestritas do Aspose.Words for .NET. Este recurso permite definir áreas em um documento do Word onde o conteúdo pode ser editado sem restrições, mesmo que o restante do documento seja somente leitura. Siga os passos abaixo:

## Etapa 1: Carregar o documento e configurar a proteção

Comece carregando o documento existente:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Proteja o documento definindo o tipo de proteção somente leitura e a senha

## Passo 2: Criando uma área editável

Comece criando uma área editável usando os objetos EditableRangeStart e EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Um objeto EditableRange é criado para o EditableRangeStart que acabamos de criar.
EditableRange editableRange = edRangeStart.EditableRange;

// Coloque algo dentro do intervalo editável.
builder.Writeln("Paragraph inside first editable range");

// Um intervalo editável está bem formado se tiver um início e um fim.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Etapa 3: adicione conteúdo fora das áreas editáveis

Você pode adicionar conteúdo fora das áreas editáveis, que permanecerão somente leitura:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Etapa 4: salve o documento

Por fim, salve o documento modificado:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para salvar o documento com áreas editáveis.

### Exemplo de código-fonte para regiões editáveis irrestritas usando Aspose.Words for .NET

Aqui está o código-fonte completo para áreas editáveis irrestritas usando Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregue um documento e torne-o somente leitura.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Inicie um intervalo editável.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Um objeto EditableRange é criado para o EditableRangeStart que acabamos de criar.
EditableRange editableRange = edRangeStart.EditableRange;

// Coloque algo dentro do intervalo editável.
builder.Writeln("Paragraph inside first editable range");

// Um intervalo editável está bem formado se tiver um início e um fim.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Seguindo essas etapas, você pode criar facilmente áreas editáveis irrestritas em seu documento do Word com Aspose.Words for .NET.

## Conclusão
Neste tutorial, aprendemos como criar regiões editáveis irrestritas em um documento do Word usando Aspose.Words for .NET. Seguindo as etapas fornecidas, você pode definir áreas específicas dentro do documento onde os usuários podem editar livremente o conteúdo, mantendo o restante do documento somente leitura. Aspose.Words for .NET oferece recursos poderosos para proteção e personalização de documentos, fornecendo controle sobre os recursos de edição de seus documentos do Word.

### Perguntas frequentes para regiões editáveis irrestritas em documentos do Word

#### P: O que são regiões editáveis irrestritas no Aspose.Words for .NET?

R: Regiões editáveis irrestritas no Aspose.Words for .NET são áreas dentro de um documento do Word onde o conteúdo pode ser editado sem quaisquer restrições, mesmo se o restante do documento estiver definido como somente leitura. Essas regiões fornecem uma maneira de definir partes específicas do documento que os usuários podem modificar, mantendo ao mesmo tempo a proteção geral do documento.

#### P: Como posso criar regiões editáveis irrestritas usando Aspose.Words for .NET?

R: Para criar regiões editáveis irrestritas em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Carregue o documento existente usando o`Document` aula.
2.  Defina a proteção do documento como somente leitura usando o`Protect` método do`Document` objeto.
3.  Use o`DocumentBuilder` classe para criar um intervalo editável adicionando um`EditableRangeStart` objeto e um`EditableRangeEnd` objeto.
4.  Adicione conteúdo dentro do intervalo editável usando o`DocumentBuilder`.
5.  Salve o documento modificado usando o`Save` método do`Document` objeto.

#### P: Posso ter várias regiões editáveis irrestritas em um documento do Word?

R: Sim, você pode ter várias regiões editáveis irrestritas em um documento do Word. Para conseguir isso, você pode criar vários conjuntos de`EditableRangeStart` e`EditableRangeEnd` objetos usando o`DocumentBuilder` aula. Cada conjunto de objetos definirá uma região editável separada onde os usuários poderão modificar o conteúdo sem quaisquer restrições.

#### P: Posso aninhar regiões editáveis umas nas outras?

 R: Não, você não pode aninhar regiões editáveis umas nas outras usando Aspose.Words for .NET. Cada região editável definida por um`EditableRangeStart` e`EditableRangeEnd` O par deve ser independente e não se sobrepor ou estar aninhado em outra região editável. Regiões editáveis aninhadas não são suportadas.

#### P: Posso remover a proteção somente leitura do documento em uma região editável?

R: Não, você não pode remover a proteção somente leitura do documento dentro de uma região editável. A proteção somente leitura é aplicada a todo o documento e não pode ser removida seletivamente em regiões editáveis específicas. A finalidade das regiões editáveis é permitir a modificação do conteúdo, mantendo o documento geral somente leitura.
---
title: Seção irrestrita em documento do Word
linktitle: Seção irrestrita em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir seções irrestritas em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-protection/unrestricted-section/
---
Neste tutorial, iremos guiá-lo através das etapas para usar o recurso de seção irrestrita do Aspose.Words for .NET. Este recurso permite definir seções específicas em um documento do Word que não estão protegidas, mesmo que o restante do documento esteja protegido. Siga os passos abaixo:

## Etapa 1: Criando o Documento e as Seções

Comece criando uma instância da classe Document e um objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: adicione conteúdo ao documento
Use o objeto DocumentBuilder para adicionar conteúdo ao documento e inserir quebras de seção:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Etapa 3: proteger documentos e seções

proteção de seção só funciona quando a proteção de documentos está habilitada e somente a edição nos campos do formulário é permitida. Você pode proteger o documento usando o método Protect() do objeto Document:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Certifique-se de especificar o tipo correto de proteção e definir a senha desejada.

## Etapa 4: desabilitar a proteção para uma seção específica

Por padrão, todas as seções são protegidas, mas você pode desabilitar seletivamente a proteção para uma seção específica usando a propriedade ProtectedForForms do objeto Section:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Neste exemplo, a proteção está desativada para a primeira seção.

## Etapa 5: salve o documento

Por fim, salve o documento modificado:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para salvar o documento com seções irrestritas.

### Exemplo de código-fonte para seção irrestrita usando Aspose.Words for .NET

Aqui está o código-fonte completo para a seção irrestrita usando Aspose.Words for .NET:


```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Insira duas seções com algum texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// A proteção de seção só funciona quando a proteção do documento está ativada e somente a edição nos campos do formulário é permitida.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Por padrão, todas as seções estão protegidas, mas podemos desativar a proteção seletivamente.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Seguindo essas etapas, você poderá definir facilmente seções irrestritas em seu documento do Word com Aspose.Words for .NET.

## Conclusão

Neste tutorial, exploramos o recurso de seção irrestrita do Aspose.Words for .NET, que permite que seções específicas em um documento do Word permaneçam desprotegidas enquanto o resto do documento está protegido. Seguindo as etapas fornecidas, você pode definir facilmente seções em seu documento onde os usuários podem editar livremente o conteúdo, mantendo a proteção para outras seções. Aspose.Words for .NET oferece recursos poderosos para proteção e personalização de documentos, dando a você controle sobre as permissões de edição em seus documentos do Word.

### Perguntas frequentes para seção irrestrita em documento do Word

#### P: O que são seções irrestritas no Aspose.Words for .NET?

R: Seções irrestritas no Aspose.Words for .NET são seções específicas dentro de um documento do Word que não estão protegidas, mesmo que o restante do documento esteja protegido. Essas seções permitem que os usuários modifiquem o conteúdo delas, mantendo a proteção para as partes restantes do documento.

#### P: Como posso criar seções irrestritas usando Aspose.Words for .NET?

R: Para criar seções irrestritas em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Crie uma instância do`Document` aula e um`DocumentBuilder` objeto.
2.  Use o`DocumentBuilder` para adicionar conteúdo ao documento e inserir quebras de seção.
3.  Proteja o documento usando o`Protect` método do`Document` objeto, especificando o tipo de proteção e senha desejados.
4.  Desative a proteção para uma seção específica configurando o`ProtectedForForms` propriedade do correspondente`Section` opor-se a`false`.
5. Salve o documento modificado.

#### P: Posso ter várias seções irrestritas em um documento do Word?

 R: Sim, você pode ter várias seções irrestritas em um documento do Word. Ao desativar seletivamente a proteção para seções específicas usando o`ProtectedForForms` propriedade do`Section`objeto, você pode definir várias seções onde os usuários podem modificar livremente o conteúdo enquanto mantêm outras seções protegidas.

#### Q4. Posso remover a proteção de uma seção que estava inicialmente protegida?
 Sim, você pode remover a proteção de uma seção que foi inicialmente protegida configurando o`ProtectedForForms` propriedade do correspondente`Section` opor-se a`false`. Isso permite que os usuários editem o conteúdo dessa seção específica sem quaisquer restrições.

#### P: Quais tipos de proteção podem ser aplicados a um documento do Word?

R: Aspose.Words for .NET fornece vários tipos de proteção que podem ser aplicados a um documento do Word, incluindo:
- NoProtection: Nenhuma proteção é aplicada.
- AllowOnlyRevisions: os usuários só podem fazer revisões no documento.
- AllowOnlyComments: os usuários só podem adicionar comentários ao documento.
- AllowOnlyFormFields: os usuários só podem editar campos de formulário no documento.
- Somente leitura: o documento é somente leitura e nenhuma edição é permitida.



---
title: Permitir apenas proteção de campos de formulário em documentos do Word
linktitle: Permitir apenas proteção de campos de formulário em documentos do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar Aspose.Words for .NET para proteger documentos do Word e permitir apenas a edição de campos de formulário.
type: docs
weight: 10
url: /pt/net/document-protection/allow-only-form-fields-protect/
---
proteção de documentos é um recurso essencial ao processar palavras com arquivos em seu aplicativo C#. Com a biblioteca Aspose.Words para .NET, você pode proteger facilmente seus documentos e permitir apenas a edição de campos de formulário. Neste guia passo a passo, orientaremos você sobre como usar o código-fonte C# para permitir apenas a edição de campos de formulário usando o recurso Permitir apenas proteção de campos de formulário do Aspose.Words for .NET.

## Etapa 1: Configurando o diretório de documentos

O primeiro passo é definir o diretório do seu documento. Você deve especificar o caminho onde deseja salvar o documento protegido. Por exemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 2: Inserindo Seções e Texto

Em seguida, você precisa inserir seções e texto em seu documento. Use a classe DocumentBuilder fornecida por Aspose.Words para construir o conteúdo do seu documento. Aqui está um exemplo simples:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Neste exemplo, criamos um novo documento em branco e usamos o DocumentBuilder para adicionar uma linha de texto.

## Passo 3: Habilitando a Proteção de Documentos

 A proteção de documentos só funciona quando a proteção de documentos está ativada. Você pode ativar a proteção de documentos usando o`Protect` método da classe Document. Veja como:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Neste exemplo, habilitamos a proteção de documentos especificando o tipo de proteção `

AllowOnlyFormFields` e definindo uma senha.

## Etapa 4: permitir apenas campos de formulário

Agora que a proteção de documentos está habilitada, precisamos especificar que apenas a edição dos campos do formulário é permitida. Isso garante que os usuários só possam editar partes do documento que sejam campos de formulário. Veja como:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Certifique-se de substituir “senha” pela senha que você definiu anteriormente.

## Passo 5: Salvando o Documento Protegido

 Finalmente, você pode salvar o documento protegido usando o`Save` método da classe Document. Especifique o caminho completo do arquivo e o nome do arquivo desejado. Por exemplo :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Certifique-se de substituir “dataDir” pelo caminho para o diretório do seu documento.

### Exemplo de código-fonte para o recurso Permitir apenas proteção de campos de formulário usando Aspose.Words for .NET

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Insira duas seções com algum texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// A proteção de documento só funciona quando a proteção de documento está ativada e somente a edição nos campos do formulário é permitida.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Salve o documento protegido.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusão

Neste guia, exploramos como usar a biblioteca Aspose.Words para .NET para proteger um documento e permitir apenas a edição de campos de formulário. Seguindo as etapas fornecidas, você pode implementar facilmente essa funcionalidade em seu aplicativo C#. A proteção de documentos é essencial para garantir a segurança e a confidencialidade dos seus documentos.

### Perguntas frequentes sobre como permitir apenas campos de formulário protegidos em documentos do Word

#### P: O que é proteção de documentos no Aspose.Words for .NET?

R: A proteção de documentos no Aspose.Words for .NET é um recurso que permite proteger seus documentos restringindo certas ações, como edição, formatação ou modificação de conteúdo. Ajuda a manter a integridade e a confidencialidade dos seus documentos, evitando alterações não autorizadas.

#### P: Como posso proteger um documento e permitir que apenas os campos do formulário sejam editados usando Aspose.Words for .NET?

R: Para proteger um documento e permitir que apenas os campos do formulário sejam editados usando Aspose.Words for .NET, você pode seguir estas etapas:
1. Defina o caminho do diretório para o seu documento.
2.  Insira seções e texto em seu documento usando o`DocumentBuilder` aula.
3.  Ative a proteção de documentos usando o`Protect` método do`Document` classe, especificando o tipo de proteção como`AllowOnlyFormFields` e fornecendo uma senha.
4.  Salve o documento protegido usando o`Save` método do`Document` aula.

#### P: Posso inserir campos de formulário em um documento protegido usando Aspose.Words for .NET?

R: Sim, você pode inserir campos de formulário em um documento protegido usando Aspose.Words for .NET. A proteção de documentos com o`AllowOnlyFormFields` type permite que os usuários editem apenas os campos do formulário enquanto protegem o restante do conteúdo do documento. Você pode usar o`DocumentBuilder` class para inserir campos de formulário no documento antes de ativar a proteção.

#### P: Posso remover a proteção de um documento protegido?

 R: Sim, você pode remover a proteção de um documento protegido usando Aspose.Words for .NET. Para remover a proteção, você pode usar o`Unprotect` método do`Document` class e forneça a senha correta. Isto removerá a proteção e permitirá a edição irrestrita do documento.

#### P: É possível proteger um documento com vários tipos de proteção?

 R: Não, o Aspose.Words for .NET permite que apenas um tipo de proteção seja aplicado a um documento por vez. No entanto, o`AllowOnlyFormFields` tipo de proteção pode efetivamente restringir a edição de campos de formulário enquanto permite outros tipos de proteção, como`AllowOnlyComments` ou`AllowOnlyRevisions`para ser combinado com proteção de campo de formulário.

#### P: Posso definir senhas diferentes para diferentes tipos de proteção em um documento?

R: Não, o Aspose.Words for .NET permite que você defina uma única senha para proteção de documentos, independentemente do tipo de proteção. A mesma senha será usada para ativar e desativar a proteção de documentos.
---
title: 비밀번호로 문서 암호화
linktitle: 비밀번호로 문서 암호화
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 비밀번호로 문서를 암호화하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
C# 응용 프로그램에서 파일을 단어 처리할 때 문서 보안은 필수적입니다. .NET용 Aspose.Words 라이브러리를 사용하면 문서를 비밀번호로 암호화하여 쉽게 보호할 수 있습니다. 이 단계별 가이드에서는 DocSaveOptions 저장 옵션을 사용하여 문서를 암호화하기 위해 .NET C# 소스 코드용 Aspose.Words를 사용하는 방법을 안내합니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 .NET을 포함한 다양한 플랫폼에서 Word 문서를 생성, 편집, 변환 및 보호하는 강력한 라이브러리입니다. 텍스트 삽입, 서식 변경, 섹션 추가 등과 같은 문서 조작을 위한 다양한 기능을 제공합니다.

## 1단계: 문서 디렉터리 정의

첫 번째 단계는 암호화된 문서를 저장할 디렉터리를 설정하는 것입니다. 전체 디렉터리 경로를 지정해야 합니다. 예를 들어 :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 2단계: 문서 만들기 및 편집

그런 다음 문서를 만들고 내용을 추가할 수 있습니다. Aspose.Words에서 제공하는 DocumentBuilder 클래스를 사용하여 문서 콘텐츠를 빌드하세요. 예를 들어 :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

이 예에서는 새 빈 문서를 만든 다음 DocumentBuilder를 사용하여 "Hello World!"라는 텍스트를 작성합니다.

## 3단계: 녹음 옵션 구성

이제 문서의 저장 옵션을 구성해 보겠습니다. DocSaveOptions 클래스를 사용하여 저장 설정을 지정합니다. 예를 들어 :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

이 예에서는 새 DocSaveOptions 개체를 만들고 Password 속성을 "password"로 설정하여 이 암호로 문서를 암호화합니다.

## 4단계: "비밀번호로 문서 암호화" 기능 활성화

우리는 이미 옵션을 구성했습니다.

지정된 비밀번호로 등록하면 "비밀번호로 문서 암호화" 기능이 자동으로 활성화됩니다. 이렇게 하면 문서를 저장할 때 지정한 비밀번호로 문서가 암호화됩니다.

## 5단계: 문서 저장

마지막으로 Document 클래스의 Save 메서드를 사용하여 문서를 저장할 수 있습니다. 파일의 전체 경로와 원하는 파일 이름을 지정합니다. 예를 들어 :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

"dataDir"을 문서의 디렉터리 경로로 바꿔야 합니다.

### .NET용 Aspose.Words를 사용하여 "비밀번호로 문서 암호화" 기능을 갖춘 DocSaveOptions 저장 옵션의 소스 코드 예

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 만들기 및 편집
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// "암호로 문서 암호화" 기능으로 저장 옵션 구성
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// 지정된 옵션으로 문서를 저장합니다.
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## 결론

이 가이드에서는 DocSaveOptions 저장 옵션을 사용하여 .NET용 Aspose.Words 라이브러리를 사용하여 비밀번호로 문서를 암호화하는 방법을 설명했습니다. 제공된 단계를 따르고 제공된 C# 소스 코드를 사용하면 C# 애플리케이션에 이 기능을 쉽게 적용할 수 있습니다. 문서를 비밀번호로 암호화하면 문서 처리 시 기밀성과 보안이 보장됩니다.
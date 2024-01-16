---
title: 비밀번호로 Docx 암호화
linktitle: 비밀번호로 Docx 암호화
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 DOCX 파일을 비밀번호로 암호화하는 방법을 알아보세요. 문서 보안에 대한 전체 튜토리얼입니다.
type: docs
weight: 10
url: /ko/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
이 튜토리얼에서는 제공된 C# 소스 코드를 탐색하여 .NET용 Aspose.Words를 사용하여 DOCX 파일을 비밀번호로 암호화합니다. 이 기능을 사용하면 지정된 비밀번호로만 문서에 액세스할 수 있도록 하여 문서를 보호할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 문서 로드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 사용하고 로드할 DOCX 파일의 경로를 전달합니다.

## 3단계: OOXML 백업 옵션 구성

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

 이 단계에서는 새로운 생성을 통해 OOXML 저장 옵션을 구성합니다.`OoxmlSaveOptions` 물체. 우리는 다음을 설정하여 문서를 암호화하기 위해 원하는 비밀번호를 지정합니다.`Password` 속성을 사용자 정의 비밀번호로 설정하세요.

## 4단계: 비밀번호로 문서 암호화

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 이 마지막 단계에서는 다음을 사용하여 문서를 저장합니다.`Save` 메서드를 사용하여 출력 파일의 경로를 전달합니다.`.docx` 확장명과 지정된 저장 옵션이 함께 제공됩니다.

이제 소스 코드를 실행하여 DOCX 문서를 비밀번호로 암호화할 수 있습니다. 결과 파일은 "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx"라는 이름으로 지정된 디렉터리에 저장됩니다. 비밀번호는 암호화된 문서를 여는 데 필요하므로 안전하게 보관하세요.

### .NET용 Aspose.Words를 사용하여 Docx를 비밀번호로 암호화하기 위한 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 DOCX 파일을 비밀번호로 암호화하는 기능을 살펴보았습니다. 지정된 비밀번호로만 문서에 액세스할 수 있도록 하여 문서를 보호하는 방법을 배웠습니다.

문서 암호화는 민감한 정보를 보호하기 위한 필수적인 보안 조치입니다. .NET용 Aspose.Words 덕분에 우리는 이 기능을 애플리케이션에 쉽게 추가할 수 있습니다.

제공된 단계에 따라 Aspose.Words for .NET 프로젝트에 비밀번호 암호화를 통합하고 문서의 기밀성을 보장할 수 있습니다.

Aspose.Words for .NET에서 제공하는 다른 기능을 자유롭게 실험하여 고급 문서 조작 기능으로 애플리케이션을 강화해 보세요.

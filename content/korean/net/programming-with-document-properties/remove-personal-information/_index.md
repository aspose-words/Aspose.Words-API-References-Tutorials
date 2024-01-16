---
title: 개인정보 삭제
linktitle: 개인정보 삭제
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에서 개인 정보를 제거하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-properties/remove-personal-information/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서에서 개인 정보를 제거하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서에서 작성자 식별 데이터와 같은 민감한 개인 정보를 제거할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 개인 정보를 제거하려는 Word 문서를 업로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 개인정보 삭제

 이제 다음을 설정하여 개인 정보 제거를 활성화하겠습니다.`RemovePersonalInformation`재산`true`. 다음 코드를 사용하세요.

```csharp
doc.RemovePersonalInformation = true;
```

이 코드는 문서의 개인 정보 삭제를 활성화합니다.

## 4단계: 문서 저장

마지막으로 개인정보가 제거된 문서를 저장하겠습니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

이 코드는 개인 정보가 제거된 문서를 새 파일에 저장합니다.

### .NET용 Aspose.Words를 사용하여 개인 정보 제거에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 문서에서 개인 정보를 제거하는 방법을 배웠습니다. 이 튜토리얼에서 제공하는 단계별 가이드를 따르면 문서에서 중요한 정보를 쉽게 제거할 수 있습니다.
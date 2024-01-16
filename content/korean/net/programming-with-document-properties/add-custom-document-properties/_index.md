---
title: 사용자 정의 문서 속성 추가
linktitle: 사용자 정의 문서 속성 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에 사용자 정의 속성을 추가하는 방법을 단계별로 안내합니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-properties/add-custom-document-properties/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서에 사용자 정의 속성을 추가하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서에 사용자 정의 정보를 추가할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 사용자 정의 속성을 추가하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 사용자 정의 속성 추가

이제 문서에 사용자 정의 속성을 추가해 보겠습니다. 다음 코드를 사용하여 속성을 추가합니다.

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

이 코드는 먼저 사용자 정의 속성에 "Authorized" 속성이 이미 존재하는지 확인합니다. 존재하는 경우 프로세스가 중단됩니다. 그렇지 않으면 사용자 정의 속성이 문서에 추가됩니다.

### .NET용 Aspose.Words를 사용하여 사용자 정의 문서 속성 추가에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 문서에 사용자 정의 속성을 추가하는 방법을 배웠습니다. 이 튜토리얼에서 제공하는 단계별 가이드를 따르면 문서에 사용자 정의 속성을 쉽게 추가할 수 있습니다.
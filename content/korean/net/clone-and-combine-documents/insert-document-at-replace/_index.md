---
title: 교체 시 문서 삽입
linktitle: 교체 시 문서 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 교체 시 문서를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/clone-and-combine-documents/insert-document-at-replace/
---
이 튜토리얼에서는 Aspose.Words for .NET의 대체 시 문서 삽입 기능을 사용하여 대체할 때 다른 문서에 문서를 삽입하는 방법을 안내합니다. 소스 코드를 이해하고 문서 삽입을 수행하려면 아래 단계를 수행하십시오.

## 1단계: 기본 문서 로드

시작하려면 문서 디렉터리를 지정하고 기본 문서를 Document 객체에 로드하세요. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2단계: 검색 및 바꾸기 옵션 구성

이제 검색 방향을 지정하고 문서를 다른 문서에 삽입하기 위한 바꾸기 콜백을 지정하여 찾기 및 바꾸기 옵션을 구성하겠습니다. 방법은 다음과 같습니다.

```csharp
// 검색 및 바꾸기 옵션을 구성합니다.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## 3단계: 대체 메서드 호출

이제 구성된 옵션을 사용하여 지정된 텍스트를 찾아 빈 문자열로 바꾸는 바꾸기 메서드를 호출합니다. 방법은 다음과 같습니다.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### .NET용 Aspose.Words를 사용하여 대체 시 문서 삽입에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 대체할 때 문서 삽입 기능에 대한 전체 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// 찾기 및 바꾸기 옵션을 설정합니다.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// 교체 메소드를 호출하십시오.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words의 대체 시 문서 삽입 기능을 사용하여 대체하는 동안 다른 문서에 문서를 삽입하는 방법을 살펴보았습니다. 찾기 및 바꾸기 옵션을 구성하고 필요한 데이터를 제공하면 특정 자리 표시자를 다른 문서 템플릿이나 섹션의 콘텐츠로 바꿔 문서를 동적으로 조합할 수 있습니다. Aspose.Words for .NET은 복잡한 문서 조작 작업을 관리하는 강력하고 유연한 방법을 제공하여 문서 생성 및 콘텐츠 삽입 시나리오를 자동화하는 데 유용한 도구입니다.

### FAQ

#### Q: 교체 중에 문서를 다른 문서에 삽입하는 목적은 무엇입니까?

A: 바꾸는 동안 문서를 다른 문서에 삽입하면 특정 자리 표시자를 별도 문서의 내용으로 동적으로 바꿀 수 있습니다. 이 기능은 미리 정의된 다양한 문서 템플릿이나 섹션을 특정 자리 표시자로 결합하여 더 큰 문서를 조합하려는 경우 특히 유용합니다.

#### Q: .NET용 Aspose.Words를 사용하여 교체하는 동안 문서를 다른 문서에 어떻게 삽입합니까?

A: .NET용 Aspose.Words를 사용하여 교체하는 동안 문서를 다른 문서에 삽입하려면 다음 단계를 따르세요.
1. 자리 표시자가 포함된 기본 문서를 Document 개체에 로드합니다.
2. 문서 삽입을 처리하기 위한 검색 방향 및 바꾸기 콜백을 포함하여 찾기 및 바꾸기 옵션을 구성합니다.
3. 구성된 옵션을 사용하여 적절한 검색 패턴으로 교체 메소드를 호출하고 자리 표시자를 빈 문자열로 바꿉니다.

#### Q: 교체 중 삽입 동작을 사용자 정의할 수 있습니까?

A: 예, 사용자 지정 ReplacingCallback을 구현하여 교체 중 삽입 동작을 사용자 지정할 수 있습니다. IReplacingCallback 인터페이스에서 상속하면 자리 표시자를 바꿀 때 특정 요구 사항에 따라 문서가 삽입되고 병합되는 방식을 제어할 수 있습니다.

#### Q: 여러 자리 표시자를 다른 문서로 바꿀 수 있나요?

A: 예, 각 자리 표시자에 대한 적절한 검색 패턴을 지정하고 삽입할 해당 문서를 제공하여 여러 자리 표시자를 다른 문서로 바꿀 수 있습니다.
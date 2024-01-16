---
title: Word 문서의 옵션 비교
linktitle: Word 문서의 옵션 비교
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서 기능의 비교 옵션에 대한 C# 소스 코드를 설명하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/compare-documents/compare-options/
---
이 튜토리얼에서는 Aspose.Words for .NET에서 Word 문서의 옵션 비교 기능을 사용하는 방법을 설명합니다. 소스 코드를 이해하고 변경 사항을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서를 사용자 정의 옵션과 비교

 시작하려면 비교할 두 문서를 로드합니다. 이 예에서는`Clone()` 원본 문서의 복사본을 만드는 방법입니다. 방법은 다음과 같습니다.

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## 2단계: 비교 옵션 구성

 이제 다음을 생성하여 비교 옵션을 구성하겠습니다.`CompareOptions` 개체를 만들고 필요에 따라 다양한 속성을 설정합니다. 방법은 다음과 같습니다.

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## 3단계: 문서를 사용자 정의 옵션과 비교

 이제 우리는`Compare()` 두 문서를 비교하기 위해 사용자 정의 옵션을 전달하는 메서드입니다. 이 방법은 원본 문서의 변경 사항을 표시합니다. 방법은 다음과 같습니다.

```csharp
// 사용자 정의 옵션으로 문서 비교
docA.Compare(docB, "user", DateTime.Now, options);

// 문서가 동일한지 확인하세요.
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### .NET용 Aspose.Words를 사용하는 비교 옵션의 예제 소스 코드

다음은 .NET용 Aspose.Words의 옵션 비교 기능에 대한 전체 소스 코드입니다.

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

이 코드를 사용하면 .NET용 Aspose.Words와 비교할 때 특정 요소를 무시하는 사용자 정의 옵션을 사용하여 두 문서를 비교할 수 있습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words의 비교 옵션을 사용하여 두 문서를 비교할 때 비교 프로세스를 사용자 정의하는 방법을 배웠습니다. 다른 옵션을 지정하면 특정 요소를 무시하고 비교 프로세스를 더욱 유연하게 만들 수 있습니다. 이 기능을 사용하면 비교 프로세스를 더 효과적으로 제어하고 특정 요구 사항에 맞게 조정할 수 있습니다. Aspose.Words for .NET은 강력한 문서 비교 기능을 제공하므로 필요에 따라 특정 요소를 무시하면서 문서 간의 차이점을 쉽게 식별할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.Words에서 비교 옵션을 사용하는 목적은 무엇입니까?

A: .NET용 Aspose.Words의 비교 옵션을 사용하면 두 문서를 비교할 때 비교 프로세스를 사용자 정의할 수 있습니다. 이러한 옵션을 사용하면 서식 변경, 머리글 및 바닥글, 테이블, 필드, 설명, 텍스트 상자, 각주 등 비교 중에 무시할 요소를 지정할 수 있습니다.

#### Q: .NET용 Aspose.Words에서 비교 옵션을 어떻게 사용합니까?

A: .NET용 Aspose.Words에서 비교 옵션을 사용하려면 다음 단계를 따르세요.
1. 비교하려는 두 문서를 별도의 Document 개체로 로드합니다.
2.  사용`Clone()` 원본 문서의 복사본을 만드는 방법입니다.
3.  만들기`CompareOptions` 개체를 선택하고 해당 속성을 설정하여 비교 프로세스를 사용자 지정합니다. 비교 중에 무시할 요소를 지정할 수 있습니다.
4.  사용`Compare()` 문서 중 하나에 대한 메서드를 사용하고 다른 문서와 해당 문서를 전달합니다.`CompareOptions` 매개변수로 개체를 사용합니다. 이 방법은 지정된 옵션을 기반으로 문서를 비교하고 원본 문서의 변경 사항을 표시합니다.
5.  을 체크 해봐`Revisions` 원본 문서의 속성입니다. 개수가 0이면 지정된 옵션을 고려하여 문서가 동일하다는 의미입니다.

#### Q: CompareOptions에서 사용할 수 있는 일반적인 옵션은 무엇입니까?

A: CompareOptions에서 사용할 수 있는 일반적인 옵션은 다음과 같습니다.
- `IgnoreFormatting`: 서식 변경을 무시합니다.
- `IgnoreHeadersAndFooters`: 머리글과 바닥글의 변경 사항을 무시합니다.
- `IgnoreCaseChanges`: 대소문자 변경(대문자/소문자)을 무시합니다.
- `IgnoreTables`: 테이블의 변경 사항을 무시합니다.
- `IgnoreFields`: 필드의 변경 사항을 무시합니다.
- `IgnoreComments`: 댓글의 변경 사항을 무시합니다.
- `IgnoreTextboxes`텍스트 상자의 변경 사항을 무시합니다.
- `IgnoreFootnotes`: 각주의 변경 사항을 무시합니다.

#### Q: 문서 비교 중에 특정 요소에 대해 사용자 정의 옵션을 사용할 수 있습니까?

 A: 예, 문서 비교 중에 특정 요소에 대해 사용자 정의 옵션을 사용할 수 있습니다. 속성을 설정하여`CompareOptions` 따라서 비교 중에 무시할 요소와 고려할 요소를 선택할 수 있습니다.
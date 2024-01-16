---
title: 중복 스타일 정리
linktitle: 중복 스타일 정리
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에서 중복된 스타일을 정리하는 단계별 가이드입니다. 전체 소스 코드가 포함되어 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 중복 스타일을 정리하기 위한 C# 소스 코드를 단계별로 안내합니다. 이 기능은 문서에서 중복된 스타일을 제거하는 데 도움이 됩니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 정리하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 청소하기 전에 스타일 계산

청소를 진행하기 전에 문서에 있는 스타일 수를 계산합니다. 스타일 개수를 표시하려면 다음 코드를 사용하세요.

```csharp
Console.WriteLine(doc.Styles.Count);
```

이 문은 문서에 있는 스타일의 수를 표시합니다.

## 4단계: 중복된 스타일 정리

이제 문서에서 중복된 스타일을 정리해 보겠습니다. 정리를 수행하려면 다음 코드를 사용하십시오.

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 이 코드는 지정된 옵션을 사용하여 문서에서 중복된 스타일을 정리합니다. 이 예에서는`DuplicateStyle` 중복된 스타일을 정리하는 옵션.

## 5단계: 청소 후 스타일 개수 계산

청소를 마친 후에는 스타일 개수를 다시 세어 감소했는지 확인합니다. 새 스타일 개수를 표시하려면 다음 코드를 사용하세요.

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

이 명령문은 청소 후 남은 스타일 수를 표시합니다.

### .NET용 Aspose.Words를 사용하여 중복 스타일 정리에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// 정리 전 스타일 수입니다.
	Console.WriteLine(doc.Styles.Count);

	// 문서에서 중복된 스타일을 정리합니다.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//정리 후 스타일 수가 감소했습니다.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```
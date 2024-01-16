---
title: 사용하지 않는 스타일 및 목록 정리
linktitle: 사용하지 않는 스타일 및 목록 정리
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 문서에서 사용하지 않는 스타일과 목록을 정리하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

이 튜토리얼에서는 C# 소스 코드를 안내하여 .NET용 Aspose.Words를 사용하여 사용하지 않는 스타일과 목록을 정리합니다. 이 기능을 사용하면 문서에서 사용되지 않는 스타일과 목록을 제거할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 정리하려는 사용되지 않은 스타일과 목록이 포함된 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 정리하기 전에 스타일 및 목록 계산

정리하기 전에 문서에 있는 스타일과 목록의 수를 계산합니다. 카운터를 표시하려면 다음 코드를 사용하십시오.

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

이 지침은 청소 전 문서에 있는 스타일과 목록의 수를 보여줍니다.

## 4단계: 사용하지 않는 스타일 및 목록 정리

이제 문서에서 사용하지 않는 스타일과 목록을 정리해 보겠습니다. 정리를 수행하려면 다음 코드를 사용하십시오.

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 이 코드는 지정된 옵션을 사용하여 문서에서 사용되지 않는 스타일과 목록을 정리합니다. 이 예에서는`UnusedStyles` 사용하지 않는 스타일을 제거하고 비활성화하는 옵션`UnusedLists` 사용하지 않더라도 목록을 유지하는 옵션입니다.

## 5단계: 정리 후 스타일 및 목록 개수 계산

정리를 수행한 후 스타일과 목록을 다시 계산하여 축소되었는지 확인합니다. 새 카운터를 표시하려면 다음 코드를 사용하십시오.

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

이 지침은 청소 후 남은 스타일과 목록의 수를 보여줍니다.

### .NET용 Aspose.Words를 사용하여 사용하지 않는 스타일 및 목록 정리에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// 내장된 스타일과 결합되어 이제 문서에는 8개의 스타일이 있습니다.
	// 문서 내에 텍스트가 있으면 사용자 정의 스타일이 "사용됨"으로 표시됩니다.
	// 해당 스타일로 포맷되었습니다. 이는 우리가 추가한 4가지 스타일이 현재 사용되지 않음을 의미합니다.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//지정된 CleanupOptions에 따라 문서에서 사용되지 않는 스타일과 목록을 정리합니다.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 문서에서 사용하지 않는 스타일과 목록을 정리하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 이 기능을 자신의 문서에 쉽게 적용할 수 있습니다.


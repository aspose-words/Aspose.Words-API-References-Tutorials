---
title: 글꼴 폴더 설정
linktitle: 글꼴 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 글꼴 폴더 설정에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 글꼴 폴더를 설정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 사용할 글꼴 폴더를 지정하는 방법을 알게 될 것입니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집된 렌더링 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 글꼴 소스 설정
 그런 다음 다음을 사용하여 글꼴 소스를 설정할 수 있습니다.`FontSettings.DefaultInstance` 수업과`SetFontsSources()` 방법. 이 예에서는 시스템 글꼴 소스와 사용자 정의 폴더 글꼴 소스를 모두 사용하고 있습니다. 필요에 따라 사용자 정의 글꼴 폴더의 경로를 조정하십시오.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 3단계: 렌더링할 문서 로드
 이제 렌더링할 문서를 로드할 수 있습니다.`Document` 수업. 올바른 문서 경로를 지정하십시오.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4단계: 렌더링된 문서 저장
 마지막으로 다음을 사용하여 렌더링된 문서를 파일로 저장할 수 있습니다.`Save()` 의 방법`Document` 수업. 올바른 경로와 파일 이름을 지정하십시오.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### .NET용 Aspose.Words를 사용하여 글꼴 폴더 설정에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 글꼴 폴더를 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 문서를 렌더링할 때 사용할 글꼴 소스를 쉽게 지정할 수 있습니다. Aspose.Words는 문서의 글꼴을 사용한 단어 처리를 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 문서를 특정 요구에 맞게 렌더링할 때 사용되는 글꼴 소스를 제어하고 사용자 정의할 수 있습니다.

### FAQ

#### Q: Aspose.Words를 사용하여 Word 문서에서 글꼴 폴더를 어떻게 구성할 수 있나요?

A: Aspose.Words를 사용하여 Word 문서에서 글꼴 폴더를 구성하려면 API를 사용하여 문서를 생성하거나 편집할 때 사용할 사용자 정의 글꼴 폴더를 지정할 수 있습니다. 이렇게 하면 Word에서 올바르게 렌더링하는 데 필요한 글꼴을 찾을 수 있습니다.

#### Q: Aspose.Words를 사용하여 Word 문서에 사용자 지정 글꼴을 추가할 수 있습니까?

A: 예, Aspose.Words를 사용하면 Word 문서에 사용자 정의 글꼴을 추가할 수 있습니다. API를 사용하면 특정 글꼴을 문서에 포함시켜 해당 글꼴이 최종 사용자 시스템에 설치되지 않은 경우에도 올바르게 표시되도록 할 수 있습니다.

#### Q: Word 문서에 필수 글꼴이 없으면 어떻게 됩니까?

A: 필요한 글꼴이 Word 문서에 누락된 경우 Aspose.Words는 이 문제를 감지하고 해결 옵션을 제공할 수 있습니다. 누락된 글꼴을 대체 글꼴로 대체하거나 누락된 글꼴을 문서에 포함하여 올바르게 볼 수 있도록 선택할 수 있습니다.

#### Q: Aspose.Words를 사용하여 Word 문서에서 사용자 정의 글꼴을 제거하려면 어떻게 해야 합니까?

A: Aspose.Words를 사용하여 Word 문서에서 사용자 정의 글꼴을 제거하려면 API를 사용하여 문서를 정리하고 더 이상 필요하지 않은 사용자 정의 글꼴을 제거할 수 있습니다. 이렇게 하면 파일 크기가 줄어들고 글꼴 관리가 더 쉬워집니다.

#### Q: Word 문서에서 글꼴 폴더를 구성하는 것이 중요합니까?

A: 예, 사용된 글꼴이 올바르게 표시되도록 하려면 Word 문서에서 글꼴 폴더를 구성하는 것이 중요합니다. Aspose.Words와 함께 사용할 사용자 정의 글꼴 폴더를 지정하면 Word 문서를 올바르게 렌더링하는 데 필요한 글꼴을 사용할 수 있습니다.
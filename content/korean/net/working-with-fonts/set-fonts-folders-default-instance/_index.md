---
title: 글꼴 폴더 기본 인스턴스 설정
linktitle: 글꼴 폴더 기본 인스턴스 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 기본 글꼴 폴더를 설정하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-fonts-folders-default-instance/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서를 렌더링할 때 기본 글꼴 폴더를 설정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 사용할 기본 글꼴 폴더를 설정하는 방법을 알게 됩니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집된 렌더링 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 기본 글꼴 폴더 설정
 그런 다음 다음을 사용하여 기본 글꼴 폴더를 설정할 수 있습니다.`FontSettings.DefaultInstance` 수업과`SetFontsFolder()`방법. 기본 폴더로 사용하려는 글꼴 폴더의 경로를 지정합니다.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## 3단계: 렌더링할 문서 로드
 이제 렌더링할 문서를 로드할 수 있습니다.`Document` 수업. 올바른 문서 경로를 지정하십시오.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4단계: 렌더링된 문서 저장
 마지막으로 다음을 사용하여 렌더링된 문서를 파일로 저장할 수 있습니다.`Save()` 의 방법`Document` 수업. 올바른 경로와 파일 이름을 지정하십시오.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### .NET용 Aspose.Words를 사용하여 글꼴 폴더 기본 인스턴스 설정에 대한 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 렌더링할 때 기본 글꼴 폴더를 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 문서를 렌더링할 때 기본 폴더로 사용할 글꼴 폴더를 쉽게 지정할 수 있습니다. Aspose.Words는 문서의 글꼴을 사용한 단어 처리를 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 문서를 특정 요구에 맞게 렌더링할 때 사용되는 글꼴 소스를 제어하고 사용자 정의할 수 있습니다.

### FAQ

#### Q: Aspose.Words에서 기본 글꼴 폴더를 어떻게 설정합니까?

 A: Aspose.Words에서 기본 글꼴 폴더를 설정하려면 다음을 사용해야 합니다.`Fonts` 수업과`SetFontsFolders` 사용자 정의 글꼴 폴더 위치를 지정하는 방법입니다.

#### Q: 기본 글꼴 폴더 설정이 Aspose.Words로 처리되는 모든 Word 문서에 영향을 미치나요?

A: 예, 기본 글꼴 폴더를 설정하면 Aspose.Words로 처리되는 모든 Word 문서에 영향을 줍니다. 기본 글꼴 폴더를 설정하면 Aspose.Words는 이 위치를 사용하여 모든 문서에서 글꼴을 검색합니다.

#### Q: Aspose.Words에서 여러 기본 글꼴 폴더를 설정할 수 있나요?

 A: 예, Aspose.Words에서 여러 기본 글꼴 폴더를 설정할 수 있습니다. 다음을 사용하여 사용자 정의 글꼴 폴더의 위치를 지정하면 됩니다.`SetFontsFolders` 의 방법`Fonts` 수업.

#### Q: 현재 Aspose.Words에 설정된 기본 글꼴 폴더를 어떻게 확인할 수 있나요?

 A: 현재 Aspose.Words에 정의된 기본 글꼴 폴더를 확인하려면 다음을 사용할 수 있습니다.`GetFolders` 의 방법`Fonts` 클래스를 사용하여 구성된 글꼴 폴더의 위치를 가져옵니다.

#### 질문: 기본 글꼴 폴더를 설정하면 내 Word 문서에서 사용자 지정 글꼴을 사용할 수 있습니까?

A: 예, 기본 글꼴 폴더를 설정하면 Word 문서에서 사용자 지정 글꼴을 사용할 수 있습니다. 지정된 폴더에 글꼴을 배치하기만 하면 Aspose.Words가 문서를 생성하거나 조작할 때 글꼴을 사용합니다.
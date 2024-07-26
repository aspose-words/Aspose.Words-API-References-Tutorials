---
title: 텍스트 입력 양식 필드를 텍스트로 내보내기
linktitle: 텍스트 입력 양식 필드를 텍스트로 내보내기
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 텍스트 입력 양식 필드를 일반 텍스트로 내보내는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## 소개

그렇다면 .NET용 Aspose.Words의 세계로 뛰어들고 계십니까? 멋진 선택입니다! 텍스트 입력 양식 필드를 텍스트로 내보내는 방법을 배우려면 올바른 위치에 있습니다. 이제 막 시작하는 분이든 기술을 연마하는 분이든 이 가이드는 여러분이 알아야 할 모든 것을 안내해 드립니다. 시작해 볼까요?

## 전제조건

핵심적인 내용을 살펴보기 전에 원활하게 진행하는 데 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.

-  .NET용 Aspose.Words: 다음에서 최신 버전을 다운로드하고 설치하세요.[여기](https://releases.aspose.com/words/net/).
- IDE: Visual Studio 또는 모든 C# 개발 환경.
- 기본 C# 지식: 기본 C# 구문 및 객체 지향 프로그래밍 개념을 이해합니다.
- 문서: 샘플 Word 문서(`Rendering.docx`) 텍스트 입력 양식 필드가 있습니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이는 모든 것이 원활하게 작동하도록 하는 빌딩 블록과 같습니다.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

자, 이제 네임스페이스가 준비되었으므로 작업에 뛰어들겠습니다!

## 1단계: 프로젝트 설정

코드를 시작하기 전에 프로젝트가 올바르게 설정되었는지 확인하겠습니다.

## 프로젝트 만들기

1. Visual Studio 열기: Visual Studio 또는 선호하는 C# 개발 환경을 열어 시작합니다.
2.  새 프로젝트 만들기: 다음으로 이동합니다.`File > New > Project` . 선택하다`Console App (.NET Core)` 또는 기타 관련 프로젝트 유형.
3.  프로젝트 이름 지정: 프로젝트에 다음과 같이 의미 있는 이름을 지정하십시오.`AsposeWordsExportExample`.

## Aspose.Words 추가하기

1.  NuGet 패키지 관리: 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고`Manage NuGet Packages`.
2.  Aspose.Words 검색: NuGet 패키지 관리자에서 다음을 검색합니다.`Aspose.Words`.
3.  Aspose.Words 설치: 다음을 클릭하세요.`Install` 프로젝트에 Aspose.Words 라이브러리를 추가합니다.

## 2단계: Word 문서 로드

이제 프로젝트가 설정되었으므로 텍스트 입력 양식 필드가 포함된 Word 문서를 로드해 보겠습니다.

1. 문서 디렉터리 지정: 문서가 저장된 디렉터리의 경로를 정의합니다.
2.  문서 로드:`Document` Word 문서를 로드하는 클래스입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 내보내기 디렉터리 준비

내보내기 전에 내보내기 디렉터리가 준비되었는지 확인하겠습니다. 여기에 HTML 파일과 이미지가 저장됩니다.

1. 내보내기 디렉터리 정의: 내보낸 파일이 저장될 경로를 지정합니다.
2. 디렉토리 확인 및 정리: 디렉토리가 존재하고 비어 있는지 확인하십시오.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## 4단계: 저장 옵션 구성

여기서 마법이 일어납니다. 텍스트 입력 양식 필드를 일반 텍스트로 내보내려면 저장 옵션을 설정해야 합니다.

1.  저장 옵션 생성: 새로 초기화`HtmlSaveOptions` 물체.
2.  텍스트 내보내기 옵션 설정:`ExportTextInputFormFieldAsText`재산`true`.
3. 이미지 폴더 설정: 이미지가 저장될 폴더를 정의합니다.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## 5단계: 문서를 HTML로 저장

마지막으로 구성된 저장 옵션을 사용하여 Word 문서를 HTML 파일로 저장해 보겠습니다.

1. 출력 경로 정의: HTML 파일이 저장될 경로를 지정합니다.
2.  문서 저장:`Save` 의 방법`Document`문서를 내보내는 클래스입니다.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 텍스트 입력 양식 필드를 일반 텍스트로 성공적으로 내보냈습니다. 이 가이드에서는 이 작업을 달성하기 위한 명확한 단계별 접근 방식을 제공해야 합니다. 연습이 완벽함을 기억하세요. Aspose.Words로 무엇을 할 수 있는지 알아보려면 다양한 옵션과 설정을 계속 실험해 보세요.

## FAQ

### 동일한 방법을 사용하여 다른 유형의 양식 필드를 내보낼 수 있습니까?

 예, 다양한 속성을 구성하여 다른 유형의 양식 필드를 내보낼 수 있습니다.`HtmlSaveOptions` 수업.

### 내 문서에 이미지가 있으면 어떻게 되나요?

 이미지는 지정된 이미지 폴더에 저장됩니다. 반드시 설정하세요.`ImagesFolder` 에 있는 재산`HtmlSaveOptions`.

### Aspose.Words에 대한 라이선스가 필요합니까?

 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/) 또는 라이센스를 구매하세요[여기](https://purchase.aspose.com/buy).

### 내보낸 HTML을 사용자 정의할 수 있나요?

 전적으로! Aspose.Words는 HTML 출력을 사용자 정의할 수 있는 다양한 옵션을 제공합니다. 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/words/net/) 상세 사항은.

### Aspose.Words는 .NET Core와 호환됩니까?

예, Aspose.Words는 .NET Core, .NET Framework 및 기타 .NET 플랫폼과 호환됩니다.

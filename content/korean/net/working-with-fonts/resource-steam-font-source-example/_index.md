---
title: 리소스 Steam 글꼴 소스 예
linktitle: 리소스 Steam 글꼴 소스 예
second_title: Aspose.Words 문서 처리 API
description: 리소스 스트림 글꼴 소스를 사용하여 .NET용 Aspose.Words에 사용자 정의 글꼴을 로드하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/resource-steam-font-source-example/
---

이 튜토리얼에서는 .NET용 Aspose.Words와 함께 리소스 흐름 글꼴 소스를 사용하는 방법을 안내합니다. 이 글꼴 소스를 사용하면 리소스 스트림에서 글꼴을 로드할 수 있으며, 이는 사용자 정의 글꼴을 응용 프로그램에 통합하려는 경우 유용할 수 있습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 업로드 및 리소스 스트림 글꼴 소스 설정
 다음으로, 다음을 사용하여 문서를 로드하겠습니다.`Document` 클래스를 사용하여 리소스 스트림 글꼴 소스를 설정합니다.`FontSettings.DefaultInstance.SetFontsSources()` 수업. 이렇게 하면 Aspose.Words가 리소스 스트림에서 글꼴을 찾을 수 있습니다.

```csharp
// 문서 로드 및 리소스 스트림 글꼴 소스 설정
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## 3단계: 문서 저장
마지막으로 문서를 저장하겠습니다. 글꼴은 지정된 리소스 스트림에서 로드되어 문서에 포함됩니다.

```csharp
// 문서 저장
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### .NET용 Aspose.Words를 사용하는 Resource Steam 글꼴 소스 예제의 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## 결론
이 자습서에서는 .NET용 Aspose.Words와 함께 리소스 흐름 글꼴 소스를 사용하는 방법을 배웠습니다. 이 기능을 사용하면 리소스 피드에서 글꼴을 로드할 수 있으며, 이는 사용자 정의 글꼴을 문서에 포함하려는 경우에 유용합니다. 다양한 글꼴을 실험하고 글꼴 관리를 위해 Aspose.Words가 제공하는 가능성을 탐색해 보세요.

### FAQ

#### Q: 리소스 스트림의 글꼴을 Aspose.Words에 어떻게 로드할 수 있나요?

 A: Aspose.Words의 리소스 스트림에서 글꼴을 로드하려면 다음을 사용할 수 있습니다.`FontSettings` 수업과`SetFontsSources` 리소스 스트림을 사용하여 글꼴 소스를 지정하는 방법입니다. 이를 통해 실제 파일이 아닌 리소스 스트림에서 직접 글꼴을 로드할 수 있습니다.

#### Q: Aspose.Words에서 글꼴 소스를 지정하기 위해 리소스 스트림을 사용하면 어떤 이점이 있나요?

A: 리소스 스트림을 사용하여 글꼴 소스를 지정하면 다음과 같은 몇 가지 장점이 있습니다.
- 애플리케이션에 내장된 리소스에서 글꼴을 로드할 수 있으므로 문서를 쉽게 배포하고 배포할 수 있습니다.
- 필요에 따라 다양한 리소스 스트림에서 글꼴을 로드할 수 있으므로 글꼴 관리의 유연성이 향상됩니다.

#### Q: .NET 애플리케이션의 리소스 스트림에 글꼴을 추가하려면 어떻게 해야 합니까?

 A: .NET 애플리케이션의 리소스 스트림에 글꼴을 추가하려면 프로젝트 리소스에 글꼴 파일을 포함해야 합니다. 그런 다음 개발 플랫폼에 특정한 방법을 사용하여 이러한 글꼴 파일에 액세스할 수 있습니다(예:`GetManifestResourceStream` 사용하여`System.Reflection` 네임스페이스).

#### Q: 다양한 리소스 스트림의 여러 글꼴을 단일 Aspose.Words 문서에 로드할 수 있습니까?

 A: 예, 다양한 리소스 스트림의 여러 글꼴을 단일 Aspose.Words 문서에 로드하는 것이 전적으로 가능합니다. 다음을 사용하여 여러 글꼴 소스를 지정할 수 있습니다.`SetFontsSources` 의 방법`FontSettings` 클래스를 사용하여 각 글꼴에 적합한 리소스 스트림을 제공합니다.

#### Q: Aspose.Words에 글꼴을 로드하는 데 어떤 유형의 리소스 스트림을 사용할 수 있나요?

A: .NET 애플리케이션에 내장된 리소스 스트림, 외부 파일의 리소스 스트림, 데이터베이스의 리소스 스트림 등과 같은 다양한 유형의 리소스 스트림을 사용하여 Aspose.Words에 글꼴을 로드할 수 있습니다. 적절한 것을 제공해야 합니다. 귀하의 설정과 필요에 따라 리소스 흐름이 달라집니다.
---
title: 페이지 저장 콜백
linktitle: 페이지 저장 콜백
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서의 각 페이지를 별도의 PNG 이미지로 저장하는 방법을 자세하고 단계별 가이드를 통해 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-imagesaveoptions/page-saving-callback/
---
## 소개

안녕하세요! Word 문서의 각 페이지를 개별 이미지로 저장해야 할 필요성을 느껴본 적이 있나요? 큰 보고서를 쉽게 이해할 수 있는 비주얼로 나누고 싶거나, 미리 보기를 위한 썸네일을 만들어야 할 수도 있습니다. 이유가 무엇이든 Aspose.Words for .NET을 사용하면 이 작업이 아주 쉬워집니다. 이 가이드에서는 문서의 각 페이지를 개별 PNG 이미지로 저장하기 위한 페이지 저장 콜백을 설정하는 과정을 안내해 드리겠습니다. 바로 시작해 볼까요!

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Words: 아직 설치하지 않았다면 여기에서 다운로드하여 설치하세요.[여기](https://releases.aspose.com/words/net/).
2. Visual Studio: 어느 버전이든 괜찮지만 이 가이드에서는 Visual Studio 2019를 사용하겠습니다.
3. C#에 대한 기본 지식: 따라가려면 C#에 대한 기본적인 이해가 필요합니다.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 가져와야 합니다. 이렇게 하면 전체 네임스페이스를 매번 입력하지 않고도 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1단계: 문서 디렉토리 설정

좋습니다. 문서 디렉토리 경로를 정의하는 것으로 시작하겠습니다. 여기에 입력 Word 문서가 있고 출력 이미지가 저장될 곳입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드

다음으로, 처리하려는 문서를 로드합니다. 문서("Rendering.docx")가 지정된 디렉토리에 있는지 확인하세요.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3단계: 이미지 저장 옵션 구성

이미지 저장 옵션을 구성해야 합니다. 이 경우, 페이지를 PNG 파일로 저장합니다.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 여기,`PageSet` 저장할 페이지 범위를 지정하고`PageSavingCallback` 사용자 정의 콜백 클래스를 가리킵니다.

## 4단계: 페이지 저장 콜백 구현

이제 각 페이지가 어떻게 저장되는지 처리하는 콜백 클래스를 구현해 보겠습니다.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 이 클래스는 다음을 구현합니다.`IPageSavingCallback` 인터페이스 및 내부`PageSaving` 이 방법을 사용하면 저장된 각 페이지에 대한 명명 패턴을 정의할 수 있습니다.

## 5단계: 문서를 이미지로 저장

마지막으로 구성된 옵션을 사용하여 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## 결론

이제 Aspose.Words for .NET을 사용하여 Word 문서의 각 페이지를 별도의 PNG 이미지로 저장하는 페이지 저장 콜백을 성공적으로 설정했습니다. 이 기술은 페이지 미리보기 만들기부터 보고서의 개별 페이지 이미지 생성까지 다양한 애플리케이션에 매우 유용합니다. 

즐거운 코딩 되세요!

## 자주 묻는 질문

### PNG 이외의 형식으로 페이지를 저장할 수 있나요?  
 예, JPEG, BMP, TIFF 등의 다양한 형식으로 페이지를 저장할 수 있습니다.`SaveFormat` ~에`ImageSaveOptions`.

### 특정 페이지만 저장하고 싶다면 어떻게 해야 하나요?  
 저장하려는 페이지를 조정하여 지정할 수 있습니다.`PageSet` 매개변수`ImageSaveOptions`.

### 이미지 품질을 사용자 정의할 수 있나요?  
 물론입니다! 다음과 같은 속성을 설정할 수 있습니다.`ImageSaveOptions.JpegQuality` 출력 이미지의 품질을 제어합니다.

### 대용량 문서를 효율적으로 처리하려면 어떻게 해야 하나요?  
대용량 문서의 경우 메모리 사용량을 효과적으로 관리하기 위해 페이지를 일괄적으로 처리하는 것이 좋습니다.

### Aspose.Words for .NET에 대한 자세한 정보는 어디에서 찾을 수 있나요?  
 확인해보세요[선적 서류 비치](https://reference.aspose.com/words/net/) 포괄적인 가이드와 예시를 보려면 여기를 클릭하세요.
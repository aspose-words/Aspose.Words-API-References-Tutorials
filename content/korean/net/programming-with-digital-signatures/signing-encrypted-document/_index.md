---
title: 암호화된 Word 문서 서명
linktitle: 암호화된 Word 문서 서명
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 암호화된 단어 문서에 디지털 서명하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/signing-encrypted-document/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 암호화된 단어 문서에 서명하는 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 해독 암호를 사용하여 암호화된 Word 문서에 디지털 서명을 할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 서명 옵션 설정

SignOptions 클래스의 인스턴스를 만들고 암호 해독 비밀번호를 설정합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

암호화된 문서에 대해 올바른 복호화 비밀번호를 지정했는지 확인하세요.

## 2단계: 인증서 로드

CertificateHolder 클래스를 사용하여 서명 인증서를 로드하는 것부터 시작하세요.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

인증서 및 관련 비밀번호의 올바른 경로를 지정하십시오.

## 3단계: 암호화된 문서에 서명하기

DigitalSignatureUtil 클래스를 사용하여 암호화된 문서에 서명합니다.

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

암호화된 문서, 서명된 문서 및 인증서에 대한 올바른 경로를 지정하십시오.

### .NET용 Aspose.Words를 사용하여 암호화된 문서에 서명하기 위한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 암호화된 문서에 서명하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
다음 단계를 따르면 Aspose.Words for .NET을 사용하여 암호화된 Word 문서에 쉽게 서명할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 암호화된 Word 문서에 서명하는 프로세스를 살펴보았습니다. 암호 해독 비밀번호와 서명 인증서를 제공함으로써 암호화된 문서에 디지털 서명을 추가할 수 있습니다. 암호화된 문서에 서명하면 진위성과 무결성이 보장되어 추가 보안 계층이 제공됩니다. Aspose.Words for .NET을 사용하면 암호화된 문서에 서명하고 Word 파일의 보안과 신뢰성을 유지할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.Words의 문서 서명이란 무엇입니까?

A: Aspose.Words for .NET의 문서 서명은 Word 문서의 진위성, 무결성 및 부인 방지를 보장하기 위해 Word 문서에 디지털 서명하는 프로세스를 의미합니다. 인증서를 사용하여 문서에 디지털 서명을 추가하는 작업이 포함됩니다.

#### Q: 암호화된 Word 문서란 무엇입니까?

A: 암호화된 Word 문서는 비밀번호를 사용하여 암호화된 문서입니다. 암호화는 문서의 내용을 뒤섞어 올바른 암호 해독 없이는 읽을 수 없도록 하여 문서의 내용을 보호하는 보안 조치입니다.

#### Q: .NET용 Aspose.Words를 사용하여 암호화된 Word 문서에 어떻게 서명할 수 있나요?

A: .NET용 Aspose.Words를 사용하여 암호화된 Word 문서에 서명하려면 서명 인증서와 함께 암호 해독 암호를 제공해야 합니다. 다음과 같이하세요:
1.  복호화 비밀번호를 설정하세요.`SignOptions` 물체.
2.  다음을 사용하여 서명 인증서를 로드합니다.`CertificateHolder` 수업.
3.  사용`DigitalSignatureUtil.Sign` 필요한 매개변수를 제공하여 암호화된 문서에 서명하는 방법입니다.

#### Q: 암호화된 문서에 서명하는 목적은 무엇입니까?

A: Aspose.Words for .NET을 사용하여 암호화된 문서에 서명하면 문서가 암호화된 경우에도 문서에 디지털 서명을 추가할 수 있습니다. 이는 추가적인 보안 계층을 제공하고 암호화된 콘텐츠의 신뢰성과 무결성을 보장합니다. 이를 통해 수신자는 문서의 원본을 확인하고 변조를 감지할 수 있습니다.

#### Q: 복호화 비밀번호를 제공하지 않고 암호화된 문서에 서명할 수 있나요?

A: 아니요. 암호화된 문서에 서명하려면 올바른 암호 해독 비밀번호를 제공해야 합니다. 디지털 서명을 적용하기 전에 문서의 암호화된 내용에 액세스하고 수정하려면 암호 해독 암호가 필요합니다.

#### Q: 모든 인증서를 사용하여 암호화된 Word 문서에 서명할 수 있습니까?

A: .NET용 Aspose.Words를 사용하여 암호화된 Word 문서에 서명하려면 유효한 X.509 인증서가 필요합니다. 인증서는 신뢰할 수 있는 인증 기관(CA)에서 얻거나 자체 서명된 인증서를 테스트 목적으로 사용할 수 있습니다.

#### Q: 동일한 인증서를 사용하여 암호화된 여러 Word 문서에 서명할 수 있습니까?

 A: 예, 동일한 인증서를 사용하여 암호화된 여러 Word 문서에 서명할 수 있습니다. 다음을 사용하여 인증서를 로드한 후`CertificateHolder` 클래스를 사용하여 암호화된 여러 문서에 서명할 수 있습니다.

#### Q: 서명된 암호화 문서의 디지털 서명을 확인할 수 있나요?

 A: 예, Aspose.Words for .NET은 서명된 암호화 문서의 디지털 서명을 확인하는 기능을 제공합니다. 당신은 사용할 수 있습니다`DigitalSignatureUtil.Verify` 디지털 서명의 유효성과 진위 여부를 확인하는 방법.

#### Q: Aspose.Words for .NET은 암호화된 문서 서명을 위해 어떤 파일 형식을 지원합니까?

 A: .NET용 Aspose.Words는 DOCX 파일 형식의 암호화된 Word 문서 서명을 지원합니다. 다음을 사용하여 암호화된 DOCX 파일에 서명할 수 있습니다.`DigitalSignatureUtil.Sign` 필요한 복호화 비밀번호 및 인증서와 함께 방법을 제공합니다.

#### Q: 암호화된 문서에 서명하면 암호화에 어떤 영향을 미치나요?

A: Aspose.Words for .NET을 사용하여 암호화된 문서에 서명해도 문서 암호화에는 영향을 미치지 않습니다. 암호화는 그대로 유지되며 암호화된 콘텐츠에 디지털 서명이 추가됩니다. 디지털 서명은 문서에 적용된 암호화를 손상시키지 않으면서 추가적인 보안과 확인을 제공합니다.
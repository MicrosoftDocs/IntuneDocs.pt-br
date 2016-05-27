---
# required metadata

title: Você encontra erros ao tentar registrar seu dispositivo iOS no Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Você encontra erros ao tentar registrar seu dispositivo iOS no Intune

A tabela a seguir lista os erros que você pode encontrar durante o registro do seu dispositivo iOS no Intune. Compartilhe este link com o administrador de TI. 

|Mensagem de erro|Problema|O que dizer ao administrador de TI|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|DeviceCapReached|Você já tem muitos dispositivos móveis registrados.|Antes de registrar outro dispositivo móvel, o usuário deve remover um de seus dispositivos móveis registrados atualmente no Portal da Empresa.|
|APNSCertificateNotValid|Há um problema com o certificado que permite que seus dispositivos móveis se comuniquem com a rede da empresa.<br /><br />Entre em contato com seus administradores de TI e informe que recebeu a mensagem **APNSCertificateNotValid** durante a tentativa de registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|Serviço de notificação de envio (APNS) da Apple fornece um canal para chegar aos dispositivos iOS registrados. Se as etapas para obter um certificado APNS não tiverem sido executadas, ou se o certificado APNS estiver vencido, então as tentativas de registro falharão e essa mensagem será exibida.<br /><br />Examine as informações sobre como configurar usuários em [Sync Active Directory and add users to Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) (Sincronizar o Active Directory e adicionar usuários ao Intune) e em [Organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) (Organizando usuários e dispositivos).|
|AccountNotOnboarded|Há um problema com o certificado que permite que seus dispositivos móveis se comuniquem com a rede da empresa.<br /><br />Entre em contato com seus administradores de TI e informe que recebeu a mensagem **APNSNotOnboarded** durante a tentativa de registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|Serviço de notificação de envio (APNS) da Apple fornece um canal para chegar aos dispositivos iOS registrados. Se as etapas para obter um certificado APNS não tiverem sido executadas, ou se o certificado APNS estiver vencido, então as tentativas de registro falharão e essa mensagem será exibida.<br /><br />Para obter mais informações, examine [Set up iOS and Mac management with Microsoft Intune](/Intune/Deployuse/set-up-ios-and-mac-management-with-microsoft-intune) (Configurar gerenciamento de iOS e Mac com o Microsoft Intune).|
|DeviceTypeNotSupported|Você pode ter tentado registrar usando um dispositivo não iOS. O tipo de dispositivo móvel que você está tentando registrar não tem suporte.<br /><br />Verifique se o dispositivo está executando o iOS versão 7.1 ou posterior.<br /><br />Entre em contato com seus administradores de TI e informe que recebeu a mensagem **DeviceTypeNotSupported** durante a tentativa de registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|Verifique se o dispositivo do usuário está executando o iOS versão 7.1 ou posterior.|
|UserLicenseTypeInvalid|Não é possível registrar seu dispositivo móvel porque sua conta de usuário ainda não é um membro de um grupo de usuário necessário.<br /><br />Entre em contato com seus administradores de TI e informe que recebeu a mensagem **UserLicenseTypeInvalid** durante a tentativa de registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|Antes que os usuários possam registrar seus dispositivos, eles devem ser membro do grupo de usuários à direita. Esta mensagem indica que eles têm o tipo de licença errado para a autoridade de gerenciamento de dispositivo móvel designado. Por exemplo, se o Intune tiver sido designado como a autoridade de gerenciamento de dispositivo móvel e eles estiverem usando uma licença do System Center 2012 R2 Configuration Manager, eles receberão esse erro.<br /><br />Examine os itens a seguir para obter mais informações:<br /><br />Consulte [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) (Configurar gerenciamento de iOS e Mac com o Microsoft Intune) e as informações sobre como configurar usuários em [Sync Active Directory and add users to Intune (Sincronizar o Active Directory e adicionar usuários ao Intune)] (/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) e em [Organizing users and devices](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) (Organizando usuários e dispositivos).|
|MdmAuthorityNotDefined|Seu administrador de TI precisa configurar o modo como os dispositivos móveis são gerenciados na sua empresa.<br /><br />Entre em contato com seus administradores de TI e informe que recebeu a mensagem **MdmAuthorityNotDefined** durante a tentativa de registrar seu dispositivo móvel e peça que eles vejam a resolução nesta tabela.|A autoridade de gerenciamento de dispositivo móvel não foi designada no Intune.<br /><br />Consulte o item nº 1 na seção "Step 6: Enroll mobile devices and install an app" (Etapa 6: Registrar dispositivos móveis e instalar um aplicativo) em [Get started with a 30-day trial of Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) (Começar com uma avaliação de 30 dias do Microsoft Intune).|

### Consulte também
[Using your iOS or Mac OS X device with Intune](using-your-ios-or-mac-os-x-device-with-intune.md)

<!--HONumber=May16_HO1-->


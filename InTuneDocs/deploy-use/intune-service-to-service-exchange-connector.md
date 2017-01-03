---
title: Exchange Connector para Exchange Online | Microsoft Intune
description: "Conecte o Intune ao serviço Office 365 Exchange para dar suporte ao MDM (gerenciamento de dispositivo móvel) do Exchange ActiveSync."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: b6d67391b50954e591817610164d8fe80fda8fd5


---

# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Configurar o Service to Service Connector do Intune para o Exchange Online

Use essas informações para conectar o serviço Microsoft Intune e Exchange Online ou o novo Exchange Online Dedicado. Para determinar se o seu ambiente Exchange Online Dedicado está na versão **nova** ou **herdada**, entre em contato com seu gerente de conta. O Intune oferece suporte apenas a uma conexão do conector do Exchange de qualquer tipo por assinatura.

## <a name="service-to-service-connector-requirements"></a>Requisitos para o Service to Service Connector
O **Service to Service Connector** tem suporte apenas para o Exchange Online ou para o novo Exchange Online Dedicado e não tem requisitos de infraestrutura local.

|Requisito|Mais informações|
|---------------|--------------------|
|Exchange Online configurado e em execução|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autoridade de gerenciamento de dispositivo móvel| [Configurar a autoridade de gerenciamento de dispositivo móvel para o Microsoft Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Versão do Microsoft Exchange|Serviço Exchange Online ou o novo Exchange Online Dedicado|
|Sincronização do Active Directory|Antes de usar o Conector do Intune, é preciso [configurar a sincronização do Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) para que os usuários e grupos de segurança locais sejam sincronizados com sua instância do Azure Active Directory.|

### <a name="exchange-cmdlet-requirements"></a>Requisitos de cmdlets do Exchange

Também é preciso criar uma conta de usuário do Exchange Online que seja usada pelo Intune Exchange Connector. A conta deve ter permissão para usar o console de administração do Intune e executar os seguintes cmdlets necessários do Windows PowerShell Exchange:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Configurar o Conector de Serviço a Serviço

1. Abra o [console de administração do Microsoft Intune](http://manage.microsoft.com) com uma conta de usuário com direitos de administrador do Exchange e permissões para os cmdlets [descritos acima](#exchange-cmdlet-requirements). O Microsoft Intune usa o endereço de email do usuário conectado no momento para configurar a conexão.

2.  No painel de atalhos do espaço de trabalho, selecione **ADMIN**>**Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange** > **Configurar Conexão com o Exchange**.
![Configurar página do Service to Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  Na página **Configurar a Conexão do Exchange**, clique em **Configurar o Conector de Serviços**.


O Service to Service Connector configura e sincroniza automaticamente seu ambiente do Exchange Online ou do novo Exchange Online Dedicado.

## <a name="validate-your-exchange-connection"></a>Validar a sua conexão do Exchange

Após configurar com êxito o Exchange Connector, vá para o [console de administração do Microsoft Intune](http://manage.microsoft.com). Selecione **Admin**> **Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange**. Em seguida, confirme se os detalhes fornecidos aparecem em **Informações sobre Conexão com o Exchange**.

Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.



<!--HONumber=Dec16_HO2-->


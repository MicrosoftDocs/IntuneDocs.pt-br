---
title: "O dispositivo não tem um certificado obrigatório | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d6fcfac7c8bd469f5163ec9b4017ae8c3d486428
ms.openlocfilehash: 92f698cb0616838b4dac5b1a889ad4569d94b956

---


# <a name="your-device-is-missing-a-required-certificate"></a>Falta ao dispositivo um certificado necessário

## <a name="whats-a-certificate"></a>O que é um certificado?

[Criptografia](https://technet.microsoft.com/en-us/library/cc962030.aspx) a ciência de fornecer segurança para informações. Tradicionalmente, a criptografia tem sido usada para passar mensagens codificadas, a fim de [garantir que a comunicação é mantida em sigilo](https://technet.microsoft.com/en-us/library/cc962019.aspx). Em sua forma mais simples, a criptografia substitui ou transpõe letras para criar uma mensagem codificada ilegível, embaralhada ou oculta. Somente alguém com uma chave de decodificação, ou _certificado_, pode converter a mensagem codificada de volta ao seu formato original e legível. Seu dispositivo Android usa certificados com o Intune para garantir que a comunicação entre o dispositivo e seus recursos organizacionais, como email e documentos, é mantida segura de uma extremidade, pelo ar, até a outra.

Se o dispositivo Android não estiver registrado no Intune e não tiver um certificado específico exigido pelo administrador de TI, você não conseguirá entrar no aplicativo Portal da Empresa. Quando você tentar entrar, verá a seguinte mensagem:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

A primeira etapa que você deve tentar é verificar se o dispositivo [não tem um certificado que normalmente vem pré-instalado nele](your-device-is-missing-a-preinstalled-certificate-android.md). Se isso não funcionar, o administrador de TI poderá [exigir a instalação de um segundo certificado para segurança adicional](your-device-is-missing-an-IT-required-certificate-android.md).

Ainda precisa de ajuda? Entre em contato com o administrador de TI. Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).



<!--HONumber=Jan17_HO1-->


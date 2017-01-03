---
title: "Usar políticas para simplificar o gerenciamento do computador Windows | Microsoft Intune"
description: "Descreve as políticas de gerenciamento de computador Windows e as configurações para o Microsoft Intune Center."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 10/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 1c6800ea3fde39603478437de6da7200ecae5afb


---

# <a name="use-policies-to-simplify-windows-pc-management"></a>Usar políticas para simplificar o gerenciamento de computador Windows

Computadores Windows que executam o cliente de software do Intune podem ser gerenciados por meio das políticas de **Gerenciamento do Computador** do Intune. Use as políticas de **Gerenciamento do Computador** do Intune para definir as configurações no Microsoft Intune Center, controlar as atualizações em computadores e configurar o Firewall do Windows para computadores.

![Modelo de políticas para computadores Windows](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>Gerenciar o Microsoft Intune Center
Os usuários veem o cliente de software do Intune como o **Microsoft Intune Center**. O Microsoft Intune Center permite que os usuários:

-   Obtenham aplicativos a partir do portal da empresa.

-   Procurem atualizações.

-   Gerencie o Endpoint Protection do Microsoft Intune.

-  Solicitem assistência remota.

O Microsoft Intune Center é instalado em todos os computadores gerenciados. Você pode definir as seguintes configurações em uma política do Intune e elas são exibidas para os usuários no Microsoft Intune Center:

|Configuração de política|Detalhes|
|------------------|--------------------|
|**Nome**|O nome do administrador que gerencia o computador.<br />Comprimento máximo: 40 caracteres|
|**Número do telefone**|O número do telefone do administrador que gerencia o computador.<br />Comprimento máximo: 20 caracteres|
|**Endereço de email**|O endereço de email do administrador que gerencia o computador.<br />Comprimento máximo: 40 caracteres|
|**Nome do site**|O nome do site de suporte para os usuários.<br />>Comprimento máximo: 40 caracteres|
|**URL do site**|A URL do site de suporte.<br />Comprimento máximo: 150 caracteres|
|**Observações**|Uma observação que é exibida para os usuários.<br />Comprimento máximo: 120 caracteres|

Consulte os seguintes recursos para obter informações sobre as políticas e configurações que você pode definir para computadores Windows:

- [Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) – essas políticas fazem os computadores gerenciados procurar e baixar atualizações de software da Microsoft e de terceiros. Essas atualizações não incluem atualizações de SO (por exemplo, atualizar do Windows 7 para o Windows 10 ou atualizar de uma versão do Windows 10 para uma versão posterior).

- [Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) – essas configurações incluem agendas de verificação e ações a serem tomadas quando um malware for detectado.

- [Ajudar a proteger computadores Windows usando políticas de Firewall do Windows no Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) – essas políticas simplificam a administração de configurações do Firewall do Windows nos computadores gerenciados.


### <a name="see-also"></a>Consulte também

[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)



<!--HONumber=Nov16_HO4-->


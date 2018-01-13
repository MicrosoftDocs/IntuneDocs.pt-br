---
title: "Logs da política de proteção do aplicativo"
titlesuffix: Azure portal
description: "Este tópico descreve o registro das configurações da política de proteção de aplicativo armazenadas nos logs de aplicativo."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 11/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4CD5EE94-7BA6-4F59-8E28-1EBCA7CA6436
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2b281a6b618e945750b5d5dec278e4ddc6166276
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2017
---
# <a name="review-app-protection-logs-in-the-managed-browser"></a>Examine os logs de proteção de aplicativo no Managed Browser

Você pode acessar os logs habilitando o Modo de Diagnóstico do Intune para um aplicativo em um cliente móvel. A tabela a seguir mostra o nome e uma explicação das configurações registradas no log.

## <a name="app-protection-policy-settings"></a>Configurações de política de proteção de aplicativo

| Nome                        | Valores possíveis                                                                                                                                                                                                                                                                                           | Configuração no Portal de Gerenciamento de Aplicativos Móveis do Intune                                                                                                                            |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AccessRecheckOfflineTimeout | x minutos                                                                                                                                                                                                                                                                                                   | [Acesso] Verificar novamente os requisitos de acesso – Período de Cortesia Offline<br>Observação: esse é período de tempo antes que os requisitos de acesso ao aplicativo sejam verificados novamente, se o dispositivo estiver offline.             |
| AccessRecheckOnlineTimeout  | _x_ minutos                                                                                                                                                                                                                                                                                                   | [Acesso] Verificar novamente os requisitos de acesso - Tempo limite.<br>Observação: esse é período de tempo antes que os requisitos de acesso ao aplicativo sejam verificados novamente após a inicialização do aplicativo, se o dispositivo estiver offline. |
| AppPinDisabled              | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Acesso] Desabilitar o PIN do aplicativo quando o PIN do dispositivo for gerenciado.                                                                                                                                     |
| AppSharingFromLevel         | 0 = Nenhum aplicativo<br>1 = Aplicativos gerenciados<br>2 = Qualquer aplicativo.                                                                                                                                                                                                                                                              | [Realocação de Dados] Permitir que este aplicativo receba dados de outros aplicativos.                                                                                                                        |
| AppSharingToLevel           | 0 = Nenhum aplicativo<br>1 = Aplicativos gerenciados<br>2 = Qualquer aplicativo.                                                                                                                                                                                                                                                              | [Realocação de Dados] Permitir que este aplicativo transfira dados para outros aplicativos.                                                                                                                         |
| AuthenticationEnabled       | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Acesso] Exigir credenciais corporativas para acesso em vez de um PIN.                                                                                                                      |
| ClipboardSharingLevel       | 0 = Bloqueado<br>1 = Aplicativos gerenciados.<br>2 = Aplicativos gerenciados com colagem.<br>3 = Qualquer aplicativo                                                                                                                                                                                                                            | [Realocação de dados] Restringir recortar, copiar e colar com outros aplicativos.                                                                                                                         |
| ContactSyncDisabled         | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Realocação de dados] Desabilitar a sincronização de contatos.                                                                                                                                                 |
| DataBackupDisabled          | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Realocação de dados] Impedir backups do iTunes e iCloud.                                                                                                                                     |
| DeviceComplianceEnabled     | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Acesso] Impedir que aplicativos gerenciados sejam executados em dispositivos com jailbreak ou root.                                                                                                                |
| DisableShareSense           | N/D                                                                                                                                                                                                                                                                                                         | N/D: não ativamente usado pelo serviço Intune.                                                                                                                                                |
| FileEncryptionLevel         | 0 = Quando o dispositivo estiver bloqueado<br>1 = Quando o dispositivo estiver bloqueado e houver arquivos abertos<br>2 = Após a reinicialização do dispositivo<br>3 = Usar configurações do dispositivo.                                                                                                                                                                      | [Realocação de dados] Criptografar dados do aplicativo.                                                                                                                                                      |
| FileSharingSaveAsDisabled   | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Realocação de Dados] Impedir "Salvar como"                                                                                                                                                     |
| IntuneIdentityUPN           | UPN do usuário MAM do Intune.                                                                                                                                                                                                                                                                                  | N/D                                                                                                                                                                                     |
| ManagedBrowserRequired      | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Realocação de Dados] Restringir a exibição de conteúdo da Web no aplicativo Intune Managed Browser.                                                                                                     |
| ManagedLocations            | Um valor que representa o número de locais de armazenamento gerenciado no qual o aplicativo pode salvar os dados. <br>1 = OneDrive<br>2 = SharePoint<br>3 = OneDrive e SharePoint<br>32 = Armazenamento Local<br>33 = Armazenamento Local & OneDrive<br>34 = Armazenamento Local & SharePoint<br>35 = Armazenamento Local, OneDrive e SharePoint | [Realocação de Dados] Selecione em quais serviços de armazenamento os dados corporativos podem ser salvos.                                                                                                          |
| MinAppVersion               | ”0.0” = sem versão de aplicativo mínima<br>qualquer outra coisa = versão mínima do aplicativo                                                                                                                                                                                                                                       | [Acesso] Exigir versão mínima do aplicativo.                                                                                                                                                    |
| MinAppVersionWarning        | ”0.0” = sem versão de aplicativo mínima.<br>qualquer outra coisa = versão mínima do aplicativo.                                                                                                                                                                                                                                       | [Acesso] Exigir versão mínima do aplicativo (somente aviso)                                                                                                                                     |
| MinOsVersion                | ”0.0” = sem versão mínima do SO<br>qualquer outra coisa = versão mínima do SO                                                                                                                                                                                                                                         | [Acesso] Exigir o sistema operacional iOS mínimo.                                                                                                                                           |
| MinOsVersionWarning         | ”0.0” = sem versão mínima do SO<br>qualquer outra coisa = versão mínima do SO                                                                                                                                                                                                                                         | [Acesso] Exigir o sistema operacional iOS mínimo (Somente aviso).                                                                                                                            |
| MinSDKVersion               | ”0.0” = sem versão mínima do SDK<br>qualquer outra coisa = versão mínima do SO.                                                                                                                                                                                                                                        | [Acesso] Exigir versão mínima do SDK de política de proteção de aplicativo do Intune.                                                                                                                       |
| PINCharacterType            | N/D                                                                                                                                                                                                                                                                                                         | N/D                                                                                                                                                                                     |
| PINEnabled                  | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Acesso] Exigir PIN para acesso                                                                                                                                                         |
| PINMinLength                | x caracteres                                                                                                                                                                                                                                                                                                | [Acesso] Comprimento do PIN                                                                                                                                                                     |
| PINNumRetry                 | x tentativas                                                                                                                                                                                                                                                                                                  | [Acesso] Número de tentativas antes da redefinição do PIN                                                                                                                                            |
| PrintingBlocked             | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Realocação de dados] Desabilitar impressão                                                                                                                                                      |
| SimplePINAllowed            | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Acesso] Permitir PIN simples                                                                                                                                                               |
| TouchIDEnabled              | 0 = Não<br>1 = Sim                                                                                                                                                                                                                                                                                           | [Acesso] Permitir a impressão digital em vez de PIN (iOS 8+).                                                                                                                                      |

## <a name="next-steps"></a>Próximas etapas

 - Para saber mais sobre as políticas de proteção do aplicativo, veja [Quais são as políticas de proteção do aplicativo?](app-protection-policy.md)
 - O Intune oferece várias ferramentas para ajudar você a solucionar problemas em seu ambiente. Para saber mais, confira [Usar o portal de solução de problemas para ajudar os usuários](help-desk-operators.md).
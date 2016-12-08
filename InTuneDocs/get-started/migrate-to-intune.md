---
title: Migrar para o Intune | Microsoft Intune
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: jeffgilb
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: c5adeb2164a55d029c9d7f86490092a72f04f126


---

# <a name="migrate-to-intune"></a>Migrar para o Intune


A migração para o Intune em sua solução de gerenciamento de mobilidade empresarial existente pode seguir a sequência geral de etapas a seguir:

![Etapas de migração para o Intune](./media/migrate-intune-steps.png)

## <a name="notify-users"></a>Notificar os usuários

Quando estiver confiante de que a implantação piloto do Intune atingiu seus requisitos, comunique-se com os usuários sobre a migração futura de seus dispositivos ao Intune. Mensagens de email, instruções e [cartazes](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) podem ajudar a definir as expectativas e fornecer detalhes de registro, os usuários de etapas necessárias para manter a conectividade contínua para aplicativos e recursos da empresa. Verifique se que sua equipe de suporte está pronta para ajudar os usuários no processo de migração.

## <a name="modify-your-existing-enterprise-mobility-management-solution"></a>Modificar sua solução de gerenciamento de mobilidade empresarial existente

Dependendo de como você planeja lidar com políticas de acesso condicional entre sua solução de gerenciamento de mobilidade empresarial existente e o Intune, você precisará desabilitar as políticas de acesso condicional existentes. Você vai desabilitar as políticas de acesso condicional existentes OU definir o escopo delas para não incluir usuários/dispositivos que você está prestes a migrar para o Intune.  Não é necessário ter ambos o Intune e a solução de gerenciamento de mobilidade empresarial existente aplicando políticas de acesso condicional para os mesmos usuários/dispositivos.

## <a name="enable-intune-conditional-access-policy-optional"></a>Habilitar a política de acesso condicional do Intune (opcional)

Se você decidiu aplicar imediatamente as políticas de acesso condicional sem um período de cortesia para a migração de dispositivos, habilite as políticas de acesso condicional no Intune nesta etapa.  Certifique-se de que essa decisão é tenha sido bem comunicada aos seus usuários e sua equipe de suporte técnico.  Se os dispositivos não estiverem registrados no Intune e não forem compatíveis com as políticas do Intune, os usuários não poderão acessar recursos corporativos até que eles se registrarem no Intune e os dispositivos forem compatíveis com as políticas do Intune.

## <a name="unenrolling-devices-from-your-existing-enterprise-mobility-management-solution"></a>Cancelar o registro de dispositivos da sua solução de gerenciamento de mobilidade empresarial existente

O registro dos dispositivos devem ser cancelados de sua solução de gerenciamento de mobilidade empresarial existente antes da inscrição no Intune. Nossa recomendação é permitir que os usuários não registrem seus próprios dispositivos para a melhor experiência de usuário.  Certifique-se de seguir as diretrizes de cancelamento de registro do provedor de solução para certificar-se de remover usuários e dispositivos de sua plataforma, garantindo o mínimo de interrupção possível para os usuários finais.

## <a name="enrolling-devices-in-intune"></a>Registrar dispositivos no Intune

Usuários programados para a migração devem imediatamente se registrar no Intune para recuperar ou evitar a perda de acesso aos aplicativos, email e recursos corporativos. Se você tiver configurado o acesso condicional e os usuários tentarem se conectar ao email antes de registrar no Intune, seu acesso será bloqueado e um email de registro os saudará. Este email os guia no registro de seu dispositivo no Intune.  Como alternativa, os usuários podem registrar no Intune por meio do aplicativo de Portal da Empresa do Intune ou nativamente no sistema operacional Windows 8.1 e Windows 10 Mobile. Consulte [O que dizer a seus usuários finais sobre como usar o Microsoft Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) para obter diretrizes adicionais sobre as etapas de registro por plataforma.

## <a name="configure-intune-conditional-access-optional"></a>Configurar o acesso condicional com o Intune (opcional)

Se você tiver concedido de um período de cortesia para a imposição de acesso condicional, habilite as políticas de acesso condicional no Intune para iniciar a imposição quando o período de cortesia concedido e comunicado aos seus usuários finais expirar. Isso exigirá que todos os dispositivos atendam aos requisitos da política de acesso condicional do Intune imediatamente.

## <a name="enroll-remaining-devices-and-users"></a>Registrar usuários e dispositivos restantes

Agora que você habilitou o acesso condicional, todos os usuários devem registrar-se no Intune e atender às políticas de conformidade da sua organização para obter acesso aos recursos corporativos. Se você já migrou seus usuários em um registro em fases (não ao mesmo tempo), repita as etapas acima até que todos os usuários e dispositivos sejam registrados e gerenciados pelo Intune.

## <a name="retire-the-previous-enterprise-mobility-management-solution"></a>Desativar a solução de gerenciamento de mobilidade empresarial anterior

Depois que tiver migrado todos os seus usuários e dispositivos Intune e validado que as migrações Intune foram bem-sucedidas, você pode desativar a solução de gerenciamento de mobilidade empresarial anterior e/ou cancelar a assinatura do serviço. Certifique-se de seguir as diretrizes do provedor de solução para certificar-se de remover quaisquer requisitos de infraestrutura desnecessários e cancelar assinaturas/licenças corretamente.

## <a name="additional-migration-resources"></a>Recursos de migração adicionais

Você precisa de ajuda adicional com a migração para o Intune? Fornecemos opções assistência especializada para ajudar a garantir que a migração esteja livre de problemas:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Serviços de Consultoria da Microsoft](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Suporte técnico e não técnico do Intune](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Fórum do Microsoft Intune no TechNet](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## <a name="get-a-downloadable-copy-of-this-guide"></a>Obtenha uma cópia deste guia

Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387).



<!--HONumber=Nov16_HO4-->


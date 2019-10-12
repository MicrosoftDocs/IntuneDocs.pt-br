---
title: Solução de problemas com políticas no Microsoft Intune – Azure | Microsoft Docs
description: Veja como usar o recurso de solução de problemas internos e leia sobre problemas ou Problemas comuns e suas resoluções ao usar perfis de configuração e políticas de conformidade no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2afdd358af19c28ff18e4e6e65839d7e314996b1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734265"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>Solucionar problemas de políticas e de perfis e no Intune

O Microsoft Intune inclui alguns recursos internos de solução de problemas. Use esses recursos para ajudar a solucionar problemas de políticas de conformidade e perfis de configuração em seu ambiente.

Este artigo lista algumas técnicas de solução de problemas comuns e descreve alguns problemas que podem ocorrer.

## <a name="check-tenant-status"></a>Verificar status do locatário
Verifique o [status do locatário](../fundamentals/tenant-status.md) e confirme se a assinatura está ativa. Você também pode exibir detalhes de incidentes e avisos ativos que podem afetar sua política ou implantação de perfil.

## <a name="use-built-in-troubleshooting"></a>Usar a solução de problemas interna

1. Na [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), selecione **Solucionar problemas**:

    ![No Intune, vá para Ajuda e Suporte e selecione Solucionar problemas](./media/troubleshoot-policies-in-microsoft-intune/help-and-support-troubleshoot.png)

2. Escolha **Selecionar usuário** > selecione o usuário com um problema > **Selecionar**.
3. Confirme que ambos a **Licença do Intune** e o **Status da conta** mostram verificações verdes:

    ![No Intune, selecione o usuário e confirme se o status da conta e a licença do Intune mostram marcas de verificações verdes para o status](./media/troubleshoot-policies-in-microsoft-intune/account-status-intune-license-show-green.png)

    **Links Úteis**:

    - [Atribuir licenças para que os usuários possam registrar dispositivos](../fundamentals/licenses-assign.md)
    - [Adicionar usuários ao Intune](../fundamentals/users-add.md)

4. Sob **Dispositivos**, localize o dispositivo com um problema. Examine as colunas diferentes:

    - **Gerenciado**: para um dispositivo receber políticas de conformidade ou de configuração, essa propriedade deve mostrar **MDM** ou **EAS/MDM**.

        - Se **Gerenciados** não está definido como **MDM** ou **EAS/MDM**, o dispositivo não está registrado. Ele não recebe as políticas de conformidade ou de configuração até que seja registrado.

        - Políticas de proteção de aplicativo (gerenciamento de aplicativos móveis) não exigem que os dispositivos sejam registrados. Para obter mais informações, veja [criar e atribuir políticas de proteção de aplicativo](../apps/app-protection-policies.md).

    - **Tipo de Junção do Azure AD**: deve ser definido como **Workplace** ou **AzureAD**.
 
        - Se essa coluna é **Não Registrado**, pode haver um problema com o registro. Normalmente, cancelar o registro do dispositivo e registrá-lo novamente resolve esse estado.

    - **Em conformidade com o Intune**: deve ser **Sim**. Se **Não** é mostrado, pode haver um problema com as políticas de conformidade, ou o dispositivo não está se conectando ao serviço do Intune. Por exemplo, o dispositivo pode estar desativado ou pode não ter uma conexão de rede. Eventualmente, o dispositivo se torna não compatível possivelmente após 30 dias.

        Para mais informações, consulte [introdução às políticas de conformidade do dispositivo](../protect/device-compliance-get-started.md).

    - **Em conformidade com Azure AD**: deve ser **Sim**. Se **Não** é mostrado, pode haver um problema com as políticas de conformidade, ou o dispositivo não está se conectando ao serviço do Intune. Por exemplo, o dispositivo pode estar desativado ou pode não ter uma conexão de rede. Eventualmente, o dispositivo se torna não compatível possivelmente após 30 dias.

        Para mais informações, consulte [introdução às políticas de conformidade do dispositivo](../protect/device-compliance-get-started.md).

    - **Último check-in**: deve ser uma data e hora recentes. Por padrão, os dispositivos do Intune fazem check-in a cada 8 horas.

        - Se o **Último check-in** for há mais de 24 horas, pode haver um problema com o dispositivo. Um dispositivo que não faz check-in não pode receber as políticas do Intune.

        - Para forçar o check-in:
            - Em dispositivos Android, abra o aplicativo Portal da Empresa > **Dispositivos** > Escolha o dispositivo na lista > **Verificar configurações de dispositivo**.
            - Em dispositivos iOS, abra o aplicativo Portal da Empresa > **Dispositivos** > Escolha o dispositivo na lista > **Verificar configurações**.

        - Em um dispositivo Windows, abra as **Configurações** > **Contas** > **Acesso corporativo ou de estudante** > Selecione a conta ou registro MDM > **Info** > **sincronização**.

    - Selecione o dispositivo para ver informações específicas de política.

        **Conformidade do dispositivo** mostra os estados de políticas de conformidade atribuídos ao dispositivo.

        **Configuração do dispositivo** mostra os estados de políticas de configuração atribuídos ao dispositivo.

        Se as políticas esperadas não são mostradas em **Conformidade do dispositivo** ou **Configuração do dispositivo**, as políticas não são direcionadas corretamente. Abra a política e atribua a política para este usuário ou dispositivo.

        **Estados de Política**:

        - **Não se Aplica**: não há suporte para essa política nesta plataforma. Por exemplo, políticas de iOS não funcionam no Android. As políticas do Samsung KNOX não funcionam em dispositivos do Windows.
        - **Conflito**: há uma configuração existente no dispositivo que o Intune não pode substituir. Ou você implantou duas políticas com a mesma configuração usando valores diferentes.
        - **Pendente**: o dispositivo ainda não fez a verificação no Intune para obter a política. Ou o dispositivo recebeu a política, mas não relatou o status para o Intune.
        - **Erros**: pesquisar erros e possíveis resoluções em [Solucionar problemas de acesso de recursos da empresa](../fundamentals/troubleshoot-company-resource-access-problems.md).

        **Links Úteis**: 

        - [Maneiras de implantar políticas de conformidade do dispositivo](../protect/device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
        - [Monitorar políticas de conformidade do dispositivo](../protect/compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Você não tem certeza se um perfil foi aplicado corretamente

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Dispositivos** > **Todos os dispositivos** > selecione o dispositivo > **Configuração do dispositivo**. 

    Todos os dispositivos listam seus perfis. Cada perfil tem um **Status**. O status se aplica quando todos os perfis atribuídos, incluindo requisitos de hardware e restrições do sistema operacional, são considerados em conjunto. Os status possíveis incluem:

    - **Em conformidade**: o dispositivo recebeu o perfil e relata ao Intune que ele está em conformidade com a configuração.

    - **Não aplicável**: a configuração do perfil não é aplicável. Por exemplo, configurações de email para dispositivos iOS não se aplicam a um dispositivo Android.

    - **Pendente**: o perfil é enviado para o dispositivo, mas não relatou o status para o Intune. Por exemplo, a criptografia no Android exige que o usuário habilite a criptografia e, portanto, pode ser mostrada como pendente.

**Link útil**: [Monitorar perfis de configuração de dispositivo](../configuration/device-profile-monitor.md)

> [!NOTE]
> Quando duas políticas com diferentes níveis de restrição aplicam-se ao mesmo dispositivo ou usuário, a política mais restritiva é aplicada.

## <a name="policy-troubleshooting-resources"></a>Recursos de solução de problemas de políticas

- [Solução de problemas de políticas do Ios ou Android que não se aplicam a dispositivos](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-tip-Troubleshooting-iOS-or-Android-policies-not-applying/ba-p/280154) (abre outro site da Microsoft)
- [Solucionando problemas de falhas de política do Windows 10 Intune](https://blogs.technet.microsoft.com/configmgrdogs/2018/08/09/troubleshooting-windows-10-intune-policy-failures/) (abre um blog)
- [Solucionar problemas de configurações personalizadas do CSP para Windows 10](https://support.microsoft.com/en-us/help/4055338/troubleshoot-csp-setting-windows-10-computer-intune) (abre outro site da Microsoft)
- [Política de MDM do Windows 10 política de grupo vs Intune](https://blogs.technet.microsoft.com/cbernier/2018/04/02/windows-10-group-policy-vs-intune-mdm-policy-who-wins/) (abre outro site da Microsoft)

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Alerta: falha ao salvar regras de acesso ao Exchange

**Problema**: você recebe o alerta **Falha ao salvar as regras de acesso ao Exchange** no console do administrador.

Se você criar políticas no workspace de Políticas do Exchange Local (Console de Administração), mas estiver usando o O365, as configurações definidas para a política não serão impostas pelo Intune. No alerta, observe a origem da política. No workspace de Políticas do Exchange Local, exclua as regras herdadas. Elas são regras globais do Exchange no Intune para o Exchange local e não são relevantes para o O365. Em seguida, crie uma nova política para o O365.

[Solucionar problemas do Conector do Exchange local do Intune](../protect/troubleshoot-exchange-connector.md) pode ser um bom recurso.

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Não é possível alterar as políticas de segurança para dispositivos registrados

Os dispositivos Windows Phone não permitem que as políticas de segurança definidas com uso de MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas. Por exemplo, você define uma **Senha com um número mínimo de caracteres** igual a 8 e, em seguida, tenta reduzi-la a 4. A política mais restritiva já foi aplicada ao dispositivo.

Dispositivos Windows 10 não podem remover políticas de segurança quando você não atribui a política (parar a implantação). Talvez seja necessário deixar a política atribuída e, em seguida, alterar as configurações de segurança de volta para os valores padrão.

Dependendo da plataforma do dispositivo, se você quer alterar a política para um valor menos seguro, pode ser necessário redefinir as políticas de segurança.

Por exemplo, no Windows 8.1, na área de trabalho, passe o dedo da direita para a esquerda para abrir a barra **Botões**. Escolha **Configurações** > **Painel de Controle** > **Contas de Usuário**. À esquerda, selecione o link **Redefinir Políticas de Segurança** e, em seguida, escolha **Redefinir Políticas**.

Para aplicar uma política menos restritiva a outras plataformas, como Android, iOS e Windows Phone 8.1, pode ser necessário desativá-los e registrá-los novamente.

[Solucionar problemas de registro de dispositivo](../enrollment/troubleshoot-device-enrollment-in-intune.md) pode ser um bom recurso.

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Computadores usando o cliente de software do Intune – portal clássico

> [!NOTE]
> Esta seção se aplica ao portal clássico. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Erros relacionados à política do Microsoft Intune em policyplatform.log

Para computadores com Windows gerenciados com o cliente de software do Intune, erros de política no arquivo `policyplatform.log` podem ser resultados de configurações não padrão no UAC (Controle de Conta de Usuário) do Windows no dispositivo. Algumas configurações de UAC não padrão podem afetar as instalações de cliente do Microsoft Intune e a execução da política.

#### <a name="resolve-uac-issues"></a>Resolver problemas do UAC

1. Desative o computador. Veja [Remover dispositivos](../remote-actions/devices-wipe.md).

2. Espere 20 minutos para o software cliente ser removido.

    > [!NOTE]
    > Não tente remover o cliente em Programas e Recursos.

3. No menu Iniciar, digite **UAC** para abrir as configurações de Controle de Conta de Usuário.

4. Mova o controle deslizante de notificação para a configuração padrão.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>ERRO: Não é possível obter o valor do computador, 0x80041013

Ocorrerá se a hora do sistema local estiver fora de sincronia por cinco minutos ou mais. Se a hora no computador local estiver fora de sincronia, transações seguras falharão porque os carimbos de data/hora serão inválidos.

Para resolver esse problema, defina a hora do sistema local o mais próximo possível do horário da Internet. Ou, defina-a como a hora dos controladores de domínio na rede.

## <a name="next-steps"></a>Próximas etapas

[Problemas comuns e resoluções com perfis de email](../configuration/troubleshoot-email-profiles-in-microsoft-intune.md)

Obtenha [ajuda do suporte da Microsoft](../fundamentals/get-support.md) ou use os [fóruns da comunidade](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
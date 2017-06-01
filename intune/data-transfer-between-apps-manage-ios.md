---
title: "Gerenciar a transferência de dados entre aplicativos iOS | Visualização do Intune Azure"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: use este tópico para entender como você pode usar o recurso Open in do iOS e as políticas de gerenciamento de aplicativo móvel para gerenciar transferências de dados entre aplicativos."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 44747236ba1bda84ccb01f613e1702c536720a2c
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Como gerenciar a transferência de dados entre aplicativos iOS
## <a name="manage-ios-apps"></a>Gerenciar aplicativos iOS
Proteger os dados da sua empresa inclui garantir que as transferências de arquivos sejam restritas a aplicativos gerenciados por você.  Você pode gerenciar aplicativos iOS das seguintes maneiras:

-   Evite a perda de dados da empresa configurando uma política de proteção de aplicativo, que chamaremos de aplicativos **gerenciados por política** aplicativos. Consulte [todos os aplicativos orientados pelo Intune que você pode gerenciar com a política de proteção de aplicativo](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Você também pode implantar e gerenciar aplicativos pelo **canal MDM**.  Isso requer que os dispositivos sejam registrados na solução MDM. Eles podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.

O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**. As restrições de Abrir em gerenciamento são definidas nas definições de configuração e implantadas usando o software de MDM.  Quando o usuário instala o aplicativo implantado, são aplicadas restrições definidas por você.
##  <a name="using-app-protection-with-ios-apps"></a>Usando a proteção do aplicativo com aplicativos iOS
Políticas de proteção de aplicativo podem ser usadas com o recurso iOS **Abrir no gerenciamento** para proteger os dados da empresa das seguintes maneiras:

-   **Dispositivos de propriedade do funcionário não gerenciados por nenhuma solução de MDM:** você pode definir as configurações de política de proteção de aplicativo para **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. O usuário final não poderá abrir o arquivo protegido em um aplicativo que não for gerenciado por políticas.

-   **Dispositivos gerenciados pelo Intune:** para dispositivos registrados no Intune, transferência de dados entre aplicativos com as políticas de proteção de aplicativo e outros aplicativos do iOS gerenciado implantados por meio do Intune é permitida automaticamente. Para permitir a transferência de dados entre aplicativos com as políticas de proteção de aplicativo, habilite a configuração **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**. Você pode usar o recurso **Aberto em gerenciamento** para controlar a transferência de dados entre aplicativos que são implantados pelo Intune.   

-   **Dispositivos gerenciados por uma solução MDM de terceiro:** você pode restringir a transferência de dados somente para aplicativos gerenciados usando o recurso **Aberto em gerenciamento** do iOS.
Para verificar se os aplicativos implantados usando a solução de MDM de terceiros também estão associados às políticas de proteção de aplicativo configuradas no Intune, você deverá definir a configuração de UPN do usuário conforme descrito no passo a passo [Definir configuração de UPN do usuário](#configure-user-upn-setting-for-third-party-emm).  Quando os aplicativos são implantados com a configuração de UPN do usuário, as políticas de proteção de aplicativo serão aplicadas ao aplicativo quando o usuário final entrar usando sua conta corporativa.

> [!IMPORTANT]
> A configuração de UPN do usuário só será necessária para aplicativos implantados para dispositivos gerenciados por um MDM de terceiro.  Para dispositivos gerenciados pelo Intune, essa configuração não é necessária.


## <a name="configure-user-upn-setting-for-third-party-emm"></a>Definir configuração de UPN do usuário para EMM de terceiros
Essa configuração de UPN do usuário é **necessária** para dispositivos gerenciados por uma solução EMM de terceiros. O procedimento descrito abaixo é um fluxo geral de como definir a configuração de UPN e a experiência resultante do usuário final:


1.  No [portal do Azure](https://portal.azure.com), [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) para iOS. Defina as configurações da política conforme os requisitos da sua empresa e selecione os aplicativos de iOS que devem ter essa política.

2.  Implante os aplicativos e o perfil de email que você deseja gerenciar **por meio da solução MDM de terceiros** usando as etapas gerais abaixo. Essa experiência também é abordada no Exemplo 1.

  1.  Implante o aplicativo com as seguintes configurações do aplicativo:

      **key** = IntuneMAMUPN,  **value** = <username@company.com>

      Exemplo: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Implante Abrir na política de gerenciamento usando o provedor de MDM de terceiros para dispositivos registrados.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>Exemplo 1: experiência de Admin no console do MDM de terceiros

1. Vá para o console de administração do seu provedor MDM de terceiros. Vá para a seção do console em que você implanta as definições de configuração de aplicativo para dispositivos iOS registrados.

2. Na seção Configuração do Aplicativo, insira a seguinte configuração:

  **key** = IntuneMAMUPN,  **value** = <username@company.com>

  A sintaxe exata do par chave/valor pode diferir com base no provedor de MDM de terceiros. A tabela a seguir mostra exemplos de provedores de MDM de terceiros e os valores exatos que você deve digitar para o par chave/valor.

|Provedor de MDM de terceiros| Chave de Configuração | Tipo de valor | Valor da Configuração|
| ------- | ---- | ---- | ---- |
|VMware AirWatch| IntuneMAMUPN | Cadeia de caracteres | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | Cadeia de caracteres | ${userUPN} **ou** ${userEmailAddress} |


### <a name="example-2-end-user-experience"></a>Exemplo 2: experiência do usuário final

1.  O usuário final instala um aplicativo Microsoft Word no dispositivo.

2.  O usuário final inicia o aplicativo de email nativo gerenciado para acessar seus emails.

3.  O usuário final tenta abrir o documento do email nativo no Microsoft Word.

4.  Quando o aplicativo Word é iniciado, o usuário final é solicitado a fazer logon usando sua conta de trabalho.  Essa conta de trabalho que o usuário final insere quando solicitado deve corresponder à conta especificada nas definições de configuração de aplicativo para o aplicativo Microsoft Word.

    > [!NOTE]
    > O usuário final pode adicionar outras contas pessoais ao Word para fazer seu trabalho pessoal e não ser afetado pelas políticas de proteção de aplicativo ao usar o aplicativo do Word em um contexto pessoal.

5.  Quando o logon for bem-sucedido, as configurações da política de proteção de aplicativo são aplicadas ao aplicativo Word.

6.  A transferência de dados é bem-sucedida e o documento é marcado como identidade corporativa no aplicativo. Além disso, os dados são tratados em um contexto de trabalho e as configurações da política são aplicadas de acordo.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Validar configuração de UPN do usuário para EMM de terceiros

Depois de definir a configuração de UPN do usuário, você deve validar a capacidade do aplicativo iOS para receber e atender à política de proteção de aplicativo do Intune.

Por exemplo, a configuração de política **Exigir PIN do aplicativo** é fácil de testar visualmente em um dispositivo. Se a configuração de política estiver definida como **Sim**, o usuário final receberá um prompt para definir ou inserir um PIN durante a tentativa de acessar dados da empresa.

Primeiro, [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) no aplicativo iOS. Consulte [Validar as políticas de proteção do aplicativo](app-protection-policies-validate.md) para obter mais informações sobre como testar a política de proteção de aplicativo.


### <a name="see-also"></a>Consulte também
[O que é a política de proteção de aplicativo do Intune](app-protection-policy.md)

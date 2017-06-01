---
title: "Resolver conflitos de política de GPO e do Intune | Microsoft Docs"
description: "Saiba como resolver conflitos entre a Política de Grupo e as políticas de configuração do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 250ddb35aa33523141ae0f5af19b48b75ce0bef0
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="resolve-group-policy-objects-gpo-and-microsoft-intune-policy-conflicts"></a>Resolver conflitos de política do Microsoft Intune e GPO (Objetos de Política de Grupo)
O Intune usa políticas que ajudam a gerenciar as configurações em computadores Windows. Por exemplo, é possível usar uma política para controlar as configurações do Firewall do Windows nos computadores. Várias configurações do Intune são semelhantes às configurações que podem ser feitas com a Política de Grupo do Windows. No entanto, é possível que, às vezes, os dois métodos entrem em conflito.

Quando ocorrem conflitos, a Política de Grupo no nível de domínio tem precedência sobre a política do Intune, a menos que o computador não possa entrar no domínio. Nesse caso, a política do Intune é aplicada ao computador cliente.

## <a name="what-to-do-if-you-are-using-group-policy"></a>O que fazer se você estiver usando a política de grupo
Garanta que as políticas aplicadas não estão sendo gerenciadas pela Política de Grupo. Para ajudar a evitar conflitos, é possível usar um ou mais dos seguintes métodos:

-   Mova seus computadores para uma OU (unidade organizacional) do Active Directory que não tenha configurações de Política de Grupo aplicadas antes de instalar o cliente do Intune. Você também pode bloquear a herança da Política de Grupo nas OUs que contenham computadores inscritos no Intune, aos quais você não deseja aplicar as configurações de Política de Grupo.

-   Use um filtro do grupo de segurança para restringir somente GPOs para computadores não gerenciados pelo Intune.

-   Desabilite ou remova os Objetos da Política de Grupo que entram em conflito com as políticas do Intune.

Para obter mais informações sobre o Active Directory e a Política de Grupo do Windows, consulte a documentação do Windows Server.

## <a name="how-to-filter-existing-gpos-to-avoid-conflicts-with-intune-policy"></a>Como filtrar os GPOs (Objetos da Política de Grupo) existentes para evitar conflitos com a política do Intune
Se você identificou GPOs com configurações que entram em conflito com as políticas do Intune, é possível usar os filtros de grupo de segurança para restringir os GPOs apenas aos computadores não gerenciados pelo Intune.

<!--- ### Use WMI filters
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all PCs in the enterprise before you enroll any PCs in the Intune service.

#### To apply WMI filters to a GPO

1.  Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to PCs that you want to enroll in the Intune service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client PCs in the Intune service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3.  Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to PCs that are managed by using Intune or to PCs that are not managed by using Intune.

    -   For GPOs that apply to PCs that are not managed by using Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   For GPOs that apply to PCs that are managed by Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    -   For GPOs that should apply only to PCs that you want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=1**.

    -   For GPOs that should apply only to PCs that you do not want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883). --->


Você pode aplicar GPOs apenas aos grupos de segurança especificados na área **Filtragem de Segurança** do console do Gerenciamento de Política de Grupo de um GPO selecionado. Por padrão, os GPOs aplicam-se a *Usuários Autenticados*.

-   No snap-in **Usuários e Computadores do Active Directory**, crie um novo grupo de segurança que contém computadores e contas de usuário que você não deseja que o Intune gerencie. Por exemplo, você pode nomear o grupo *Não pertence ao Microsoft Intune*.

-   No console de Gerenciamento de Política de Grupo, na guia **Delegação** do GPO selecionado, clique com o botão direito do mouse no novo grupo de segurança para delegar as permissões **Leitura** e **Aplicar Política de Grupo** a usuários e computadores no grupo de segurança. (As permissões para**Aplicar Política de Grupo** estão disponíveis na caixa de diálogo **Avançado** .)

-   Em seguida, aplique o novo filtro de grupo de segurança a um GPO selecionado e remova o filtro padrão **Usuários Autenticados**.

O novo grupo de segurança deve ser mantido como registro nas alterações de serviço do Intune.

### <a name="see-also"></a>Consulte também
[Gerenciar computadores Windows com o Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)

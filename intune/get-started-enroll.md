---
title: "Introdução ao registro de dispositivos"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36e658cebdfd23547e3c376124289046f81acc1f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Introdução ao registro de dispositivos
<a id="getting-started-enrolling-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Dispositivo iOS mostrando o aplicativo de portal da empresa. a primeira tela apresentada ao usuário para o processo de registro é mostrada.](/intune-user-help/media/ios-enroll-1a-comp-access-setup.png)

O Microsoft Intune ajuda você a capacitar sua força de trabalho com dispositivos móveis, ao mesmo tempo que mantém seus dados corporativos protegidos. Como os usuários finais interagem com o Intune em seus dispositivos, em vez de no console do administrador, você deve estar familiarizado com a experiência de registro. Dessa forma, você pode combinar as políticas de conformidade bem elaboradas com sua experiência para demonstrar empatia pelos usuários. Isso é especialmente importante porque os usuários saberão exatamente quais informações que você pode ver como um administrador:

## O que a equipe de TI não pode ver
<a id="what-it-cannot-see" class="xliff"></a>
* Histórico de chamadas e de navegação na Web
* Local
* Email pessoal
* Mensagens de texto
* Contatos
* Senhas de suas contas pessoais
* Eventos do calendário
* Imagens, incluindo o conteúdo do aplicativo de fotos ou as imagens da câmera

## O que a equipe de TI pode ver
<a id="what-it-can-see" class="xliff"></a>
* Modelo
* Número de série
* Versão do sistema operacional
* Nomes de aplicativo
* Proprietário
* Nome do dispositivo
* Fabricante (para dispositivos não fabricados pela Apple)
* Número de telefone (para dispositivos corporativos, o número completo. Para dispositivos pessoais, apenas os últimos quatro dígitos.)

## Como registro um dispositivo?
<a id="how-do-i-enroll-a-device" class="xliff"></a>

Registrar um dispositivo é a primeira experiência que muitos usuários finais terão ao acessar recursos corporativos. [Entender essa experiência](end-user-educate.md) pode ajudar a tornar uma experiência possivelmente desagradável em uma melhor.

1. Abra a **Loja de Aplicativos** e pesquise por **Portal da Empresa do Intune**.
2. Baixe o aplicativo **Portal da Empresa do Microsoft Intune**.
3. Abra o aplicativo **Portal da Empresa**, digite seu endereço de email e a senha do usuário de teste e toque em **Entrar**.
4. Atualize a senha temporária para uma nova.
5. Na página **Configuração de Acesso da Empresa**, toque em **Registro de Dispositivo**.
6. Na página **Por que registrar seu dispositivo?** leia sobre o que um usuário pode fazer ao registrar o dispositivo e, em seguida, toque em **Continuar**.
7. Examine uma lista de qual acesso um usuário recebe ao registrar-se e toque em **Continuar**.
8. Examine o que os administradores de TI podem ou não podem ver em um dispositivo e toque em **Continuar**.
9. Na página **O que vem em seguida**, leia sobre o que acontece durante o registro e, em seguida, toque em **Registrar**.
10. Na página **Instalar Perfil**, toque em **Instalar** e insira a senha do dispositivo se solicitado.
11. Toque em **Instalar**.
12. Toque em **Instalar** novamente para indicar que você leu o aviso.
13. No pop-up **Aviso**, toque em **Confiar**.
14. Quando a tela for alterada para mostrar que o perfil terminou de instalar, toque em **Concluído**.
15. Uma mensagem de “Registrando dispositivo” é mostrada na tela e, em seguida, mostra que o dispositivo foi registrado com êxito. Um pop-up será exibido perguntando se a página deve ser aberta no Portal da Empresa. Toque em **Abrir**.
16. Você voltará para a tela **Configuração de Acesso da Empresa**. Se você não tiver nenhuma política de teste configurada, então o dispositivo deverá aparecer em conformidade. Se você tiver alguma política de teste, tocar em **Conformidade do Dispositivo** mostrará que há coisas que precisam ser feitas para proteger o dispositivo.
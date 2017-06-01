---
title: Solucionar problemas de acesso a recursos da empresa | Microsoft Docs
description: "Códigos de erro e de status neste tópico para ajudá-lo a solucionar problemas de acesso do recurso."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40622ced-6029-4abf-873e-b51d2b51934c
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 9956d92c5d1b294c4ccf04ebecd15cdb59794c90
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="troubleshoot-company-resource-access-problems-with-microsoft-intune"></a>Solucionar problemas de acesso ao recurso da empresa com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use os códigos de erro e de status neste tópico para ajudá-lo a solucionar problemas quando uma ação do Microsoft Intune retornar um código de erro.

Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](../troubleshoot/how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.

## <a name="status-codes-for-mdm-managed-windows-devices"></a>Códigos de status de dispositivos Windows gerenciados pelo MDM

|Código de status|Mensagem de erro|O que fazer|
|---------------|-----------------|--------------|
|10 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Instalação em andamento||
|20 (APP_CI_ENFORCEMENT_IN_PROGRESS_WAITING_CONTENT)|Aguardando conteúdo||
|30 (APP_CI_ENFORCEMENT_ERROR_RETRIEVING_CONTENT)|Recuperando conteúdo|Causa provável: o status de trabalho 30 indica que o download de um aplicativo por um usuário falhou.<br /><br />As causas prováveis disso podem ser:<br /><br />O dispositivo perdeu a conectividade com a Internet enquanto o download estava em andamento.<br /><br />O certificado emitido para o dispositivo no momento do registro pode ter expirado.<br /><br />Mitigação:<br /><br />Inicie o aplicativo Company Apps no Painel de Controle do dispositivo para verificar se o certificado do dispositivo não expirou. Em caso afirmativo, você precisará registrar o dispositivo novamente.<br /><br />Confirme se o dispositivo está conectado à Internet e tente solicitar o aplicativo novamente.|
|40 (APP_CI_ENFORCEMENT_IN_PROGRESS_CONTENT_DOWNLOADED)|Download do conteúdo concluído||
|50 (APP_CI_ENFORCEMENT_IN_PROGRESS_INSTALLING)|Instalação em andamento||
|60 (APP_CI_ENFORCEMENT_ERROR_INSTALLING)|Ocorreu um erro de instalação|A instalação do aplicativo falhou após o download.<br /><br />O certificado de assinatura de código com o qual o aplicativo foi assinado não está presente no dispositivo.<br /><br />Uma dependência de estrutura da qual o aplicativo depende não está instalada no dispositivo.<br /><br /><br />Caso a falha de instalação se deva à ausência de uma dependência de estrutura, o administrador precisará publicar novamente o aplicativo, empacotando a estrutura no pacote de aplicativos.<br /><br />O pacote de aplicativos baixado não é um pacote válido, pode ter sido corrompido ou pode não ser compatível com a versão do sistema operacional no dispositivo.|
|70 (APP_CI_ENFORCEMENT_SUCCEEDED)|Instalação bem-sucedida||
|80 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Desinstalação em andamento||
|90 (APP_CI_ENFORCEMENT_ERROR)|Ocorreu um erro de desinstalação||
|100 (APP_CI_ENFORCEMENT_SUCCEEDED)|Desinstalação bem-sucedida||
|110 (APP_CI_ENFORCEMENT_ERROR)|Incompatibilidade de hash de conteúdo||
|120 (APP_CI_ENFORCEMENT_ERROR)|SLK / sideload não habilitado||
|130 (APP_CI_ENFORCEMENT_ERROR)|Falha na instalação da licença MSADP||
|Nenhum status (APP_CI_ENFORCEMENT_UNKNOWN)|N/D|O status é desconhecido no momento.|

## <a name="company-resource-access-common-errors"></a>Acesso aos recursos da empresa (erros comuns)

|Código de status|Código de erro hexadecimal|Mensagem de erro|
|---------------|--------------------------|-----------------|
|-2016281101|0x87D1FDF3|Solicitação de CRP do MDM não encontrada|
|-2016281102|0x87D1FDF2|URL de NDES não encontrada|
|-2016281103|0x87D1FDF1|Informações do certificado CRP do MDM não encontradas|
|-2016281104|0x87D1FDF0|Informações do certificado CI do MDM não encontradas|
|-2016281105|0x87D1FDEF|Falha ao avaliar a regra|
|-2016281106|0x87D1FDEE|Não aplicável porque se perdeu na resolução de conflitos|
|-2016281107|0x87D1FDED|Fonte de descoberta de configuração sem suporte|
|-2016281108|0x87D1FDEC|Configuração de referência não encontrada no CI|
|-2016281109|0x87D1FDEB|Falha na conversão do tipo de dados|
|-2016281110|0x87D1FDEA|Parâmetro inválido para configuração de CIM|
|-2016281111|0x87D1FDE9|Não aplicável para este dispositivo|
|-2016281112|0x87D1FDE8|Falha na ação de correção|
|-2016330905|0x87D13B67|O estado do aplicativo é desconhecido|
|-2016330906|0x87D13B66|O aplicativo é gerenciado, mas foi removido pelo usuário|
|-2016330907|0x87D13B65|O dispositivo está resgatando o código de resgate|
|-2016330908|0x87D13B64|Falha na instalação do aplicativo|
|-2016330909|0x87D13B63|O usuário rejeitou a oferta para atualizar o aplicativo|
|-2016330910|0x87D13B62|O usuário rejeitou a oferta para instalar o aplicativo|
|-2016330911|0x87D13B61|O usuário instalou o aplicativo antes que a instalação do aplicativo gerenciado pudesse ocorrer|
|-2016330912|0x87D13B60|O aplicativo está programado para instalação, mas precisa de um código de resgate para concluir a transação|
|-2016341109|0x87D1138B|O dispositivo iOS retornou um erro|
|-2016341110|0x87D1138A|O dispositivo iOS rejeitou o comando devido ao formato incorreto|
|-2016341111|0x87D11389|O dispositivo iOS retornou um status ocioso inesperado|
|-2016341112|0x87D11388|O dispositivo iOS está ocupado no momento|

## <a name="errors-returned-by-ios-devices"></a>Erros retornados por dispositivos iOS

|Código de status|Código de erro hexadecimal|Mensagem de erro|
|---------------|--------------------------|-----------------|
|-2016299111|0x87D1B799|Erro interno|
|-2016299112|0x87D1B798|Erro interno|
|-2016300111|0x87D1B3B1|36001: (erro interno)|
|-2016300112|0x87D1B3B0|36000: celular já configurado|
|-2016301110|0x87D1AFCA|35002: diversas fontes em um único conteúdo|
|-2016301111|0x87D1AFC9|35001: falha na instalação da fonte|
|-2016301112|0x87D1AFC8|35000: dados de fonte inválida|
|-2016302109|0x87D1ABE3|34003: nome da entidade Kerberos inválido|
|-2016302110|0x87D1ABE2|34002: nome da entidade Kerberos ausente|
|-2016302111|0x87D1ABE1|34001: padrão de correspondência de URL inválido|
|-2016302112|0x87D1ABE0|34000: padrão de correspondência de identificador de aplicativo inválido|
|-2016304112|0x87D1A410|32000: aplicativos em excesso|
|-2016305111|0x87D1A029|31001: não é possível aplicar as configurações|
|-2016305112|0x87D1A028|31000: não é possível aplicar a credencial|
|-2016306111|0x87D19C41|30001: tempo limite atingido|
|-2016306112|0x87D19C40|30000: falha na autenticação|
|-2016307109|0x87D1985B|29003: dados de certificado incorretos|
|-2016307110|0x87D1985A|29002:|
|-2016307111|0x87D19859|29001:|
|-2016307112|0x87D19858|29000: dispositivo não supervisionado|
|-2016308110|0x87D19472|28002: não é possível definir o papel de parede|
|-2016308111|0x87D19471|28001: imagem de papel de parece incorreta|
|-2016308112|0x87D19470|28000: item desconhecido|
|-2016310111|0x87D18CA1|26001: criptografia no nível do arquivo sem suporte|
|-2016310112|0x87D18CA0|26000: criptografia no nível do bloco sem suporte|
|-2016311110|0x87D188BA|25002: não é possível remover|
|-2016311111|0x87D188B9|25001: não é possível instalar|
|-2016311112|0x87D188B8|25000: perfil incorreto|
|-2016312109|0x87D184D3|24003: perfil final incorreto|
|-2016312110|0x87D184D2|24002: carga de identidade incorreta|
|-2016312111|0x87D184D1|24001: não é possível assinar o dicionário de atributos|
|-2016312112|0x87D184D0|24000: não é possível criar o dicionário de atributos|
|-2016313110|0x87D180EA|23002: certificado do servidor inválido|
|-2016313111|0x87D180E9|23001: resposta do servidor incorreta|
|-2016313112|0x87D180E8|23000: identidade incorreta|
|-2016314099|0x87D17D0D|22013: resposta de PKIOperation inválida|
|-2016314100|0x87D17D0C|22012: não é possível armazenar CACertificate|
|-2016314101|0x87D17D0B|22011: não é possível gerar o CSR|
|-2016314102|0x87D17D0A|22010: não é possível armazenar a identidade temporária|
|-2016314103|0x87D17D09|22009: não é possível criar a identidade temporária|
|-2016314104|0x87D17D08|22008: não é possível criar a identidade|
|-2016314105|0x87D17D07|22007: certificado assinado inválido|
|-2016314106|0x87D17D06|22006: CACaps insuficiente|
|-2016314107|0x87D17D05|22005: erro de rede|
|-2016314108|0x87D17D04|22004: configuração de certificado sem suporte|
|-2016314109|0x87D17D03|22003: RAResponse inválida|
|-2016314110|0x87D17D02|22002: CAResponse inválida|
|-2016314111|0x87D17D01|22001: não é possível gerar o par de chaves|
|-2016314112|0x87D17D00|22000: uso de chave inválido|
|-2016315105|0x87D1791F|21007: não é possível verificar a conta|
|-2016315106|0x87D1791E|21006: não é possível descriptografar o certificado|
|-2016315107|0x87D1791D|21005: Conta não exclusiva (o Perfil de Email já existe no dispositivo)|
|-2016315108|0x87D1791C|21004: não é possível criar a conta|
|-2016315109|0x87D1791B|21003: nenhum nome de host|
|-2016315110|0x87D1791A|21002: não é possível manter a conformidade com a política de criptografia do servidor|
|-2016315111|0x87D17919|21001: não é possível manter a conformidade com a política do servidor|
|-2016315112|0x87D17918|21000: não é possível obter a política do servidor|
|-2016316110|0x87D17532|20002: conta não exclusiva|
|-2016316111|0x87D17531|20001: nenhum nome de host|
|-2016316112|0x87D17530|20000: não é possível criar a conta|
|-2016317110|0x87D1714A|19002: conta não exclusiva|
|-2016317111|0x87D17149|19001: nenhum nome de host|
|-2016317112|0x87D17148|19000: não é possível criar a conta|
|-2016318110|0x87D16D62|18002: credenciais inválidas|
|-2016318111|0x87D16D61|18001: host inacessível|
|-2016318112|0x87D16D60|18000: erro desconhecido|
|-2016319110|0x87D1697A|17002: conta não exclusiva|
|-2016319111|0x87D16979|17001: nenhum nome de host|
|-2016319112|0x87D16978|17000: não é possível criar a conta|
|-2016320110|0x87D16592|16002: conta não exclusiva|
|-2016320111|0x87D16591|16001: nenhum nome de host|
|-2016320112|0x87D16590|16000: não é possível criar a assinatura|
|-2016321109|0x87D161AB|15003: certificado inválido|
|-2016321110|0x87D161AA|15002: não é possível bloquear a configuração de rede|
|-2016321111|0x87D161A9|15001: não é possível remover o VPN|
|-2016321112|0x87D161A8|15000: não é possível instalar o VPN|
|-2016322110|0x87D15DC2|14002: a configuração de nuvem já existe|
|-2016322111|0x87D15DC1|14001: dispositivo bloqueado|
|-2016322112|0x87D15DC0|14000: campo inválido|
|-2016323107|0x87D159DD|13005: não é possível configurar o proxy|
|-2016323108|0x87D159DC|13004: não é possível configurar o EAP|
|-2016323109|0x87D159DB|13003: não é possível criar a configuração de WiFi|
|-2016323110|0x87D159DA|13002: senha necessária|
|-2016323111|0x87D159D9|13001: nome de usuário necessário|
|-2016323112|0x87D159D8|13000: não é possível instalar|
|-2016324070|0x87D1561A|12042: código de localidade desconhecido|
|-2016324071|0x87D15619|12041: código de idioma desconhecido|
|-2016324072|0x87D15618|12040: logon da iTunes Store necessário|
|-2016324073|0x87D15617|12039: (não utilizado)|
|-2016324074|0x87D15616|12038: aplicativo não gerenciado|
|-2016324075|0x87D15615|12037: código de resgate inválido|
|-2016324076|0x87D15614|12036: não é possível remover o aplicativo no estado atual|
|-2016324077|0x87D15613|12035: o aplicativo não pode ser comprado|
|-2016324078|0x87D15612|12034: a URL não é HTTPS|
|-2016324079|0x87D15611|12033: manifesto inválido|
|-2016324080|0x87D15610|12032: aplicativos em excesso no manifesto|
|-2016324081|0x87D1560F|12031: instalação do aplicativo desabilitada|
|-2016324082|0x87D1560E|12030: URL inválida|
|-2016324083|0x87D1560D|12029: aplicativo não gerenciado|
|-2016324084|0x87D1560C|12028: não aguardando resgate|
|-2016324085|0x87D1560B|12027: não é um aplicativo|
|-2016324086|0x87D1560A|12026: o aplicativo já está na fila|
|-2016324087|0x87D15609|12025: o aplicativo já está instalado|
|-2016324088|0x87D15608|12024: não foi possível validar o manifesto do aplicativo|
|-2016324089|0x87D15607|12023: não foi possível validar a ID do aplicativo|
|-2016324090|0x87D15606|12022: tópico inválido|
|-2016324091|0x87D15605|12021: tipo de solicitação inválida|
|-2016324092|0x87D15604|12020: não autorizado pelo servidor|
|-2016324093|0x87D15603|12019: não é possível copiar o segredo de caução|
|-2016324094|0x87D15602|12018: não é possível copiar os dados do pacote de chaves de caução|
|-2016324095|0x87D15601|12017: não é possível criar o pacote de chaves de caução|
|-2016324096|0x87D15600|12016: identidade ausente|
|-2016324097|0x87D155FF|12015: não é possível obter o token de push|
|-2016324098|0x87D155FE|12014: perfil de provisionamento não gerenciado|
|-2016324099|0x87D155FD|12013: perfil não gerenciado|
|-2016324100|0x87D155FC|12012: incompatibilidade de substituição de MDM|
|-2016324101|0x87D155FB|12011: configuração de MDM inválida|
|-2016324102|0x87D155FA|12010: erro de inconsistência interna|
|-2016324103|0x87D155F9|12009: perfil de substituição inválido|
|-2016324104|0x87D155F8|12008: solicitação malformada|
|-2016324105|0x87D155F7|12007: não autorizado|
|-2016324106|0x87D155F6|12006: redirecionamento negado|
|-2016324107|0x87D155F5|12005: não é possível encontrar o certificado|
|-2016324108|0x87D155F4|12004: certificado de push inválido|
|-2016324109|0x87D155F3|12003: resposta de desafio inválida|
|-2016324110|0x87D155F2|12002: não é possível fazer check-in|
|-2016324111|0x87D155F1|12001: diversas instâncias de MDM|
|-2016324112|0x87D155F0|12000: direitos de acesso inválidos|
|-2016325111|0x87D15209|11001: APN personalizado já instalado|
|-2016325112|0x87D15208|11000: não é possível instalar o APN|
|-2016326111|0x87D14E21|10001: signatário inválido|
|-2016326112|0x87D14E20|10000: não é possível instalar os padrões|
|-2016327106|0x87D14A3E|9006: o certificado não é uma identidade|
|-2016327107|0x87D14A3D|9005: o certificado está incorreto|
|-2016327108|0x87D14A3C|9004: não é possível armazenar o certificado raiz|
|-2016327109|0x87D14A3B|9003: não é possível armazenar os dados de WAPI|
|-2016327110|0x87D14A3A|9002: não é possível armazenar o certificado|
|-2016327111|0x87D14A39|9001: certificados em excesso em um conteúdo|
|-2016327112|0x87D14A38|9000: senha inválida|
|-2016328112|0x87D14650|8000: não é possível instalar o clipe da Web|
|-2016329105|0x87D1426F|7007: a conta SMTP está configurada incorretamente|
|-2016329106|0x87D1426E|7006: a conta POP está configurada incorretamente|
|-2016329107|0x87D1426D|7005: a conta IMAP está configurada incorretamente|
|-2016329108|0x87D1426C|7004: certificado SMIME incorreto|
|-2016329109|0x87D1426B|7003: certificado SMIME não encontrado|
|-2016329110|0x87D1426A|7002: um erro desconhecido ocorreu durante a validação|
|-2016329111|0x87D14269|7001: credenciais inválidas|
|-2016329112|0x87D14268|7000: host inacessível|
|-2016330110|0x87D13E82|6002: não é possível criar a consulta|
|-2016330111|0x87D13E81|6001: cadeia de caracteres vazia|
|-2016330112|0x87D13E80|6000: erro no sistema de conjunto de chaves|
|-2016331097|0x87D13AA7|5015: não é possível definir o período de cortesia|
|-2016331098|0x87D13AA6|5014: não é possível definir a senha|
|-2016331099|0x87D13AA5|5013: não é possível limpar a senha|
|-2016331100|0x87D13AA4|5012:(não utilizado)|
|-2016331101||5011: senha incorreta|
|-2016331102||5010: dispositivo bloqueado|
|-2016331103|0x87D13AA4|5009:(não utilizado)|
|-2016331104|0x87D13AA0|5008: senha muito recente|
|-2016331105|0x87D13A9F|5007: senha expirada|
|-2016331106|0x87D13AA3|5006: a senha exige caracteres alfa|
|-2016331107|0x87D13A9D|5005: a senha exige um número|
|-2016331108|0x87D13A9C|5004: a senha tem caracteres ascendentes/descendentes|
|-2016331109|0x87D13A9B|5003: a senha tem caracteres repetidos|
|-2016331110|0x87D13A9A|5002: caracteres complexos insuficientes|
|-2016331111|0x87D13A99|5001: caracteres exclusivos insuficientes|
|-2016331112|0x87D13A98|5000: senha muito curta|
|-2016332093|0x87D136C3|4019: diversos conteúdos de Bloqueio de Aplicativo|
|-2016332094|0x87D136C2|4018: diversos conteúdos de APN ou celular|
|-2016332095|0x87D136C1|4017: diversos conteúdos HTTPProxy globais|
|-2016332096|0x87D136C0|4016:(erro interno)|
|-2016332097|0x87D136BF|4015: o perfil de substituição não tem um conteúdo de MDM|
|-2016332098|0x87D136BE|4014: nenhuma identidade de dispositivo disponível|
|-2016332099|0x87D136BD|4013: falha na atualização|
|-2016332100|0x87D136BC|4012: o perfil não é atualizável|
|-2016332101|0x87D136BB|4011: o perfil final não é um perfil de configuração|
|-2016332102|0x87D136BA|4010: o perfil atualizado não tem o mesmo identificador|
|-2016332103|0x87D136B9|4009: dispositivo bloqueado|
|-2016332104|0x87D136B8|4008: certificados não correspondentes|
|-2016332105|0x87D136B7|4007: formato de arquivo não reconhecido|
|-2016332106|0x87D136B6|4006: a data de remoção do perfil está no passado|
|-2016332107|0x87D136B5|4005: a senha não está em conformidade|
|-2016332108|0x87D136B4|4004: o usuário cancelou a instalação|
|-2016332109|0x87D136B3|4003: perfil não enfileirado para instalação|
|-2016332110|0x87D136B2|4002: UUID duplicado|
|-2016332111|0x87D136B1|4001: falha na instalação|
|-2016332112|0x87D136B0|4000: não é possível analisar o perfil|
|-2016333111|0x87D132C9|3001: sensor de comparação de valor inconsistente (erro interno)|
|-2016333112|0x87D132C8|3000: sensor de restrição inconsistente (erro interno)|
|-2016334108|0x87D12EE4|2004: valor de campo sem suporte|
|-2016334109|0x87D12EE3|2003: tipo de dados incorreto no campo|
|-2016334110|0x87D12EE2|2002: campo obrigatório ausente|
|-2016334111|0x87D12EE1|2001: versão de conteúdo sem suporte|
|-2016334112|0x87D12EE0|2000: conteúdo malformado|
|-2016335102|0x87D12B02|1010: valor de campo sem suporte|
|-2016335103|0x87D12B01|1009: falha na instalação do perfil|
|-2016335104|0x87D12B00|1008: identificadores de conteúdo não exclusivos|
|-2016335105|0x87D12AFF|1007: UUIDs não exclusivos|
|-2016335106|0x87D12AFE|1006: não é possível descriptografar|
|-2016335107|0x87D12AFD|1005: perfil vazio|
|-2016335108|0x87D12AFC|1004: assinatura incorreta|
|-2016335109|0x87D12AFB|1003: tipo de dados incorreto no campo|
|-2016335110|0x87D12AFA|1002: campo obrigatório ausente|
|-2016335111|0x87D12AF9|1001: versão de perfil sem suporte|
|-2016335112|0x87D12AF8|1000: perfil malformado|

## <a name="oma-response-codes"></a>Códigos de resposta do OMA

|Código de status|Código de erro hexadecimal|Mensagem de erro|
|---------------|--------------------------|-----------------|
|-2016344008|0x87D10838|(1404): acesso negado ao certificado|
|-2016344009|0x87D10837|(1403): certificado não encontrado|
|-2016344010|0x87D10836|DCMO(1402): falha na operação|
|-2016344011|0x87D10835|DCMO(1401): o usuário optou por não aceitar a operação quando solicitado|
|-2016344012|0x87D10834|DCMO(1400): erro do cliente|
|-2016344108|0x87D107D4|DCMO(1204): a Capacidade de Dispositivo está desabilitada e o Usuário está autorizado a reabilitá-la|
|-2016344109|0x87D107D3|DCMO(1203): a Capacidade de Dispositivo está desabilitada e o Usuário não está autorizado a reabilitá-la|
|-2016344110|0x87D107D2|DCMO(1202): a operação de habilitação é executada com êxito, mas a Capacidade de Dispositivo está atualmente desanexada|
|-2016344111|0xF3FB4D95|DCMO(1201): a operação de habilitação é executada com êxito e a Capacidade de Dispositivo está atualmente anexada|
|-2016344112|0x87D107D0|DCMO (1200): a operação é executada com sucesso|
|-2016345595|0x87D10205|Syncml(517): a resposta a um comando atômico era demasiado extensa para caber numa única mensagem.|
|-2016345596|0x87D10204|Syncml(516): o comando estava dentro de um elemento Atômico e o Atômico falhou. Este comando não foi revertido com êxito.|
|-2016345598|0x87D10202|Syncml(514): o comando SyncML não foi concluído com êxito porque a operação já tinha sido cancelada antes do processamento do comando.|
|-2016345599|0x87D10201|Syncml(513): o destinatário não dá suporte ou recusa-se a dar suporte à versão especificada do Protocolo de Sincronização de SyncML utilizado na Mensagem de SyncML de solicitação.|
|-2016345600|0x87D10200|Syncml(512): ocorreu um erro no aplicativo durante a sessão de sincronização.|
|-2016345601|0x87D101FF|Syncml(511): ocorreu um erro grave no servidor durante o processamento do pedido.|
|-2016345602|0x87D101FE|Syncml(510): ocorreu um erro ao processar a solicitação. O erro está relacionado a uma falha no armazenamento de dados do destinatário.|
|-2016345603|0x87D101FD|Syncml(509): reservado para utilização futura.|
|-2016345604|0x87D101FC|Syncml(508): ocorreu um erro que exige uma atualização do estado de sincronização atual do cliente com o servidor.|
|-2016345605|0x87D101FB|Syncml(507): o erro causou a falha de todos os comandos SyncML num tipo de elemento Atômico.|
|-2016345606|0x87D101FA|Syncml(506): ocorreu um erro no aplicativo durante o processamento do pedido.|
|-2016345607|0x87D101F9|Syncml(505): o destinatário não dá suporte ou recusa-se a dar suporte à versão especificada do DTD de SyncML utilizada na Mensagem de SyncML de solicitação.|
|-2016345608|=0x87D101F8|Syncml(504): o destinatário, ao atuar como gateway ou proxy, não recebeu uma resposta em tempo hábil do destinatário a montante especificado pelo URI (por exemplo, HTTP, FTP, LDAP) ou de qualquer outro destinatário auxiliar (por exemplo, DNS) ao qual necessitava acessar para tentar concluir o pedido.|
|-2016345609|0x87D101F7|Syncml(503): o destinatário não consegue processar a solicitação neste momento devido a uma sobrecarga temporária ou a manutenção do destinatário.|
|-2016345610|0x87D101F6|Syncml(502): o destinatário, ao atuar como gateway ou proxy, recebeu uma resposta inválida do destinatário a montante ao qual acessou uma tentativa de satisfazer a solicitação.|
|-2016345611|0x87D101F5|Syncml(501): o destinatário não dá suporte ao comando necessário para satisfazer o pedido.|
|-2016345612|0x87D101F4|Syncml(500): o destinatário encontrou uma condição inesperada que o impediu de satisfazer a solicitação|
|-2016345684|0x87D101AC|Syncml(428): falha ao mover|
|-2016345685|0x87D101AB|Syncml(427): não é possível excluir o elemento pai porque contém elementos filhos.|
|-2016345686|0x87D101AA|Syncml(426): item parcial não aceito.|
|-2016345687|0x87D101A9|Syncml(425): falha ao executar o comando solicitado porque o remetente não tem ACL (permissões de controle de acesso) adequadas em relação ao destinatário.|
|-2016345688|0x87D101A8|Syncml(424): o objeto em segmentos foi recebido, mas o tamanho do objeto recebido não correspondeu ao tamanho declarado no primeiro segmento.|
|-2016345689|0x87D101A7|Syncml(423): falha ao executar o comando solicitado porque o item "Eliminado de Forma Recuperável" foi "Eliminado de Forma Definitiva" no servidor anteriormente.|
|-2016345690|0x87D101A6|Syncml(422): falha ao executar o comando solicitado no servidor porque o script CGI no LocURI estava formado incorretamente.|
|-2016345691|0x87D101A5|Syncml(421): falha ao executar o comando solicitado no servidor porque a gramática de pesquisa especificada era desconhecida.|
|-2016345692|0x87D101A4|Syncml(420): o destinatário não dispõe de mais espaço de armazenamento para os dados de sincronização restantes.|
|-2016345693|0x87D101A3|Syncml(419): a solicitação do cliente criou um conflito que foi resolvido pelo comando prevalecente do servidor.|
|-2016345694|0x87D101A2|Syncml(418): falha ao executar o comando Put ou Add solicitado porque o destino já existe.|
|-2016345695|0x87D101A1|Syncml(417): falha momentânea ao executar a solicitação. O originador deverá repetir a solicitação mais tarde.|
|-2016345696|0x87D101A0|Syncml(416): falha ao executar a solicitação porque o tamanho especificado em bytes era demasiado grande.|
|-2016345697|0x87D1019F|Syncml(415): tipo de suporte de mídia ou formato sem suporte.|
|-2016345698|0x87D1019E|Syncml(414): falha ao executar o comando solicitado porque o URI de destino é demasiado extenso para a capacidade ou disponibilidade de processamento do destinatário.|
|-2016345699|0x87D1019D|Syncml(413): o destinatário está se recusando a executar o comando solicitado porque o item solicitado é maior do que o destinatário é capaz ou está disposto a processar.|
|-2016345700|0x87D1019C|Syncml(412): falha ao executar o comando solicitado no destinatário porque estava incompleto ou formado incorretamente.|
|-2016345701|0x87D1019B|Syncml(411): o comando solicitado deve estar acompanhado do tamanho em bytes ou da informação de comprimento no tipo de elemento Meta.|
|-2016345702|0x87D1019A|Syncml(410): o destino solicitado já não se encontra no destinatário e nenhum URI de reencaminhamento é conhecido.|
|-2016345703|0x87D10199|Syncml(409): falha ao executar o pedido devido a um conflito de atualização entre as versões dos dados no cliente e no servidor.|
|-2016345704|0x87D10198|Syncml(408): não foi recebida uma mensagem esperada dentro do prazo atribuído.|
|-2016345705|0x87D10197|Syncml(407): falha ao executar o comando solicitado porque o originador deve disponibilizar a autenticação correta.|
|-2016345706|0x87D10196|Syncml(406): falha ao executar o comando solicitado porque não tinha suporte um recurso opcional na solicitação.|
|-2016345707|0x87D10195|Syncml(405): o comando solicitado não é permitido no destino.|
|-2016345708|0x87D10194|Syncml(404): o destino solicitado não foi localizado.|
|-2016345709|0x87D10193|Syncml(403): falha ao executar o comando solicitado, mas o destinatário compreendeu o comando pretendido.|
|-2016345710|0x87D10192|Syncml(402): falha ao executar o comando solicitado porque é necessário o pagamento adequado.|
|-2016345711|0x87D10191|Syncml(401): falha ao executar o comando solicitado porque o solicitante deve disponibilizar a autenticação adequada.|
|-2016345712|0x87D10190|Syncml(400): não foi possível executar o comando solicitado devido à sintaxe formada incorretamente no comando.|
|-2016345807|0x87D10131|Syncml(305): o destino solicitado deve ser acessado pelo URI de proxy especificado.|
|-2016345808|0x87D10130|Syncml (304): O comando de SyncML solicitado não foi executado no destino.|
|-2016345809|0x87D1012F|Syncml(303): é possível localizar o destino solicitado em outro URI.|
|-2016345810|0x87D1012E|Syncml(302): o destino solicitado foi movido temporariamente para outro URI.|
|-2016345811|0x87D1012D|Syncml(301): o destino solicitado tem um novo URI.|
|-2016345812|0x87D1012C|Syncml(300): o destino solicitado é uma das várias alternativas de destino solicitadas.|
|-2016345896|0x87D100D8|Syncml(216): um comando estava dentro de um elemento do Atômico e o Atômico falhou. Este comando foi revertido com êxito.|
|-2016345897|0x87D100D7|Syncml(215): não foi executado um comando, como resultado da interação do usuário, o qual optou por não aceitar a escolha.|
|-2016345898|0x87D100D6|Syncml(214): operação cancelada. O comando SyncML foi concluído com êxito, mas não serão processados mais comandos na sessão.|
|-2016345899|0x87D100D5|Syncml(213): o item em segmento foi aceito e colocado em buffer|
|-2016345900|0x87D100D4|Syncml(212): autenticação aceita. Nenhuma autenticação adicional é necessária para o restante da sessão de sincronização. Este código de resposta pode ser usado apenas em resposta a uma solicitação em que credenciais foram fornecidas.|
|-2016345901|0x87D100D3|Syncml(211): item não excluído. O item solicitado não foi encontrado. Ele pode ter sido excluído previamente.|
|-2016345902|0x87D100D2|Syncml(210): excluir sem arquivamento. A resposta indica que os dados solicitados foram excluídos com êxito, mas não foram arquivados antes da exclusão porque esse recurso OPCIONAL não era compatível com a implementação.|
|-2016345903|0x87D100D1|Conflito resolvido com duplicata. A resposta indica que a solicitação criou um conflito de atualização, que foi resolvido com a duplicação dos dados do cliente no banco de dados do servidor. A resposta inclui os dois URIs de destino da duplicata no Item do Status. Além disso, no caso de uma sincronização bidirecional, um comando Add é retornado com a definição de dados duplicada.|
|-2016345904|0x87D100D0|Conflito resolvido com o comando do cliente "vencedor". A resposta indica que há um conflito de atualização, que foi resolvido com o comando do cliente vencendo.|
|-2016345905|0x87D100CF|Conflito resolvido com a mesclagem. A resposta indica que a solicitação criou um conflito, que foi resolvido com uma mesclagem das instâncias do cliente e do servidor dos dados. A resposta inclui os URLs de origem e de destino no Item do Status. Além disso, um comando Replace é retornado com os dados mesclados.|
|-2016345906|0x87D100CE|A resposta indica que apenas parte do comando foi concluído. Se o restante do comando puder ser concluído mais tarde, quando ele for concluído outro código de status de solicitação de conclusão DEVE ser criado.|
|-2016345907|0x87D100CD|A origem DEVE atualizar seu conteúdo. O remetente da solicitação está sendo informado de que seu conteúdo DEVE ser sincronizado para obter uma versão atualizada.|
|-2016345908|0x87D100CC|A solicitação foi concluída com êxito, mas nenhum dado está sendo retornado. O código de resposta também é retornado em resposta a um Get quando o destino não tem conteúdo.|
|-2016345909|0x87D100CB|Resposta não autoritativa. A solicitação está sendo respondida por uma entidade que não é a de destino. A resposta deve ser retornada apenas quando a solicitação resultar em um código de resposta 200 do destino autoritativo.|
|-2016345910|0x87D100CA|Aceita para processamento. A solicitação para executar uma execução remota de um aplicativo ou para alertar um usuário ou aplicativo foi executada com êxito.|
|-2016345911|0x87D100C9|O item solicitado foi adicionado.|
|-2016345912|0x87D100C8|O comando SyncML foi concluído com êxito.|
|-2016346011|0x87D10065|O comando SyncML especificado está sendo executado, mas ainda não foi concluído.|

### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](../troubleshoot/how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

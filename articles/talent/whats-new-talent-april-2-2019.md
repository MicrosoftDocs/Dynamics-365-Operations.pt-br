---
title: Novidades ou alterações no Dynamics 365 for Talent (2 de abril de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8f488b0bf844fc04f07fedfa447073cdeabacc15
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517307"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-april-2-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (2 de abril de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="approval-emails-in-attract"></a>Emails de aprovação no Attract
Os novos emails de aprovação melhoram a visibilidade do processo de aprovação. Os emails são enviados aos aprovadores quando ocorre um dos seguintes cenários:

- Um solicitante envia um trabalho para aprovação.
- Um trabalho é rejeitado ou aprovado.
- Um aprovador não executou nenhuma ação em relação a uma solicitação de aprovação em 24 horas.

Você pode personalizar o conteúdo dos emails de aprovação com novos modelos.

### <a name="application-and-profile-attachments"></a>Anexos de solicitação de emprego e perfil
Melhorias na guia **Documentos** em perfis de grupos de talentos e solicitações de emprego agora mostram o nome e o tipo do documento.

## <a name="changes-in-onboard"></a>Alterações de Integração
Esta versão inclui correções de bug menores para Dynamics 365 Talent: Onboard.

## <a name="coming-soon-attract-and-onboard"></a>Em breve (Attract e Onboard)

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integração do Lifecycle Services (LCS) com Relatar um Problema
No Attract e no Onboard, os problemas registrados por usuários finais usando o recurso Relatar um Problema agora criam problemas de suporte automaticamente no projeto do LCS do cliente. Assim os administradores podem fazer a triagem dos problemas e enviá-los à Microsoft quando necessário. Isso é consistente com a forma como o Core HR lida com problemas de suporte do usuário final.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2216.

### <a name="platform-update-25"></a>Update 25 para plataforma
Para obter mais informações sobre a atualização de Plataforma 25, consulte [Exibição de recursos na atualização de Plataforma 25 do Dynamics 365 for Finance and Operations (abril de 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-25).

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Segurança de compensação avançada (fixa e variável)
Em muitas organizações, gerentes de remuneração e benefícios só podem ter acesso a alguns tipos de registro de remuneração. Esses registros podem incluir registros de executivos ou funcionários regionais. Essa alteração permite que o RH gerencie e mantenha planos de remuneração para diferentes grupos de funcionários da organização. É possível atribuir funções de segurança para planos fixos e variáveis. Essas funções de segurança determinam o acesso a planos e dados de funcionários relacionados, como registros de salário ou de bônus, por isso somente elas podem processar a remuneração dos grupos de funcionários.

### <a name="upgrade-to-common-data-service"></a>Atualizar para o Common Data Service
Os prazos finais para atualizar para o Common Data Service estão se aproximando rapidamente. Entre na central de administração do PowerApps para determinar se sua base de dados precisa ser atualizada. Para obter mais informações sobre os prazos finais e as etapas necessárias para atualizar, consulte [Fazer upgrade para o Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>Em visualização

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir que os códigos de motivo sejam especificados nos tipos de licença
As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para determinados tipos de licença em solicitações de folga
As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam pedidos de folga. Isso pode ser devido a uma diretiva da empresa ou a requisitos regulatórios. Agora você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

## <a name="coming-soon"></a>Em breve

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Melhorias na interface de usuário para verificação de funcionários duplicados
Com esta alteração, as duplicatas são detectadas conforme você digita nos campos de nome, e um status exibe o número de duplicatas localizado. Você pode selecionar o link fornecido para abrir uma nova página a fim de avaliar se deve usar ou não a correspondência detectada. Para evitar a interrupção da entrada de dados, as duplicatas não são abertas automaticamente.

###  <a name="email-support-for-alerts"></a>Suporte de email para alertas
Com a atualização de Plataforma 25, os usuários podem criar regras de alerta que enviem automaticamente notificações por email a contatos quando disparadas por um evento. 

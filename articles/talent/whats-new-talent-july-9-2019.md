---
title: Novidades ou alterações no Dynamics 365 for Talent (9 de julho de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e5bb02a7128cb920a79a5f04ac910be205aeed41
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856368"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-july-9-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (9 de julho de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Em breve no Attract
#### <a name="job-approvals-appear-on-the-home-page"></a>As aprovações de trabalho aparecem na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem revisar suas aprovações em **Atribuída(s) a você**, que mostra a ID do trabalho, o cargo, outros aprovadores e a data em que o trabalho foi atribuído. Os usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**, que mostra os aprovadores que ainda precisam aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2374.

### <a name="platform-update-28"></a>Update 28 para plataforma

Para obter mais detalhes sobre a atualização de Plataforma 28, consulte [Exibição de recursos na atualização de plataforma 28 do Dynamics 365 for Finance and Operations (julho de 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-28).

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>A entidade oferece suporte a campos personalizados no Common Data Service 

As seguintes entidades oferecem suporte aos campos personalizados: 

- **Plano de remuneração fixa**
- **Configuração do ponto de referência de compensação**
- **Linha de configuração de ponto de referência de compensação**
- **Código de ganho de folha de pagamento**
- **Período de pagamento**
- **Evento de compensação fixa**
- **Grade de remuneração**

Para exibir todas as entidades atualizadas no Talent, siga estas etapas:

1. Selecione **Administração do sistema**, selecione **Links** e, em seguida, selecione **Configuração do Common data service**.
2. Selecione o menu suspenso **Nome da entidade CDS**. Todas as entidades listadas estão na versão mais recente. 

###  <a name="full-name-added-to-worker-entity-in-common-data-service"></a>Nome completo adicionado à entidade Trabalhador no Common Data Service

O campo **Nome completo** foi adicionado à entidade **Trabalhador**.

### <a name="full-time-equivalent-higher-than-10"></a>Equivalente ao horário integral superior a 1.0

Agora, é exibido um aviso, se um valor maior que 1.0 for inserido para um funcionário em tempo integral em um cargo. 

### <a name="a-warning-no-longer-displays-on-the-worker-page-when-there-is-no-future-dated-employment"></a>Um aviso não é mais exibido na página Trabalhador quando não há emprego com data futura

Você não receberá mais uma mensagem indicando que existe um emprego futuro ao navegar para a página **Trabalhador** na lista **Funcionários existentes** no espaço de trabalho **Gerenciamento de pessoal**. 

### <a name="unable-to-delete-a-business-process-in-talent"></a>Não foi possível excluir um processo de negócios no Talent

Agora você pode excluir os processos de negócios no espaço de trabalho **Processo de negócios**.

### <a name="leave-balance-no-longer-displays-zero-for-plans-with-no-accruals-when-using-balance-as-of-accrual-period"></a>Os saldos de licença não exibem mais zero para os planos sem acumulações ao usar o Saldo no período de acumulação

Os planos configurados sem acumulações agora podem mostrar um saldo.

## <a name="in-preview"></a>Em visualização

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Os recursos de visualização estão habilitados somente em instâncias da área restrita

Quando você provisiona uma nova instância do Talent, pode especificar se o tipo de instância é **Produção** ou **Área restrita**. As instâncias do tipo **Área restrita** permitem testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância **Área restrita**, fale com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Restringir os tipos de licença em solicitações de folga

As organizações podem oferecer muitos tipos diferentes de licenças aos funcionários. Entretanto, talvez não seja apropriado para os funcionários enviar solicitações de folga para alguns tipos de licença. Esses tipos de licença podem ser gerenciadas pelo RH. Nessa versão, você pode configurar para que tipos de licença os funcionários podem enviar solicitações de folga. 

## <a name="coming-soon-in-core-hr"></a>Em breve no Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Exiba informações estendidas de desempenho no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões, que são cogeridas pelos funcionários. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos. 

### <a name="entities-supporting-custom-fields"></a>Entidades que oferecem suporte a campos personalizados

As seguintes entidades serão habilitadas para campos personalizadas no Common Data Service: 

- **Tipo de licença**
- **Conta bancária do trabalhador**
- **Calendário de trabalho**

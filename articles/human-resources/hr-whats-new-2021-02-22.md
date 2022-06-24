---
title: Novidades ou alterações no Dynamics 365 Human Resources 22 de fevereiro de 2021
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 22 de fevereiro de 2021.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d07e73ccd922e9d52a9de9260577087a50ef1da4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897825"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 22 de fevereiro de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve os recursos novos, alterados ou que serão lançados em breve no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.3988.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Aplicativo Dynamics 365 Human Resources para Microsoft Teams | [Experiência de licença e ausência de funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md)<br>[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este artigo para incluir correções de bugs feitas no build após a publicação inicial deste artigo.

| Número do problema | Problema |  Descrição |
| --- | --- | --- |
| 529994 | Modificar o campo **Conhecido como** no formulário **Trabalhador** não dispara uma atualização do Dataverse | Problema corrigido em que o Dataverse não é atualizado quando o campo **Conhecido como** é atualizado no formulário **Trabalhador**. |
| 532651 | O relatório PBI de análise de remuneração não usa a conversão de moeda ao calcular métrica para todas as empresas | Problema corrigido em que o relatório PBI de análise de remuneração não fez conversões de moeda corretas. |
| 552226 | O processamento de eventos de vida fecha e reabre planos várias vezes para evento de vida único  | Corrigido problema em que um funcionário está em várias entidades legais e um evento de vida ocorre. É gerado um registro de evento de vida para cada entidade legal na qual o funcionário está. Durante o processamento de eventos de vida, a entidade legal a ser processada deve ser selecionada. No entanto, a lógica de processamento não se limita a essa entidade legal. Ela processa todas as entidades legais e fecha e reabre os planos na entidade legal selecionada. Esta ação leva um evento de vida a ser processado várias vezes na mesma entidade legal, resultando em vários fechamentos/reaberturas de cada plano afetados pelo evento de vida. |
| 518064 | Somente um dependente selecionado em planos qualificados quando mais de um é marcado como representante padrão | Corrigido um problema em que vários representantes padrão não são selecionados automaticamente em planos qualificados. Agora você também pode designar um beneficiário principal para um contato pessoal. O beneficiário principal é listado como 100% nos planos qualificados quando há vários beneficiários. |
| 552365 | Falha em trabalhos de exportação Bring Your Own Key (BYOD) após atualização para o Platform update 40 | Corrigido um problema em que há falha em exportações BYOD após atualização do Platform update 40 ser aplicada ao ambiente. |
| 547123 | Limitar o número de tarefas consultadas na lista de tarefas no painel | O número de tarefas mostradas na lista de tarefas é limitado a 15 para corrigir um problema de desempenho causado por um número excessivo de tarefas que tentam ser carregadas. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Exibição de licenças interempresariais para gerentes | [Exibição de licenças interempresariais de funcionários para gerentes](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parâmetros de licença e ausência](./hr-leave-and-absence-parameters.md) |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Restringir a edição de detalhes de contato comercial por funcionários | [Restringir a edição de detalhes de contato comercial por funcionários](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restringir a edição de informações pessoais](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| As habilidades inseridas por um gerente para os funcionários podem ser aprovadas automaticamente por um fluxo de trabalho | Em breve. |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Atualizações de terminologia para o Microsoft Dataverse

A partir de novembro de 2020, o Common Data Service foi renomeado para [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Consulte o [anúncio oficial](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) no blog do Power Apps para saber mais. Com essa alteração de nome, alguma terminologia no Dataverse foi atualizada. Por exemplo, *entidade* agora é *tabela* e *campo* agora é *coluna*. Para obter mais informações, consulte [Atualizações de terminologia](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Nesta versão, a terminologia relacionada à integração do Dynamics 365 Human Resources com o Dataverse foi atualizada em todo o aplicativo para refletir essas alterações. Por exemplo, o formulário **Integração do Common Data Service** agora é **Integração do Microsoft Dataverse**.

Para saber mais sobre a integração do Dynamics 365 Human Resources com o Microsoft Dataverse, consulte [Configurar a integração do Microsoft Dataverse](./hr-admin-integration-common-data-service.md) e [Configurar tabelas virtuais do Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="updates-to-service-deployment"></a>Atualizações para implantação de serviço

A partir da versão 2021 de 22 de fevereiro, estamos ajustando a implantação de atualização de serviço regional. Os ajustes incluirão a rotação da ordem em que as regiões globais recebem atualizações para o serviço do Human Resources e modificações no tempo de espera entre os estágios de atualização. Essas alterações nos dão mais informações em linha com práticas de implantação segura (SDP) para melhorar a estabilidade, a qualidade e a capacidade de suporte do serviço.

Continuaremos a seguir a cadência de implantação de duas semanas. No entanto, os clientes podem perceber que as atualizações são normalmente aplicadas aos ambientes do Human Resources em um dia diferente do ciclo de duas semanas do que em versões anteriores.

Para obter mais informações sobre o processo de atualização de serviços, consulte [Processo de atualização](./hr-admin-setup-update-process.md).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
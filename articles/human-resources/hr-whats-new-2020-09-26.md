---
title: Novidades ou alterações no Dynamics 365 Human Resources 26 de setembro de 2020
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 26 de setembro de 2020.
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f78201585101e2848eded69e03d5eb4c22d7e9a
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066752"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources 26 de setembro de 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este artigo descreve os recursos novos, alterados ou que serão lançados em breve no Dynamics 365 Human Resources. Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número de build 8.1.3589-hf.3.

### <a name="new-features"></a>Novos recursos

O seguinte recurso está geralmente disponível nesta versão:

- **A atualização da plataforma 10.0.13 está disponível**: para obter mais informações sobre a atualização, consulte [Atualizações de plataforma para a versão 10.0.13 de aplicativos de finanças e operações (outubro de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md).

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações para você o mais rápido possível. Este artigo poderá ser atualizado para incluir correções de bugs feitas no build após a publicação inicial deste artigo.

| Número do problema | Problema | Descrição |
| --- | --- | --- |
| 469495 | Atualizar grade e caixa de diálogo de dimensões financeiras padrão | A grade e caixa de diálogo de dimensões financeiras é atualizada por meio do Human Resources. |
| 474887 | Item de trabalho de solicitação de licença abre o link errado em uma decisão manual | Quando uma configuração de fluxo de trabalho contém uma decisão manual, a navegação para a solicitação de licença de **Itens de trabalho atribuídos a mim** abre o link errado, mostrando um formulário em branco ou uma solicitação de licença criada pelo usuário atual, em vez do atribuído a ele para a decisão manual. |
| 474962 | A entidade de parâmetros de licença e ausência tem campos com rótulos ambíguos | Os rótulos de entidade de parâmetros de licença e ausência são atualizados para serem mais claros. |
| 481401 | O processamento de competência trava quando a base da data de acumulação é posterior à data de início e no final do mês | O processamento de competência é atualizado para não ter um atraso quando a base da data de acumulação é posterior à data de início da competência e no final do mês. |
| 447167 | As listas de registros de vencimento incluem trabalhadores inativos | A guia **Registros com data de expiração** em **Gerenciamento de pessoal** incluía trabalhadores inativos. Agora, só inclui trabalhadores ativos. |
| 486840 | A solicitação de licença errada abre em **Itens de trabalho atribuídos a mim** | A seleção de uma licença em **Itens de trabalho atribuídos a mim** não abre mais a solicitação de licença mais recente atribuída ao usuário atual. |
| 506868 | Campo **Título** do Dataverse não definido para a entidade **Cargo** | Campo **Título** nas entidades **Trabalho** e **Cargo** exibido como não especificado. Agora, o campo **Cargo** é exibido. |
| 430359 | Não é possível acessar as tarefas da lista de verificação de remoção com funções de gerente e funcionário atribuídas | Os trabalhadores com uma data de demissão futura não poderão acessar suas tarefas da lista de verificação se tiverem apenas uma função de funcionário ou gerente. Agora, os usuários com apenas uma função de funcionário ou gerente podem acessar as tarefas de remoção com uma data de demissão futura. |
| 458102 | O novo funcionário não aparece na entidade **Informações da folha de pagamento do trabalhador** quando criado | Os novos funcionários são incluídos na entidade de informações da folha de pagamento do trabalhador sem precisar abrir as informações de folha de pagamento do funcionário antes de exportar a entidade. |

## <a name="in-preview"></a>Em visualização

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Plano de versão | Documentação |
| --- | --- | --- |
| Aplicativo Human Resources no Microsoft Teams | [Experiência de licença e ausência de funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md)<br>[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md) |
| Aprovações e solicitações de fluxo de trabalho avançadas | [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opção de configuração para posicionar a lista Itens de trabalho atribuídos a mim](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>Em breve

Este recurso novo está agendado para uma versão futura:

- [Personalizar links no autoatendimento para gerentes](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2019 ciclo de lançamentos 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Recursos adicionais

[O que há de novo ou alterado no Human Resources](hr-admin-whats-new.md)
[Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[Atualizar processo](hr-admin-setup-update-process.md)
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

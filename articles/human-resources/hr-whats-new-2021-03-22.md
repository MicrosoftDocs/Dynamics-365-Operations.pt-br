---
title: Novidades ou alterações no Dynamics 365 Human Resources 22 de março de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 22 de março de 2021.
author: marcelbf
ms.date: 03/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 13520ca55c98fb1acb6185af393550b12fbc2072
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693518"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 22 de março de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4049.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Opção para forçar o cancelamento e redefinir trabalhos em lotes presos (560976) | NA | [Redefinir trabalhos em lotes presos](./hr-admin-troubleshooting-batch-execution.md) |
| Atualizações secundárias de UX para criar novo plano de benefícios (419941) | NA | [Criar um plano de benefícios](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema |  descrição |
| --- | --- | --- |
| 554239 | Melhorias de desempenho para entidades relacionadas à tabela **BusinessProcessTaskAssignment** | Melhore o desempenho de entidades relacionadas à tabela **BusinessProcessTaskAssignment** adicionando índices sugeridos a ela. |
| 566061 | Remover o código de fallback da entidade V2 da sincronização noturna | Remova o código de fallback da V2 para a sincronização noturna do Dataverse. O fallback não é mais necessário e impede que a sincronização filtrada funcione conforme o esperado. A alteração melhora a consistência da sincronização de dados do Dataverse. |
| 538024 | Erro em Planos de benefícios do trabalhador > Remover check-out | Corrigido o erro ao remover o check-out da opção do plano de benefícios do formulário de benefícios do trabalhador. |
| 557965 | Espaço de trabalho de **Benefícios**: o link **Eventos de vida ativos** deve estar sempre visível na seção **Links** | Corrigido o problema em que o link **Eventos de vida ativos** estava visível na seção **Links**, mas gerava um erro ao tentar navegar se o recurso **(Versão preliminar) Espaço de trabalho do gerenciamento de benefícios** não estivesse habilitado. Para obter mais informações sobre como habilitar o espaço de trabalho, consulte o [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md). |
| 556672 | Não é possível processar acúmulos para um funcionário demitido quando **Entrada de funcionário simplificada** estiver habilitado no Gerenciamento de recursos | A opção de acumular planos de ausência e de licença foi adicionada a **Mais opções** em **Histórico profissional** dos funcionários quando **Entrada de funcionários simplificada** for habilitada no gerenciamento de recursos. |
| 562656 | O item de menu **SysRecordChangeLogValidTimeState** deve ser incluído em um privilégio de segurança e em uma extensão do direito de segurança **SystemExternalBasicMaintain** | As funções de administrador que não são do sistema não tinham o botão **Exibir alterações** nos formulários do gerenciador de datas. |
| 505989 | Processamento de eventos de vida: altere a elegibilidade não processada corretamente devido à data usada | Corrigido o problema em que a alteração no processamento da elegibilidade dependia da data inicial da posição e não apenas da posição atual. |
| 562286 | Demitir trabalhador envia várias atualizações para o Dataverse | Quando um trabalhador é demitido, mais de uma operação de atualização é enviada para o Dataverse, resultando em duas notificações de atualização para a mesma alteração. Isso pode causar vários gatilhos se um fluxo do Power Automate estiver configurado para disparar com a ação. |
| 527340 | O erro "DateTime não representável" é exibido ao abrir os registros de licença e ausência | Ao selecionar um registro de licença e ausência, o erro não será mais exibido. |
| 561663 | Aumentar o intervalo do tempo de espera para o provisionamento de cluster | Melhore a estabilidade da infraestrutura e a consistência do provisionamento com atualizações do provisionamento de cluster. |
| 486129 | Não é possível editar campos personalizados em **Cargos > Gerenciar alterações** | Corrigido um problema em que os campos não podiam ser editados na guia **Gerenciar alterações** em **Cargos**. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Restringir a edição de detalhes de contato comercial por funcionários | [Restringir a edição de detalhes de contato comercial por funcionários](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restringir a edição de informações pessoais](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| As habilidades inseridas por um gerente para os funcionários podem ser aprovadas automaticamente por um fluxo de trabalho | Em breve. |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Novidades ou alterações no Dynamics 365 Human Resources 8 de março de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 8 de março de 2021.
author: marcelbf
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 37e4ca0658da4ac8e199223496f715ff1cd92653
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056988"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 08 de março de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4017.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Exibição de licenças interempresariais para gerentes | [Exibição de licenças interempresariais de funcionários para gerentes](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parâmetros de licença e ausência](./hr-leave-and-absence-parameters.md) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema |  descrição |
| --- | --- | --- |
| 486611 | A licença de ausência é mostrada no calendário de licenças quando **Desabilitar licença em todos os calendários** está habilitado | Se **Desabilitar licença em todos os calendários** estiver habilitado, as informações de licença não serão mais exibidas quando o recurso Aprimoramentos do calendário de licença e ausência estiver habilitado.|
| 508972 | A entidade Transação bancária de licença e ausência não tem validação de registro | Ao usar a entidade Transação bancária de licença e ausência, os funcionários não inscritos em um plano não poderão mais ser importados. |
| 554854 | Atualizar calendários em erros da Entidade de emprego se a entidade legal padrão em Opções de usuário for diferente | O uso da Entidade de emprego para atualizar o calendário de um funcionário não retornará mais um erro se a entidade legal padrão em Opções de usuário for diferente. |
| 558347 | "Não é possível criar um registro em configurações do formulário (FormRunConfiguration)" aparece ao carregar a página inicial. | As personalizações levam o erro "Não é possível criar um registro em configurações do formulário (FormRunConfiguration)" a aparecer ao carregar a página inicial. |
| 557327 | Espaço de trabalho de gerenciamento de benefícios: a lacuna aparece acima da grade. | Problema corrigido em experiência do usuário com uma lacuna não intencional que aparece nas bordas da grade de tabelas no espaço de trabalho Benefícios. |
| 557334 | Espaço de trabalho de gerenciamento de benefícios: a caixa suspensa de seleção **Período** só deve aparecer na guia **Resumo** | A caixa suspensa de seleção **Período** de benefícios agora aparece somente quando a guia **Resumo** está ativa no espaço de trabalho Benefícios e não nas seções **Resultados do processo** e **Links**. |
| 557336 | Espaço de trabalho de gerenciamento de benefícios: o texto **Abrir inscrição com planos de check-out** está truncado na exibição de blocos | Texto alterado no modo de exibição de blocos para **Planos de check-out...abrir inscrição** para evitar o truncamento do contexto necessário. |

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
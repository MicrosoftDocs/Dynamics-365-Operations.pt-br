---
title: Novidades ou alterações no Dynamics 365 Talent (10 de dezembro de 2019)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/10/2019
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
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 18f86f5d87b780d5d4ffc83330d389077987dda6
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528162"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-10-2019"></a>Novidades ou alterações no Dynamics 365 Talent (10 de dezembro de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2660. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Espaço de trabalho do gerenciamento de recursos

O espaço de trabalho **Gerenciamento de recursos** fornece uma lista de recursos entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles. Para obter mais informações sobre o Gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias. Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia. Assim que vir novos recursos no espaço de trabalho **Gerenciamento de recursos**, você poderá ativá-los. Alguns recursos podem ser ativados por padrão.
 
Às vezes, um recurso integral estará ativado por padrão e não poderá ser desativado (por exemplo, o espaço de trabalho **Gerenciamento de recursos**).
 
Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção. O espaço de trabalho **Gerenciamento de recursos** indica quando a versão prévia do recurso se tornará obrigatória. Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais. Você não pode desativar recursos obrigatórios. Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.

### <a name="streamlined-worker-form-has-moved-to-the-feature-management-workspace-390583"></a>O formulário simplificado do trabalhador foi movido para o espaço de trabalho Gerenciamento de recursos (390583)

Com esta alteração, o formulário simplificado do trabalhador pode ser habilitado no espaço de trabalho do **Gerenciamento de recursos**. Este recurso foi movido do formulário **Parâmetros do sistema** em **Administração do sistema**.

### <a name="prevent-hcmworkerpayrollinfo-records-from-being-written-without-a-worker-value-394526"></a>Impeça que os registros HcmWorkerPayrollInfo sejam gravados sem um valor para trabalhador (394526)

Nesta versão, os registros **HcmWorkerPayrollInfo** não são mais criados sem uma referência de trabalhador neste cenário. 

### <a name="message-log-associated-to-the-action-isnt-populated-when-the-action-fails-to-complete-374007"></a>O log de mensagens associado à ação não é populado quando a ação não é concluída (374007)

Esta versão inclui uma alteração para popular o log de mensagens de ação quando uma ação falhar em determinados cenários. 

### <a name="common-data-service-integration-batch-job-creation-388030"></a>Criação de trabalho em lotes de integração do Common Data Service (388030)

Com esta alteração, os trabalhos em lotes para a integração do Common Data Service serão criados quando o serviço estiver habilitado.

### <a name="additional-pick-list-values-to-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Os valores adicionais da lista de separação para campos personalizados não são refletidos no Common Data Service após clicar em aplicar no formulário de campos personalizados (379599)

Com esta alteração, os novos valores da lista de separação em Talent agora são sincronizados com o Common Data Service ao aplicar as alterações.

### <a name="update-to-common-data-service-for-then-leave-bank-transaction-entity-turns-into-an-insert-on-talent-side-352938"></a>Atualizar para o Common Data Service faz com que a entidade Transação bancária da licença seja transformada em uma inserção no Talent (352938)

Esta alteração corrige um problema que ao atualizar Transação bancária da licença, um novo registro era criado no Talent.

## <a name="in-preview"></a>Em visualização

Os recursos da versão prévia estão disponíveis somente em ambientes de **Área restrita**.

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.


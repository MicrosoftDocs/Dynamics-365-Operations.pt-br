---
title: Novidades ou alterações no Dynamics 365 Talent (23 de outubro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/23/2019
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
ms.search.validFrom: 2019-10-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 27cb4a7c125cb2b330dff083c8ed0c1ee89c0e7e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527994"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-23-2019"></a>Novidades ou alterações no Dynamics 365 Talent (23 de outubro de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2569. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-30-for-finance-and-operations-apps"></a>Atualização de plataforma 30 para os aplicativos do Finance and Operations

Para obter mais informações, consulte [Novidades ou alterações na Atualização de plataforma 30 para os aplicativos Finance and Operations (novembro de 2019)](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-platform-update-30).

### <a name="remove-benefits-open-enrollment-preview-feature"></a>Remova a versão prévia do recurso de inscrição aberta de benefícios

Junto com o comunicado em [Investimentos estratégicos](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) na postagem do blog de incentivo à excelência operacional do core HR, a Microsoft removerá a versão prévia da inscrição aberta de benefícios da versão prévia pública em 18 de outubro de 2019. Em vez disso, a nova funcionalidade será lançada no futuro. O uso da produção do recurso de inscrição aberta de benefícios atualmente na versão prévia pública não será compatível.

### <a name="error-while-selecting-the-countryregion-on-the-worker-form-a-second-time-350294"></a>Erro ao selecionar país/região no formulário do trabalhador pela segunda vez (350294)

Na versão desta semana, o problema foi corrigido ao selecionar país/região no formulário **Trabalhador**.

### <a name="financial-dimension-values-default-to-the-combination-display-field-when-do-not-allow-manual-entry-is-set-to-true-340097"></a>Os valores da dimensão financeira são predefinidos para o campo de Exibição da combinação quando a entrada manual Não permitir for definida como verdadeira (340097)

Com esta alteração, ao configurar as dimensões financeiras e usar a opção de não permitir a entrada manual, o sistema predefinirá corretamente o valor da dimensão no campo **Exibição da combinação**.

### <a name="new-relationship-types-should-be-added-to-relationship-lookup-in-the-personal-contacts-form-347691"></a>Novos tipos de relacionamento devem ser adicionados à Pesquisa de relacionamento no formulário de contatos pessoais (347691)

Esta versão inclui novos recursos para adicionar tipos de relacionamento na tabela **Tipos de relacionamento** e refletir essas alterações na pesquisa de relacionamento para contatos pessoais.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-379599"></a>Os valores adicionais da lista nos campos personalizados não são refletidos no Common Data Service (379599)

Com a versão desta semana, adicionar um novo valor da lista a um campo personalizado existente que já está sincronizado com o Common Data Service, os novos valores da lista de separação aparecerão após aplicar as alterações à entidade.

### <a name="on-the-terms-of-employment-page-all-employees-terms-of-employment-appear-after-selecting-open-in-excel-348073"></a>Na página Contrato de trabalho, os contratos de trabalho de todos os funcionários aparecerão após selecionar Abrir no Excel (348073)

Com esta versão, somente o contrato de trabalho dos funcionários selecionados será aberto no Excel. A segurança de toda a empresa também será respeitada.

### <a name="the-association-between-the-work-calendar-holiday-entity-and-the-work-calendar-entity-is-missing-in-common-data-service-324178"></a>A associação entre a entidade de feriados do Calendário de atividades e a entidade Calendário de atividades está ausente no Common Data Service (324178)

Este relacionamento foi adicionado com a versão. Esta alteração habilitará a exibição dos dias úteis de um funcionário no PowerApps. 

### <a name="error-when-using-employee-self-service-workflows-with-configurable-hierarchies-370132"></a>Erro ao usar fluxos de trabalho do employee self-service com hierarquias configuráveis (370132)

Nesta versão, há um melhor sistema de mensagens disponível para configurar fluxos de trabalho usando hierarquias configuráveis. 

### <a name="system-allows-creation-of-new-positions-where-the-available-for-assignment-date-is-earlier-than-the-activation-date-340103"></a>O sistema permite a criação de novas posições, onde a data de Disponível para atribuição for anterior à data de Ativação (340103)

Esta alteração exibirá um aviso quando a data **Disponível para atribuição** for anterior à data de **Ativação** da posição.

## <a name="coming-soon"></a>Em breve

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.

### <a name="feature-management-workspace"></a>Espaço de trabalho do gerenciamento de recursos

Os recursos são adicionados e atualizados em cada versão. A experiência de gerenciamento de recursos fornece um espaço de trabalho no qual você pode exibir uma lista dos recursos que foram entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles.

Para saber mais sobre as mudanças que acompanham o gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview)

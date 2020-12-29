---
title: Novidades ou alterações no Dynamics 365 Talent (19 de novembro de 2019)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/19/2019
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
ms.search.validFrom: 2019-11-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aa984a01e9da30e6da07516fa2986833366a882b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527135"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-19-2019"></a>Novidades ou alterações no Dynamics 365 Talent (19 de novembro de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2621. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-31-for-finance-and-operations-apps"></a>Atualização de plataforma 31 para os aplicativos do Finance and Operations

Para obter mais informações, consulte [Versões prévias de recurso na Atualização de plataforma 31 para aplicativos do Finance and Operations (janeiro de 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-31).

### <a name="feature-management-workspace-383856"></a>Espaço de trabalho do gerenciamento de recursos (383856)

O espaço de trabalho **Gerenciamento de recursos** fornece uma lista de recursos entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles. Para obter mais informações sobre o Gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias. Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia. Assim que vir novos recursos no espaço de trabalho **Gerenciamento de recursos**, você poderá ativá-los. Alguns recursos podem ser ativados por padrão.
 
Às vezes, um recurso integral estará ativado por padrão e não poderá ser desativado (por exemplo, o espaço de trabalho **Gerenciamento de recursos**).
 
Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção. O espaço de trabalho **Gerenciamento de recursos** indica quando a versão prévia do recurso se tornará obrigatória. Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais. Você não pode desativar recursos obrigatórios. Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.

### <a name="message-appears-when-canceled-action-exists-for-a-position-382887"></a>A mensagem aparecerá quando existir uma ação cancelada para uma posição (382887)

A seguinte mensagem não aparecerá mais quando você selecionar uma posição específica e só houver uma ação cancelada disponível para a posição: **Uma ação incompleta está em andamento para a posição xxxxxx**.

### <a name="in-learning-analytics-the-course-type-and-status-display-incorrect-data-381151"></a>Na análise de aprendizado, o Tipo de curso e o Status exibem dados incorretos (381151)

A versão desta semana atualizou a análise de aprendizado para exibir corretamente **Tipo de curso** e **Status**.

### <a name="personnel-number-should-display-in-the-new-worker-form-banner-383832"></a>O Número de equipe deve ser exibido na faixa do formulário Novo trabalhador (383832)

No formulário **Novo trabalhador** , **Número da equipe** agora é exibido na faixa de referência rápida.

### <a name="position-start-date-determines-the-job-record-to-use-when-retrieving-a-compensation-level-during-hire-350361"></a>A data inicial da posição determina o Registro de trabalho a ser usado na recuperação de um nível de compensação durante a contratação (350361)

Nesta versão, **Data inicial de compensação** determina o nível atribuído ao novo trabalho.

### <a name="custom-pick-list-fields-in-the-position-table-arent-synchronized-to-common-data-service-387503"></a>Os campos de lista de separação personalizados na tabela Posição não são sincronizados para o Common Data Service (387503)

Nesta versão, os itens de lista de separação são sincronizados com o Common Data Service.

### <a name="worker-address-entity-doesnt-synchronize-with-common-data-service-while-importing-new-data-349673"></a>A entidade Endereço do trabalhador não sincroniza com o Common Data Service durante a importação de novos dados (349673)

Na versão desta semana, os dados de endereço agora são sincronizados com o Common Data Service durante a importação de novos dados.

## <a name="in-preview"></a>Em visualização

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.

---
title: Espaço de trabalho de gerenciamento de benefícios
description: Este tópico descreve o espaço de trabalho Gerenciamento de benefícios no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6cc1432e108c74706dea124a62024272e65b6c1
ms.sourcegitcommit: 47a3ad71210c7ac84d0c25e913c440b5ba205282
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7512464"
---
# <a name="benefits-management-workspace"></a>Espaço de trabalho Gerenciamento de benefícios

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

Este tópico descreve o espaço de trabalho **Gerenciamento de benefícios** no Dynamics 365 Human Resources.

> [!NOTE]
> Para exibir o espaço de trabalho **Gerenciamento de benefícios**, você deve primeiro habilitar o recurso **(Versão preliminar) Espaço de trabalho de gerenciamento de benefícios** no Gerenciamento de recursos. Para obter mais informações sobre como habilitar os recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md).<br><br>![Habilitar espaço de trabalho Gerenciamento de benefícios.](./media/hr-benefits-management-workspace-enable.png)

O espaço de trabalho **Gerenciamento de benefícios** fornece uma exibição rápida dos itens de benefícios que exigem sua atenção. Nesta página, você pode ver:

- Totais de itens aguardando ação
- Trabalhadores com seleções não confirmadas
- Trabalhadores recém-inscritos em benefícios
- Trabalhadores com eventos de vida futuros
- Novos contratados que não estão inscritos
- Trabalhadores com eventos de vida ativos
- Trabalhadores com inscrições abertas que não optaram por planos

![Espaço de trabalho de gerenciamento de benefícios.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Exibir itens de ação

Você pode exibir itens de ação selecionando um bloco ou uma guia. Se você selecionar uma guia, poderá exibir e selecionar trabalhadores na página do espaço de trabalho.

![Itens de ação.](./media/hr-benefits-management-workspace-action-items.png)

Se você selecionar um bloco, Acesse a página dessa área. Por exemplo, a seleção de um desses blocos exibe a página **Planos de benefícios do trabalhador**, filtrada para os funcionários nos quais você precisa executar uma ação:

- **Seleções não confirmadas**
- **Abrir inscrições com planos sem check-out**
- **Inscrito em benefícios**
- **Nova contratação não inscrita**

![Planos de benefícios para o trabalhador.](./media/hr-benefits-management-workspace-plans.png)

A seleção de **Eventos de vida ativos** ou **Eventos de vida futuros** levará você a uma lista de eventos de vida ativos ou futuros.

![Eventos de vida.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>Processando

Para processar a qualificação da inscrição, eventos de vida ou atualizações da alteração de taxa, selecione o item apropriado na barra de navegação.

![Processamento.](./media/hr-benefits-management-workspace-processing.png)

Para exibir resultados do processo, selecione **Resultados do processo** na página.

![Resultados do processo.](./media/hr-benefits-management-workspace-process-results.png)

Para obter mais informações sobre o processamento de benefícios, consulte:

- [Processar qualificação da inscrição](hr-benefits-process-enrollment-eligibility.md)
- [Processar alterações de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Processar qualificação para eventos de vida](hr-benefits-process-life-event-eligibility.md)
- [Processar eventos de vida](hr-benefits-process-life-events.md)
- [Processar alterações de taxa](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Alterar período

Para exibir um período de benefícios diferente, selecione-o na lista suspensa **Período**.

![Alterar período.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>Guia Registro aberto

Você pode exibir itens de ação selecionando um bloco ou uma guia. Se você selecionar uma guia, poderá exibir e selecionar trabalhadores na página do espaço de trabalho.
A guia **Registro aberto** fornece métricas-chave para o processo de registro aberto. 

As informações sobre o registro aberto serão exibidas 30 dias antes da **Data de início do registro**. Isso é definido na configuração de **Períodos** em **Gerenciamento de benefícios** > **Links** > **Períodos**, no campo **Data de início da inscrição**.  Para alterar essa configuração, acesse **Parâmetros compartilhados do Human Resources** > **Gerenciamento de benefícios** > **Opções de registro aberto** e atualize o campo **Número de**.  

As informações a seguir estão disponíveis na guia **Registro aberto**:
 - Funcionários que não iniciaram o processo de registro aberto
 - Funcionários com eleições em processo
 - Funcionários que concluíram o processo de eleição
 - Seleções não confirmadas

**Blocos do resumo**

- **Não iniciado** – o bloco **Não iniciado** mostra uma contagem de funcionários que não iniciaram o processo de registro. O bloco **Não iniciado** é uma lista filtrada que mostra somente os funcionários que não têm planos selecionados, renunciados ou com check-out para o período de planejamento de registro aberto. Os planos obrigatórios são ignorados e não incluídos, pois são selecionados por padrão para o funcionário.  É possível fazer uma busca detalhada nesse bloco para ver uma lista de funcionários que não iniciaram o processo de registro aberto na página **Plano de benefícios do trabalhador**.

  > [!NOTE]
  > Se você não quiser rastrear o andamento do registro aberto para um **Tipo de plano**, será possível excluí-lo acessando **Gerenciamento de benefícios** > **Links** > **Parâmetros de autoatendimento para funcionários** > **Configuração do bloco de planos de benefícios** e atualizando o campo **Rastrear o progresso do registro aberto**.  Por exemplo, você pode ter planos criados em que **Tipo de plano** = **Outro**. Esses planos podem ser planos opcionais para os quais você não deseja rastrear o andamento do registro. Se você não selecionar esse tipo de plano, os planos desses tipos serão ignorados ao rastrear o andamento ou a conclusão do registro na guia **Registro aberto**. Essa configuração se aplica ao tipo de plano selecionado para todos os períodos e entidades legais.

- **Em andamento** – o bloco **Em andamento** fornece uma contagem de funcionários com eleições em andamento. O bloco **Em andamento** é uma lista filtrada que mostra apenas funcionários com pelo menos um plano renunciado ou selecionado. Os planos obrigatórios são ignorados e não incluídos, pois são selecionados por padrão para o funcionário. Você pode resumir neste bloco para ver os planos selecionados e renunciados na página **Atualização em Massa dos Planos de Benefícios do Trabalhador**.

- **Registrado em benefícios** – o bloco **Registrado em benefícios** oferece uma contagem de funcionários que são totalmente registrados em benefícios. O formulário **Registrado em benefícios** é uma lista filtrada que mostra os funcionários com todos os planos selecionados ou renunciados. A consulta excluirá planos que não estão sendo rastreados para registro aberto na página **Parâmetros de autoatendimento para funcionários**. Você pode detalhar esse bloco para ver uma lista de funcionários na página **Planos de benefícios do trabalhador**.

- **Seleções não confirmadas** – o bloco **Seleções não confirmadas** mostra uma contagem de funcionários com planos selecionados ou renunciados e que precisam ser confirmados. Você pode detalhar esse bloco para exibir a página **Atualização em Massa dos Planos de Benefícios do Trabalhador**.

**Atividade**

- **Não iniciado** – a guia **Não iniciado** exibe uma lista de funcionários que não iniciaram o processo de registro. O bloco **Não iniciado** é uma lista filtrada que mostra somente os funcionários que não têm planos selecionados, renunciados ou com check-out para o período de planejamento de registro aberto. Os planos obrigatórios são ignorados e não incluídos, pois são selecionados por padrão para o funcionário. Você pode detalhar o trabalhador para exibir a página **Detalhe dos planos de benefícios do trabalhador**.

- **Eleições em andamento** – a guia **Eleições em andamento** exibe uma lista de funcionários com eleições em andamento. **Eleições em andamento** é uma lista filtrada que mostra apenas funcionários com pelo menos um plano renunciado ou selecionado. Os planos obrigatórios são ignorados e não incluídos, pois são selecionados por padrão para o funcionário. Você pode detalhar o trabalhador para exibir a página **Detalhe dos planos de benefícios do trabalhador**.

## <a name="view-more-options"></a>Exibir mais opções

Para exibir mais informações e/ou ações adicionais, selecione **Links**.

![Links.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Consulte também

[Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md)

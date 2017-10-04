---
title: "Home page de Orçamento"
description: "Este tópico fornece uma visão geral dos componentes da funcionalidade de orçamento, ferramentas de orçamento e recursos de relatório no Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: twheeloc
manager: AnnBe
ms.date: 08/09/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 529751c09b8f99f986cad23a633bea661929d558
ms.openlocfilehash: e59c29370353a6e4a67d2b892e2024ca78d560fc
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---

# <a name="budgeting-home-page"></a>Home page de Orçamento

[!include[banner](../includes/banner.md)]


Este tópico fornece uma visão geral dos componentes da funcionalidade de orçamento, ferramentas de orçamento e recursos de relatórios no Finance and Operations. 

<a name="components-of-budgeting-functionality"></a>Componentes da funcionalidade de orçamento
-------------------------------------

O ciclo de planejamento de recursos para uma empresa consiste, em geral, em planejar, orçar e prever atividades.

[![Componentes da funcionalidade de orçamento](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

Os processos de planejamento estratégico de longo prazo e planejamento de orçamento anual têm suporte por meio de um documento de plano de orçamento. Os documentos do plano de orçamento são totalmente integrados ao Microsoft Excel. Os usuários podem configurar cenários monetários e quantitativos ilimitados, e também podem definir uma hierarquia organizacional de orçamento para oferecer suporte aos métodos de orçamento de cima para baixo e de baixo para cima. Após um orçamento ser estabelecido e aprovado no Finance and Operations, você converte o plano de orçamento em uma entrada de registro de orçamento. As entradas de registro de orçamento fornecem ferramentas para manter o orçamento e manter os valores rastreáveis através de códigos de orçamento. As entradas de registro de orçamento permitem revisar orçamentos originais, executar transferências, e manter valores de orçamento do ano anterior. Com base no orçamento estabelecido, uma empresa por habilitar o controle de orçamento. O nível de controle depende da cultura organizacional e do nível organizacional de maturidade. As organizações que têm um nível de maturidade baixo podem deixar o orçamento "no estado em que se encontra" e talvez sejam mais reativas do que pró-ativas se um orçamento não atender às expectativas. Outras organizações podem habilitar políticas de controle de orçamento que impedem os usuários de fazer compras se os fundos de orçamento não estão disponíveis.

Por fim, as organizações muito maduras podem estabelecer uma cultura organizacional na qual os funcionários são instruídos sobre os objetivos organizacionais e acompanham esses objetivos por meio de políticas como “Considerar reunião online em vez de deslocamento”. O Finance and Operations inclui uma estrutura de controle de orçamento que permite ao gerenciamento da empresa optar pelo controle rígido (o qual evita lançamentos que excedem o orçamento) ou controle flexível (onde os usuários são alertados de que excederão os fundos de orçamento disponíveis, mas podem decidir como proceder). Por fim, você pode usar as previsões de rolamento. Uma previsão de rolamento é uma comparação regular de orçamento com números reais e é usada para definir o quão bem a empresa opera em relação ao orçamento. Uma previsão de rolamento também é usada para identificar tendências. No Finance and Operations, as previsões de rolamento têm suporte por meio de um documento de plano de orçamento na forma de atividades iniciais de planejamento. As previsões de rolamento podem ser executadas em paralelo ao planejamento para o próximo ciclo orçamentário.

-   [Orçamento básico: visão geral e configuração](basic-budgeting-overview-configuration.md)
-   [Controle de orçamento: visão geral e configuração](budget-control-overview-configuration.md)
-   [Planejamento de orçamento: visão geral e configuração](budget-planning-overview-configuration.md)
-   [Previsão de posição](position-forecasting.md)
-   [Documentos de justificativa de planejamento de orçamento](budget-planning-justification-docs.md)
-   [Modelos de planejamento de orçamento do Microsoft Excel](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-finance-and-operations"></a>Ferramentas de orçamento no Finance and Operations
[![Ferramentas de orçamento](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Os recursos adicionais de planejamento e orçamento estão disponíveis no Finance and Operations e são integrados aos orçamentos do razão.

-   **Orçamentos de força de trabalho** – O orçamento de força de trabalho inclui um planejamento detalhado de componente de custo de orçamento para posições, grupos de compensação e assim por diante.
-   **Orçamentos de ativos fixos** – Com base nas informações de ativos fixos, você pode calcular a depreciação planejada e registrar outras transações planejadas relacionadas a ativos fixos.
-   **Orçamentos de projeto** – No módulo dos projetos, você pode criar previsões de projeto detalhadas. As previsões de projetos incluirão detalhes sobre horas, despesas, taxas e itens planejados.
-   **Previsão de demanda**– Você pode estimar a demanda futura de estoque e criar previsões de demanda, com base nos dados históricos de transação.

Para obter informações sobre como exibir dados de planejamento de outros módulos nos planos de orçamento, consulte [Integração do planejamento de orçamento com outros módulos](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Recursos de relatório e de interface de usuário
No Finance and Operations, os usuários podem criar planos de orçamento diretamente no cliente do Finance and Operations (usando uma página configurável do documento do plano de orçamento) ou no Excel. O Excel fornece vários recursos adicionais. Por exemplo, você pode usar dados externos como uma fonte para um plano de orçamento, realizar cálculos personalizados e usar Tabela Dinâmica e gráficos da Microsoft. A maioria das variáveis no processo de planejamento de orçamento podem ser configuradas. 

Por exemplo, você pode definir quem faz o orçamento, o que é orçado e a aparência do processo. Embora você possa usar o Excel para o planejamento de orçamento, o Finance and Operations é mantido como uma origem única da verdade e ajuda a evitar problemas de controle de orçamento. Os processos periódicos podem ser usados para levar os dados iniciais do orçamento para o plano de orçamento. Para relatórios, o Finance and Operations oferece um conjunto de páginas de consulta padrão que permitem exibir e analisar dados do orçamento. Os dados do plano de orçamento podem ser acessados por meio do Management Reporter, e cenários de plano de orçamento separados podem ser exibidos como colunas no relatório do Management Reporter.







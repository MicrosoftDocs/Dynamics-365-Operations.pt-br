---
title: Home page do planejamento mestre
description: O Planejamento mestre permite que as empresas determinem e equilibrem a necessidade futura de matérias-primas e a capacidade de cumprir as metas da empresa.
author: ChristianRytt
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7dd25fdd1549fb2fddff57dc2d9cf8762cfd6823
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416518"
---
# <a name="master-planning-home-page"></a>Home page do planejamento mestre

[!include [banner](../includes/banner.md)]

Essencialmente, o Planejamento mestre permite que as empresas determinem e equilibrem a necessidade futura de matérias-primas e a capacidade de cumprir as metas da empresa. O Planejamento mestre avalia o seguinte:

- Quais matérias-primas e capacidades estão disponíveis atualmente?
- Quais matérias-primas e capacidades são necessárias para concluir a produção? Por exemplo, o que deve ser fabricado, comprado, transferido ou separado como estoque de segurança antes de você concluir a produção?

O Planejamento mestre usa as informações para calcular as necessidades e gerar ordens planejadas.

Os três processos de planejamento principais são:

- **Planejamento mestre** - O Planejamento mestre calcula os requisitos líquidos. Ele se baseia em ordens reais atuais e permite que as empresas controlem o reabastecimento do estoque a curto prazo diariamente. Outro termo para descrevê-lo é o *Plano de requisições líquidas*. Para obter mais informações, consulte [Visão geral de Planos mestre](master-plans.md).

- **Planejamento de previsão** - O Plano de previsão calcula os requisitos brutos. Ele se baseia em projeções futuras (ou previsões) e permite que as empresas realizem o planejamento de materiais e capacidade a longo prazo. Para obter mais informações, consulte [Visão geral da previsão de demanda](introduction-demand-forecasting.md).

- **Planejamento mestre intercompanhia** - O plano mestre intercompanhia calcula requisições líquidas entre entidades legais. Ele conecta demanda e fornecimento entre as empresas, não apenas em demanda e fornecimento de confirmação em curto prazo, mas também em demanda e fornecimento planejado a longo prazo. Para obter mais informações, consulte [Planejamento de intercompanhias](planning-optimization/Intercompany-planning.md).

As empresas podem alterar a saída do plano. Elas podem realizar alteração líquida, regenerativa ou ambas. Planos regenerativos atualizam todos os requisitos, enquanto planos de alteração líquida atualizam apenas o plano nos itens com novos requisitos que entraram desde a última execução do agendamento.

Os planos de agendamento do planejamento mestre geralmente envolvem o curto prazo, o que pode significar qualquer período de uma semana a seis meses. O módulo Planejamento mestre determina as necessidades de fornecimento (materiais) e capacidade (recursos) que atenderão à demanda atual (os requisitos líquidos). Na maioria das empresas, isso é ampliado para incluir o prazo de entrega cumulativo mais longo entre os produtos a serem recebidos.

## <a name="learning-map"></a>Mapa de aprendizado

O mapa de aprendizado a seguir mostra os principais conceitos e tarefas que compõem a estrutura do módulo de Planejamento mestre. Clique nos links da seção [Links rápidos](#quick-links) para aprender a usar o módulo.

[![Mapa de aprendizado do planejamento mestre.](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>Links Rápidos

- [Visão geral de planos mestres](master-plans.md)  
- [Gerar um plano restrito](./tasks/constrained-plan.md)
- [Criar um plano de materiais para coprodutos](./tasks/create-material-plan-co-products.md)
- [Visão geral de planejamento mestre e funcionalidade multissite](master-plan-multisite-functionality.md)
- [Criar um plano intercompanhia](./tasks/create-intercompany-plan.md)
- [Visão geral da previsão de demanda](introduction-demand-forecasting.md)
- [Chaves de redução da previsão](reduction-keys.md)

## <a name="additional-resources"></a>Recursos adicionais

### <a name="roadmaps"></a>Roteiros

Visite o [Roteiro do Microsoft Dynamics 365](https://roadmap.dynamics.com/) para conferir os novos recursos que foram lançados e os novos recursos em desenvolvimento.

### <a name="blogs"></a>Blogs

Você encontra opiniões, notícias e outras informações sobre Planejamento mestre e outras soluções no [Blog da Equipe Dynamics AX Manufacturing R&D](/archive/blogs/axmfg/) e no [Blog da equipe do Supply Chain Management no Dynamics AX R&D](https://blogs.msdn.microsoft.com/dynamicsaxscm).

### <a name="task-guides"></a>Guias de tarefas

A ajuda adicional está disponível como guias de tarefas. Para acessar os guias de tarefas, clique no botão **Ajuda** em qualquer página.

### <a name="webinars"></a>Webinars

[Usar o Azure Machine Learning para previsão de demanda](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)

### <a name="tech-conference-recordings"></a>Gravações de conferências sobre tecnologia

- [Estender a funcionalidade de previsão de demanda](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
- [Planejamento mestre – dicas e truques para solucionar problemas de desempenho](https://youtu.be/7v8BPmEs9Dg)
- [Ajuste de desempenho do MRP](https://youtu.be/RLXybx20B5o)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
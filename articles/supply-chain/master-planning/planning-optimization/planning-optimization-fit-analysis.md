---
title: Análise de ajuste da Otimização de Planejamento
description: Este tópico explica como verificar sua configuração e seus dados atuais em relação aos recursos da funcionalidade Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f669499c73b59fd22acb222615c2c6dd0d50cca1
ms.sourcegitcommit: 70b1567d316f19c15a4b032b4897f15c8dcdca09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5556233"
---
# <a name="planning-optimization-fit-analysis"></a>Análise de ajuste da Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Você deve analisar o resultado da análise de ajuste da Otimização de Planejamento, como parte do processo de migração. Observe que o escopo da Otimização de Planejamento não é igual à funcionalidade de planejamento mestre incorporado atual. Recomendamos que você trabalhe com seu parceiro e leia a documentação para se preparar para a migração. 

A análise de ajuste da Otimização de Planejamento ajuda a identificar onde o resultado pode diferir entre o mecanismo de planejamento mestre e a Otimização de Planejamento internos. Essa análise é feita com base na configuração e nos dados atuais. 

Para ver o resultado da análise de ajuste de Otimização de Planejamento, vá para o **Planejamento mestre** \> **Configuração** \> **Análise de ajuste da Otimização de Planejamento** e, depois selecione **Executar análise**. Se a análise localizar inconsistências, elas serão listadas na mesma página. (A análise pode demorar alguns minutos).

> [!NOTE]
> Se forem encontradas inconsistências, você ainda poderá usar a Otimização de Planejamento. Os resultados da análise de ajuste simplesmente mostram locais onde os serviços de planejamento não honrarão sua configuração atual. Em outras palavras, eles mostram os locais onde alguns processos podem estar sendo ignorados ou onde não têm suporte.

## <a name="analysis-results-example-1"></a>Resultados da análise: exemplo 1

- **Recurso:** produção
- **Questão:** Itens com um nível de lista de materiais (BOM) maior do que zero: 56
- **Explicação:** a análise de ajuste encontrou 56 itens com uma configuração da BOM de produção. Como a versão atual da Otimização de Planejamento não dá suporte a produção, a Otimização de Planejamento gerará ordens de compra planejadas em vez de ordens de produção planejadas. Também mostrará um aviso que lista os itens afetados.

## <a name="analysis-results-example-2"></a>Resultados da análise: exemplo 2

- **Recurso:** ações
- **Problema:** grupos de cobertura com cálculo de ações habilitado: 6
- **Explicação:** a análise de ajuste encontrou seis grupos de cobertura onde o cálculo de ação está ativado. Como a versão atual da Otimização de Planejamento não dá suporte a ações, nenhuma ação será gerada durante o planejamento mestre.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Visão geral dos resultados possíveis da análise de ajuste

A tabela a seguir mostra os vários resultados que podem ser exibidos após uma análise de ajuste. Os sinais numéricos (_\#_) serão substituídos por um número que indica o número de registros que têm a questão listada. Os recursos com suporte ou em versão preliminar estão disponíveis na versão 10.0.9 ou posterior (a menos que um número de versão superior esteja listado na coluna "Disponibilidade esperada").

| Recurso | Questão listada | Explicação | Disponibilidade esperada |
| --- | --- | --- | --- |
| Ações | Grupos de cobertura com Cálculo de ações habilitado: _\#_ | Este recurso está pendente. No momento, as ações não são geradas durante o planejamento mestre quando a otimização do planejamento é habilitada, independentemente dessa configuração. A principal finalidade das ações é sugerir alterações nas ordens existentes. Avalie se as ações são aplicadas ativamente como parte de seus processos de negócios ou se as informações de atraso relacionadas às ordens são suficientes. | Outubro de 2021 - Abril de 2022 |
| Calendários base | Calendários usando o calendário base: _\#_ | Este recurso está pendente. No momento, o calendário base é ignorado quando a otimização de planejamento é habilitada. Avalie se o calendário base é necessário para seus processos de negócios ou se a configuração direta em calendários é suficiente. | 2021 de abril | 
| Códigos de disposição em lotes | Mestres de disposição em lotes não-líquidos: _\#_ | Este recurso está pendente. No momento, os códigos de disposição em lotes são ignorados quando a otimização do planejamento é habilitada. | Outubro de 2021 - Abril de 2022 |
| Capacidade de comprometimento (CTP) | Configurações de ordem padrão com controle de data entrega definido como CTP: _\#_ | Este recurso está pendente. No momento, o CTP é ignorado quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Outubro de 2021 - Abril de 2022 |
| Copiar plano estático para dinâmico | A cópia de plano estático para dinâmico está habilitada nos parâmetros do plano mestre. | A otimização do planejamento não copia o plano estático para o plano dinâmico, independentemente dessa configuração. Em geral, esse conceito é menos relevante devido à velocidade e à regeneração completa que a otimização do planejamento oferece. Se dois ou mais planos forem usados, o planejamento mestre deverá ser disparado para cada plano. | Outubro de 2021 - Abril de 2022 |
| Confirmação | Grupos de cobertura com limite de tempo de confirmação automática definido: _\#_ | Na versão 10.0.7 e mais recente, a confirmação é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso _Confirmação automática para a otimização de planejamento_ seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| Confirmação | Registros de cobertura de item com confirmação automática definida: _\#_ | Na versão 10.0.7 e mais recente, a confirmação automática é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso _Confirmação automática para a otimização de planejamento_ seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| Confirmação | Planos mestres com confirmação automática definida: _\#_ | Na versão 10.0.7 e mais recente, a confirmação automática é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso _Confirmação automática para a otimização de planejamento_ seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| FitAnalysisPlanningItems | Itens de planejamento: _\#_ | Este recurso está pendente. No momento, o planejamento de itens é tratado como itens comuns quando a otimização do planejamento é habilitada. | Outubro de 2021 - Abril de 2022 |
| Previsão | Grupos de cobertura com "Incluir ordens intercompanhia" habilitado: _\#_ | Este recurso está pendente. No momento, o planejamento mestre não inclui demanda planejada de downstream quando a otimização do planejamento é habilitada, independentemente dessa configuração. Observe que as ordens lançadas/confirmadas ainda funcionam com a funcionalidade intercompanhia regular e cobrir a maioria dos cenários. | Suportado |
| Previsão | Os grupos de cobertura com a configuração "Reduzir previsão por" são definidos como um valor diferente de "Pedidos": _\#_ | Por padrão, a otimização do planejamento usa "Reduzir previsão por" para pedidos, independentemente dessa configuração. | Suportado |
| Previsão | Modelos de previsão com submodelos: _\#_ | Este recurso está pendente. No momento, as previsões que usam submodelos não têm suporte quando a otimização de planejamento está habilitada. Eles serão ignorados, independentemente dessa configuração. | 2021 de abril |
| Previsão | Planejamentos mestres com "Incluir previsão de fornecimento" habilitado: _\#_ | Este recurso está pendente. No momento, as previsões de fornecimento não têm suporte quando a otimização de planejamento está habilitada. Eles serão ignorados, independentemente dessa configuração. | Outubro de 2021 - Abril de 2022 |
| Congelar limite de tempo | Grupos de cobertura com limite de tempo de congelamento definido: _\#_ | O limite de tempo de congelamento não é geralmente usado e, no momento, não há planos para incluí-lo na otimização do planejamento. No momento, a configuração de limite de tempo de congelamento é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | N/D |
| Congelar limite de tempo | Registros de cobertura de item com limite de tempo de congelamento definido: _\#_ | O limite de tempo de congelamento não é geralmente usado e, no momento, não há planos para incluí-lo na otimização do planejamento. No momento, a configuração de limite de tempo de congelamento é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | N/D |
| Congelar limite de tempo | Planos mestres com limite de tempo de congelamento definido: _\#_ | O limite de tempo de congelamento não é geralmente usado e, no momento, não há planos para incluí-lo na otimização do planejamento. No momento, a configuração de limite de tempo de congelamento é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | N/D |
| Intercompanhia | Planos mestres incluindo a demanda downstream planejada: _\#_ | Este recurso está pendente. No momento, o planejamento mestre não inclui demanda planejada de downstream quando a otimização do planejamento é habilitada, independentemente dessa configuração. Observe que as ordens lançadas/confirmadas ainda funcionam com a funcionalidade intercompanhia normal e cobrir a maioria dos cenários. | Suportado |
| Kanban | Registros de cobertura de item com kanban do tipo de ordem planejada: _\#_ | Este recurso está pendente. No momento, a cobertura do item definida como kanban será ignorada quando a otimização do planejamento estiver habilitada. O tipo de ordem planejado para kanban criará um aviso durante o planejamento mestre e as ordens de compra planejadas serão criadas para cobrir a demanda relacionada. | Outubro de 2021 - Abril de 2022 |
| Kanban | Itens com o kanban do tipo de ordem padrão: _\#_ | No momento, um tipo de pedido padrão definido como kanban será ignorado quando a otimização do planejamento estiver habilitada. O tipo de ordem padrão para kanban criará um aviso durante o planejamento mestre e as ordens de compra planejadas serão criadas para cobrir a demanda relacionada. | Outubro de 2021 - Abril de 2022 |
| Estado do ciclo de vida do produto   | Estados do ciclo de vida do produto não ativos para planejamento: _\#_ | Este recurso está pendente. No momento o estado do ciclo de vida do produto é ignorado com a otimização de planejamento habilitada. Você pode ajustar o filtro de produto de nível de plano para evitar incluir produtos nos quais o estado do ciclo de vida do produto está desabilitado para planejamento. | Suportado |
| Produção | Linhas de BOM com arredondamento ou configuração múltipla: _\#_ | Este recurso está pendente. No momento, o arredondamento e várias configurações são ignorados nas linhas da BOM quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2021 de abril |
| Produção | Linhas de fórmula/BOM com medida de fórmula: _\#_ | Este recurso está pendente. No momento, a medida da fórmula é ignorada na BOM e linhas de fórmula quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2021 de outubro |
| Produção | Linhas de fórmula/BOM com substituição de itens (grupos de planos): _\#_ | Este recurso está pendente. No momento, substituição de item (grupos de planejamento) é ignorada na BOM e linhas de fórmula quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2021 de outubro |
| Produção | Linhas de fórmula/BOM com quantidade negativa: _\#_ | Este recurso está pendente. As linhas de BOM e fórmulas que têm quantidade negativa serão incluídas em uma quantidade de 0 (zero) e um aviso será emitido quando a otimização do planejamento for habilitada. Atualize os dados mestres para evitar avisos. | 2021 de outubro |
| Produção | Linhas de fórmula/BOM com consumo de recursos: _\#_ | Este recurso está pendente. No momento, as linhas da BOM e da fórmula que têm consumo de recursos são ignoradas quando a otimização do planejamento for habilitada. Quando esse recurso é compatível, o requisito de material será definido para a data de início da produção. Até que esse recurso seja compatível, os requisitos não serão gerados para materiais marcados com um sinalizador de consumo de recursos. | 2021 de abril |
| Produção | Linhas de fórmula/BOM com consumo em etapas: _\#_ | Este recurso está pendente. No momento, consumo de etapa é ignorado na BOM e linhas de fórmula quando a otimização do planejamento for habilitada. | 2021 de outubro |
| Produção | BOMs com sucata constante ou sucata variável definida: _\#_ | Este recurso está pendente. No momento, a sucata constante e a sucata variável definidas nas BOMs são ignoradas quando a otimização do planejamento for habilitada. | Outubro de 2021 - Abril de 2022 |
| Produção | BOMs com subcontratação: _\#_ | Este recurso está pendente. No momento, a configuração de subcontratação nas BOMs é ignorada quando a otimização do planejamento for habilitada, independentemente dessa configuração. | Outubro de 2021 - Abril de 2022 |
| Produção | BOMs sem um site: _\#_ | Este recurso está pendente. No momento, as BOMs sem um local são ignoradas quando a otimização do planejamento é habilitada. | Suportado |
| Produção | Demanda com requisitos específicos de BOM ou roteiro definidos: _\#_ | Este recurso está pendente. No momento, os requisitos específicos da BOM ou do roteiro definidos na demanda (como uma sub-BOM ou um sub-roteiro em uma ordem de venda) são ignorados quando a otimização do planejamento é habilitada. A BOM ou o roteiro padrão será usado, independentemente dessa configuração. | Outubro de 2021 - Abril de 2022 |
| Produção | Versões de fórmula com Coprodutos/Subprodutos: _\#_ | Este recurso está pendente. No momento, os coprodutos e subprodutos associados à versão da fórmula são ignorados quando a otimização do planejamento é habilitada. | 2021 de outubro |
| Produção | Versões de fórmula com Produção: _\#_ | Este recurso está pendente. No momento, o rendimento associado à versão da fórmula é ignorado quando a otimização do planejamento é habilitada. | Outubro de 2021 - Abril de 2022 |
| Produção | Planos que incluem sequenciamento: _\#_ | Este recurso está pendente. No momento, o sequenciamento é ignorado quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Outubro de 2021 - Abril de 2022 |
| Produção | Ordens de produção liberadas que não foram iniciadas, nas quais o início agendado é anterior a hoje: _\#_ | Este recurso está pendente. Atualmente, se uma ordem de produção estiver atrasada, o planejamento mestre presumirá que ela será concluída hoje. Isso é relevante para ordens de produção lançadas em que uma data de entrega está no passado, mas ainda não foi concluída. | Outubro de 2021 - Abril de 2022 |
| Produção | Recursos agendados com capacidade finita: _\#_ | Este recurso está pendente. No momento, os recursos agendados com capacidade finita são ignorados quando a otimização do planejamento for habilitada. O plano é feito com base no prazo de entrega padrão do produto. | Infinito: abril de 2021, Finito: outubro de 2021 |
| Produção | Roteiros usados no planejamento: _\#_ | Este recurso está pendente. No momento, roteiros são ignorados quando a otimização do planejamento é habilitada. O o prazo de entrega padrão do produto é usado. | 2021 de abril |
| Produção | Reserva de linha de vendas usando detalhamento: _\#_ | A reserva de linha de venda que usa detalhamento não tem suporte quando a otimização de planejamento está habilitada. | 2021 de outubro |
| Produção | Agendamento com detalhamento das ordens de produção: _\#_ | Agendamento que usa explosão de ordens de produção não tem suporte quando a otimização de planejamento está habilitada. As ordens de produção podem ser planejadas individualmente. | 2021 de outubro |
| Solicitação de cotação | Planos mestres com solicitações de cotação habilitadas: _\#_ | Este recurso está pendente. No momento, as solicitações de cotação (RFQs) não são consideradas como demandas quando a otimização do planejamento for habilitada. Eles serão ignorados, independentemente dessa configuração. | Outubro de 2021 - Abril de 2022 |
| Requisições | Planos mestres com requisições habilitadas: _\#_ | Este recurso está pendente. No momento, requisições de compra não são consideradas quando a Otimização de Planejamento está habilitada. Eles serão ignorados, independentemente dessa configuração. | Suportado |
| Margens de segurança | Grupos de cobertura com margem de segurança: _\#_ | Este recurso está pendente. No momento, a margem de segurança é ignorada quando a otimização de planejamento for habilitada. Para compensar esse comportamento, você pode aumentar o prazo de entrega para que ele inclua a margem de segurança. | Margem de recebimento: com suporte. Margem de segurança e margem de saída: abril de 2021 |
| Margens de segurança | Planos mestres com margem de segurança: _\#_ | Este recurso está pendente. No momento, a margem de segurança é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. Para compensar esse comportamento, você pode aumentar o prazo de entrega para que ele inclua a margem de segurança. | Margem de recebimento: com suporte. Margem de segurança e margem de saída: abril de 2021 |
| Atendimento de estoque de segurança | Registros de cobertura de item com "Preencher mínimo" diferente de "Data de hoje + tempo de aquisição": _\#_ | A otimização de planejamento sempre usa a *Data de hoje + tempo de aquisição*. Essa alteração é feita para preparar-se para uma configuração de planejamento simplificada no futuro e para fornecer um resultado acionável. Se o tempo de compras não for incluído no estoque de segurança, as ordens planejadas criadas para o estoque baixo atual sempre estarão atrasadas por conta do prazo de entrega. Esse comportamento pode causar um ruído significativo e ordens planejadas indesejadas. A prática recomendada é alterar a configuração de forma que a *Data de hoje + tempo de aquisição* seja usada. Atualize os dados mestres para evitar avisos. | N/D |
| Cotações de venda | Planos mestres com cotações de venda habilitadas: _\#_ | Este recurso está pendente. No momento, cotações não são consideradas quando a otimização do planejamento for habilitada. Eles serão ignorados, independentemente dessa configuração. | Outubro de 2021 - Abril de 2022 |
| Validade | Planos mestres com validade habilitada: _\#_ | Este recurso está pendente. No momento, a validade não é configurada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2021 de outubro |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Otimização de Planejamento](planning-optimization-overview.md)

[Introdução à Otimização de Planejamento](get-started.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

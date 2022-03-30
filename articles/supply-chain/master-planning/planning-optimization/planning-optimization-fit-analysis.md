---
title: Análise de ajuste da Otimização de Planejamento
description: Este tópico explica como verificar sua configuração e seus dados atuais em relação aos recursos da funcionalidade Otimização de Planejamento.
author: ChristianRytt
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 440cddca11df8d705757c6f6adf01e08626c5158
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408006"
---
# <a name="planning-optimization-fit-analysis"></a>Análise de ajuste da Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Você deve analisar o resultado da análise de ajuste da Otimização de Planejamento, como parte do processo de migração. Observe que o escopo da Otimização de Planejamento não é igual à funcionalidade de planejamento mestre incorporado atual. Recomendamos que você trabalhe com seu parceiro e leia a documentação para se preparar para a migração. 

A análise de ajuste da Otimização de Planejamento ajuda a identificar onde o resultado pode diferir entre o mecanismo de planejamento mestre e a Otimização de Planejamento internos. Essa análise é feita com base na configuração e nos dados atuais. 

Para ver o resultado da análise de ajuste de Otimização de Planejamento, Acesse o **Planejamento mestre** \> **Configuração** \> **Análise de ajuste da Otimização de Planejamento** e, depois selecione **Executar análise**. Se a análise localizar inconsistências, elas serão listadas na mesma página. (A análise pode demorar alguns minutos).

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

> [!NOTE]
> Algumas inconsistências não podem ser identificadas pela análise de ajuste de Otimização de Planejamento. Para obter mais informações, consulte [Diferenças entre o planejamento mestre clássico e a Otimização de Planejamento](planning-optimization-differences-with-built-in.md).

| Recurso | Questão listada | Explicação | Disponibilidade esperada |
| --- | --- | --- | --- |
| Ações | Grupos de cobertura com Cálculo de ações habilitado: _\#_ | Este recurso está pendente. No momento, as ações não são geradas durante o planejamento mestre quando a otimização do planejamento é habilitada, independentemente dessa configuração. A principal finalidade das ações é sugerir alterações nas ordens existentes. Avalie se as ações são aplicadas ativamente como parte de seus processos de negócios ou se as informações de atraso relacionadas às ordens são suficientes. | 2022 de abril |
| Calendários base | Calendários usando o calendário base: _\#_ | Este recurso agora é suportado. | 2022 de março | 
| Códigos de disposição em lotes | Mestres de disposição em lotes não-líquidos: _\#_ | Este recurso está pendente. No momento, os códigos de disposição em lotes são ignorados quando a otimização do planejamento é habilitada. | Outubro de 2022 ou posterior |
| Capacidade de comprometimento (CTP) | Configurações de ordem padrão com controle de data entrega definido como CTP: _\#_ | Este recurso está pendente. No momento, o CTP é ignorado quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2022 de outubro |
| Copiar plano estático para dinâmico | A cópia de plano estático para dinâmico está habilitada nos parâmetros do plano mestre. | A otimização do planejamento não copia o plano estático para o plano dinâmico, independentemente dessa configuração. Em geral, esse conceito é menos relevante devido à velocidade e à regeneração completa que a otimização do planejamento oferece. Se dois ou mais planos forem usados, o planejamento mestre deverá ser disparado para cada plano. | 2022 de outubro |
| Confirmação | Grupos de cobertura com limite de tempo de confirmação automática definido: _\#_ | Na versão 10.0.7 e mais recente, a confirmação é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso _Confirmação automática para a otimização de planejamento_ seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| Confirmação | Registros de cobertura de item com confirmação automática definida: _\#_ | Na versão 10.0.7 e mais recente, a confirmação automática é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso _Confirmação automática para a otimização de planejamento_ seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| Confirmação | Planos mestres com confirmação automática definida: _\#_ | Na versão 10.0.7 e mais recente, a confirmação automática é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso _Confirmação automática para a otimização de planejamento_ seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| FitAnalysisPlanningItems | Itens de planejamento: _\#_ | Este recurso está pendente. No momento, o planejamento de itens é tratado como itens comuns quando a otimização do planejamento é habilitada. | Outubro de 2022 ou posterior |
| Previsão | Grupos de cobertura com "Incluir ordens intercompanhia" habilitado: _\#_ | Este recurso agora é suportado. Para obter informações adicionais, consulte [Planejamento intercompanhia](Intercompany-planning.md) | Suportado |
| Previsão | Os grupos de cobertura com a configuração "Reduzir previsão por" são definidos como um valor diferente de "Pedidos": _\#_ | Este recurso agora é suportado. Para obter mais informações, consulte [Planejamento mestre com previsões de demanda​](demand-forecast.md) | Suportado |
| Previsão | Modelos de previsão com submodelos: _\#_ |  Este recurso agora é suportado. Para obter mais informações, consulte [Planejamento mestre com previsões de demanda​](demand-forecast.md) | Suportado |
| Previsão | Planejamentos mestres com "Incluir previsão de fornecimento" habilitado: _\#_ | Este recurso está pendente. No momento, as previsões de fornecimento não têm suporte quando a otimização de planejamento está habilitada. Eles serão ignorados, independentemente dessa configuração. | Outubro de 2022 ou posterior |
| Congelar limite de tempo | Grupos de cobertura com o recurso Congelar limite de tempo definido: _\#_ | O recurso Congelar limite de tempo não é geralmente usado e, no momento, não há planos para incluí-lo na otimização do planejamento. No momento, a configuração do recurso Congelar limite de tempo é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | N/D |
| Congelar limite de tempo | Registros de cobertura de item com o recurso Congelar limite de tempo definido: _\#_ | O recurso Congelar limite de tempo não é geralmente usado e, no momento, não há planos para incluí-lo na otimização do planejamento. No momento, a configuração do recurso Congelar limite de tempo é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | N/D |
| Congelar limite de tempo | Planos mestres com o recurso Congelar limite de tempo definido: _\#_ | O recurso Congelar limite de tempo não é geralmente usado e, no momento, não há planos para incluí-lo na otimização do planejamento. No momento, a configuração do recurso Congelar limite de tempo é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | N/D |
| Intercompanhia | Planos mestres incluindo a demanda downstream planejada: _\#_ | Este recurso agora é suportado. Para obter informações adicionais, consulte [Planejamento intercompanhia](Intercompany-planning.md) | Suportado |
| Kanban | Registros de cobertura de item com kanban do tipo de ordem planejada: _\#_ | Este recurso está pendente. No momento, a cobertura do item definida como kanban será ignorada quando a otimização do planejamento estiver habilitada. O tipo de ordem planejado para kanban criará um aviso durante o planejamento mestre e as ordens de compra planejadas serão criadas para cobrir a demanda relacionada. | Outubro de 2022 ou posterior |
| Kanban | Itens com o kanban do tipo de ordem padrão: _\#_ | No momento, um tipo de pedido padrão definido como kanban será ignorado quando a otimização do planejamento estiver habilitada. O tipo de ordem padrão para kanban criará um aviso durante o planejamento mestre e as ordens de compra planejadas serão criadas para cobrir a demanda relacionada. | Outubro de 2022 ou posterior |
| Estado do ciclo de vida do produto | Estados do ciclo de vida do produto não ativos para planejamento: _\#_ | Este recurso agora é suportado. Para obter informações adicionais, consulte [Excluir produtos que têm estados específicos do ciclo de vida do produto](product-lifecycle-state.md) | Suportado |
| Produção | Linhas de BOM com arredondamento ou configuração múltipla: _\#_ | Este recurso está pendente. No momento, o arredondamento e várias configurações são ignorados nas linhas da BOM quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2021 de outubro |
| Produção | Linhas de fórmula/BOM com medida de fórmula: _\#_ | Este recurso está pendente. No momento, a medida da fórmula é ignorada na BOM e linhas de fórmula quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2022 de outubro |
| Produção | Linhas de fórmula/BOM com substituição de itens (grupos de planos): _\#_ | Este recurso está pendente. No momento, substituição de item (grupos de planejamento) é ignorada na BOM e linhas de fórmula quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2022 de outubro |
| Produção | Linhas de fórmula/BOM com quantidade negativa: _\#_ | Este recurso está pendente. As linhas de BOM e fórmulas que têm quantidade negativa serão incluídas em uma quantidade de 0 (zero) e um aviso será emitido quando a otimização do planejamento for habilitada. Atualize os dados mestres para evitar avisos. | 2022 de outubro |
| Produção | Linhas de fórmula/BOM com consumo de recursos: _\#_ | Este recurso está pendente. No momento, as linhas da BOM e da fórmula que têm consumo de recursos são ignoradas quando a otimização do planejamento for habilitada. Quando esse recurso é compatível, o requisito de material será definido para a data de início da produção. Até que esse recurso seja compatível, os requisitos não serão gerados para materiais marcados com um sinalizador de consumo de recursos. | 2022 de outubro |
| Produção | Linhas de fórmula/BOM com consumo em etapas: _\#_ | Este recurso está pendente. No momento, consumo de etapa é ignorado na BOM e linhas de fórmula quando a otimização do planejamento for habilitada. | 2022 de outubro |
| Produção | BOMs com sucata constante ou sucata variável definida: _\#_ | Este recurso está pendente. No momento, a sucata constante e a sucata variável definidas nas BOMs são ignoradas quando a otimização do planejamento for habilitada. | 2022 de outubro |
| Produção | BOMs com subcontratação: _\#_ | Este recurso está pendente. No momento, a configuração de subcontratação nas BOMs é ignorada quando a otimização do planejamento for habilitada, independentemente dessa configuração. | 2022 de abril |
| Produção | BOMs sem um site: _\#_ | Este recurso agora é suportado. Para obter informações adicionais, consulte [Planejamento de produção](production-planning.md) | Suportado |
| Produção | Demanda com requisitos específicos de BOM ou roteiro definidos: _\#_ | Este recurso está pendente. No momento, os requisitos específicos da BOM ou do roteiro definidos na demanda (como uma sub-BOM ou um sub-roteiro em uma ordem de venda) são ignorados quando a otimização do planejamento é habilitada. A BOM ou o roteiro padrão será usado, independentemente dessa configuração. | 2022 de outubro |
| Produção | Versões de fórmula com Coprodutos/Subprodutos: _\#_ | Este recurso está pendente. No momento, os coprodutos e subprodutos associados à versão da fórmula são ignorados quando a otimização do planejamento é habilitada. | 2022 de outubro |
| Produção | Versões de fórmula com Produção: _\#_ | Este recurso está pendente. No momento, o rendimento associado à versão da fórmula é ignorado quando a otimização do planejamento é habilitada. | 2022 de outubro |
| Produção | Planos que incluem sequenciamento: _\#_ | Este recurso está pendente. No momento, o sequenciamento é ignorado quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2022 de outubro |
| Produção | Ordens de produção liberadas que não foram iniciadas, nas quais o início agendado é anterior a hoje: _\#_ | Este recurso está pendente. Atualmente, se uma ordem de produção estiver atrasada, o planejamento mestre presumirá que ela será concluída hoje. Isso é relevante para ordens de produção lançadas em que uma data de entrega está no passado, mas ainda não foi concluída. | 2022 de outubro |
| Produção | Recursos agendados com capacidade finita: _\#_ | Este recurso está pendente. No momento, os recursos agendados com capacidade finita são ignorados quando a otimização do planejamento for habilitada. O plano é feito com base no prazo de entrega padrão do produto. | 2022 de outubro |
| Produção | Roteiros usados no planejamento: _\#_ | Este recurso está pendente. No momento, roteiros são ignorados quando a otimização do planejamento é habilitada. O o prazo de entrega padrão do produto é usado. | Versão preliminar: com suporte (10.0.20), GA: outubro de 2021 |
| Produção | Reserva de linha de vendas usando detalhamento: _\#_ | A reserva de linha de venda que usa detalhamento não tem suporte quando a otimização de planejamento está habilitada. | 2022 de outubro |
| Produção | Agendamento com detalhamento das ordens de produção: _\#_ | Agendamento que usa explosão de ordens de produção não tem suporte quando a otimização de planejamento está habilitada. As ordens de produção podem ser planejadas individualmente. | 2022 de outubro |
| Solicitação de cotação | Planos mestres com solicitações de cotação habilitadas: _\#_ | Este recurso está pendente. No momento, as solicitações de cotação (RFQs) não são consideradas como demandas quando a otimização do planejamento for habilitada. Eles serão ignorados, independentemente dessa configuração. | 2022 de outubro |
| Requisições | Planos mestres com requisições habilitadas: _\#_ | Este recurso agora é suportado. Para obter mais informações, consulte [Requisições de compra](purchase-requisitions.md) | Suportado |
| Margens de segurança | Grupos de cobertura com margem de segurança: _\#_ | Este recurso agora é suportado parcialmente. Para obter informações adicionais, consulte [Margens de segurança](safety-margins.md) | Margem de recebimento: com suporte. Margem de segurança e margem de saída: janeiro de 2022 |
| Margens de segurança | Planos mestres com margem de segurança: _\#_ | Este recurso agora é suportado parcialmente. Para obter informações adicionais, consulte [Margens de segurança](safety-margins.md) | Margem de recebimento: com suporte. Margem de segurança e margem de saída: janeiro de 2022 |
| Atendimento de estoque de segurança | Registros de cobertura de item com "Preencher mínimo" diferente de "Data de hoje + tempo de aquisição": _\#_ | A otimização de planejamento sempre usa a *Data de hoje + tempo de aquisição*. Essa alteração é feita para preparar-se para uma configuração de planejamento simplificada no futuro e para fornecer um resultado acionável. Se o tempo de compras não for incluído no estoque de segurança, as ordens planejadas criadas para o estoque baixo atual sempre estarão atrasadas por conta do prazo de entrega. Esse comportamento pode causar um ruído significativo e ordens planejadas indesejadas. A prática recomendada é alterar a configuração de forma que a *Data de hoje + tempo de aquisição* seja usada. Atualize os dados mestres para evitar avisos. | N/D |
| Cotações de venda | Planos mestres com cotações de venda habilitadas: _\#_ | Este recurso está pendente. No momento, cotações não são consideradas quando a otimização do planejamento for habilitada. Eles serão ignorados, independentemente dessa configuração. | Outubro de 2022 ou posterior |
| Validade | Planos mestres com validade habilitada: _\#_ | Este recurso está pendente. No momento, a validade não é configurada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | 2022 de abril |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da Otimização de Planejamento](planning-optimization-overview.md)

[Introdução à Otimização do Planejamento](get-started.md)

[Diferenças entre o planejamento mestre clássico e a Otimização de Planejamento](planning-optimization-differences-with-built-in.md)

[Parâmetros não usados pela Otimização de Planejamento](not-used-parameters.md)

[Exibir histórico e logs de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

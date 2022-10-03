---
title: Análise de ajuste da Otimização do Planejamento
description: Este artigo explica como verificar sua configuração e seus dados atuais em relação aos recursos da funcionalidade Otimização de Planejamento.
author: t-benebo
ms.date: 08/11/2022
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
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 7e32b3ed6ed96de7193cc496e0630969137cd0c1
ms.sourcegitcommit: 15b331f39d6e3ef811b9c2bf055a4f5b4572bae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2022
ms.locfileid: "9591841"
---
# <a name="planning-optimization-fit-analysis"></a>Análise de ajuste da Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Você deve analisar o resultado da análise de ajuste da Otimização de Planejamento, como parte do processo de migração. Observe que o escopo da Otimização de Planejamento não é igual à funcionalidade de planejamento mestre incorporado atual. Recomendamos que você trabalhe com seu parceiro e leia a documentação para se preparar para a migração. 

A análise de ajuste da Otimização de Planejamento ajuda a identificar onde o resultado pode diferir entre o mecanismo de planejamento mestre e a Otimização de Planejamento internos. Essa análise é feita com base na configuração e nos dados atuais. 

Para ver o resultado da análise de ajuste de Otimização de Planejamento, Acesse o **Planejamento mestre** \> **Configuração** \> **Análise de ajuste da Otimização de Planejamento** e, depois selecione **Executar análise**. Se a análise localizar inconsistências, elas serão listadas na mesma página. (A análise pode demorar alguns minutos).

> [!NOTE]
>
> - Algumas inconsistências não podem ser identificadas pela análise de ajuste de Otimização de Planejamento. Para obter mais informações, consulte [Diferenças entre o planejamento mestre clássico e a Otimização de Planejamento](planning-optimization-differences-with-built-in.md).
>
> - Se forem encontradas inconsistências, você ainda poderá usar a Otimização de Planejamento. Os resultados da análise de ajuste simplesmente mostram locais onde os serviços de planejamento não honrarão sua configuração atual. Em outras palavras, eles mostram os locais onde alguns processos podem estar sendo ignorados ou onde não têm suporte.

## <a name="analysis-results-example-1"></a>Resultados da análise: exemplo 1

- **Recurso:** produção
- **Questão:** Itens com um nível de lista de materiais (BOM) maior do que zero: 56
- **Explicação:** a análise de ajuste encontrou 56 itens com uma configuração da BOM de produção. Como a versão atual da Otimização de Planejamento não dá suporte a produção, a Otimização de Planejamento gerará ordens de compra planejadas em vez de ordens de produção planejadas. Também mostrará um aviso que lista os itens afetados.

## <a name="analysis-results-example-2"></a>Resultados da análise: exemplo 2

- **Recurso:** ações
- **Problema:** grupos de cobertura com cálculo de ações habilitado: 6
- **Explicação:** a análise de ajuste encontrou seis grupos de cobertura onde o cálculo de ação está ativado. Como a versão atual da Otimização de Planejamento não dá suporte a ações, nenhuma ação será gerada durante o planejamento mestre.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Visão geral dos resultados possíveis da análise de ajuste

A tabela a seguir mostra os vários resultados que podem ser exibidos após uma análise de ajuste. Os sinais numéricos (*\#*) serão substituídos por um número que indica o número de registros que têm a questão listada.

> [!IMPORTANT]
> Para recursos que ainda não têm suporte, a tabela a seguir fornece as informações de disponibilidade esperadas que são estimadas com base em nosso roteiro atual. Essas estimativas estão sujeitas a alterações sem aviso prévio.

| Recurso | Questão listada | Explicação | Disponibilidade esperada |
| --- | --- | --- | --- |
| Ações | Grupos de cobertura com Cálculo de ações habilitado: *\#* | Este recurso agora é suportado. | Com suporte |
| Calendários base | Calendários usando o calendário base: *\#* | Este recurso agora é suportado. | Com suporte | 
| Códigos de disposição em lotes | Mestres de disposição em lotes não-líquidos: *\#* | Este recurso está pendente. No momento, os códigos de disposição em lotes são ignorados quando a otimização do planejamento é habilitada. | Ciclo de lançamentos 2 de 2022 <!-- KFM: Now available? [Use batch disposition codes to mark batches as available or unavailable](../../inventory/batch-disposition-codes.md) --> |
| Capacidade de comprometimento (CTP) | Configurações de ordem padrão com controle de data entrega definido como CTP: *\#* | No Supply Chain Management 10.0.28 e mais recente, um processo chamado *CTP para Otimização de Planejamento* torna as datas de remessa e de recebimento confirmadas disponíveis após a execução do plano dinâmico. Para versões anteriores do Supply Chain Management, a configuração do CTP herdado é ignorada quando a Otimização do Planejamento é habilitada. | Com suporte |
| Copiar plano estático para dinâmico | A cópia de plano estático para dinâmico está habilitada nos parâmetros do plano mestre. | A otimização do planejamento não copia o plano estático para o plano dinâmico, independentemente dessa configuração. Em geral, esse conceito é menos relevante devido à velocidade e à regeneração completa que a otimização do planejamento oferece. Se dois ou mais planos forem usados, o planejamento mestre deverá ser disparado para cada plano. | N/D |
| Confirmação | Grupos de cobertura com limite de tempo de confirmação automática definido: *\#* | Na versão 10.0.7 e mais recente, a confirmação é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso *Confirmação automática para a otimização de planejamento* seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Com suporte |
| Confirmação | Registros de cobertura de item com confirmação automática definida: *\#* | Na versão 10.0.7 e mais recente, a confirmação automática é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso *Confirmação automática para a otimização de planejamento* seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| Confirmação | Planos mestres com confirmação automática definida: *\#* | Na versão 10.0.7 e mais recente, a confirmação automática é suportada como um trabalho em lotes de confirmação separado após a conclusão do planejamento mestre (desde que o recurso *Confirmação automática para a otimização de planejamento* seja habilitado no [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observe que a confirmação automática para otimização de planejamento é baseada na data da ordem (data de início), e não na data do requisito (data final). Esse comportamento garante que a confirmação das ordens planejadas ocorra no tempo devido, sem que seja necessário incluir o prazo de entrega no limite de tempo de confirmação. | Suportado |
| FitAnalysisPlanningItems | Itens de planejamento: *\#* | Este recurso está pendente. No momento, o planejamento de itens é tratado como itens comuns quando a otimização do planejamento é habilitada. | Ciclo de lançamentos 2 de 2022 ou posterior |
| Previsão | Grupos de cobertura com "Incluir ordens intercompanhia" habilitado: *\#* | Este recurso agora é suportado. Para obter informações adicionais, consulte [Planejamento intercompanhia](Intercompany-planning.md) | Suportado |
| Previsão | Os grupos de cobertura com a configuração "Reduzir previsão por" são definidos como um valor diferente de "Pedidos": *\#* | Este recurso agora é suportado. Para obter mais informações, consulte [Planejamento mestre com previsões de demanda​](demand-forecast.md) | Suportado |
| Previsão | Modelos de previsão com submodelos: *\#* |  Este recurso agora é suportado. Para obter mais informações, consulte [Planejamento mestre com previsões de demanda​](demand-forecast.md) | Suportado |
| Previsão | Planejamentos mestres com "Incluir previsão de fornecimento" habilitado: *\#* | Este recurso está pendente. No momento, as previsões de fornecimento não têm suporte quando a otimização de planejamento está habilitada. Eles serão ignorados, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 ou posterior |
| Congelar limite de tempo | Grupos de cobertura com o recurso Congelar limite de tempo definido: *\#* | Este recurso está pendente. No momento, a configuração do recurso Congelar limite de tempo é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Congelar limite de tempo | Registros de cobertura de item com o recurso Congelar limite de tempo definido: *\#* | Este recurso está pendente. No momento, a configuração do recurso Congelar limite de tempo é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Congelar limite de tempo | Planos mestres com o recurso Congelar limite de tempo definido: *\#* | Este recurso está pendente. No momento, a configuração do recurso Congelar limite de tempo é ignorada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Intercompanhia | Planos mestres incluindo a demanda downstream planejada: *\#* | Este recurso agora tem suporte. Para obter informações adicionais, consulte [Planejamento intercompanhia](Intercompany-planning.md) | Com suporte |
| Kanban | Registros de cobertura de item com kanban do tipo de ordem planejada: *\#* | Este recurso está pendente. No momento, a cobertura do item definida como kanban será ignorada quando a otimização do planejamento estiver habilitada. O tipo de ordem planejado para kanban criará um aviso durante o planejamento mestre e as ordens de compra planejadas serão criadas para cobrir a demanda relacionada. | Ciclo futuro |
| Kanban | Itens com o kanban do tipo de ordem padrão: *\#* | No momento, um tipo de pedido padrão definido como kanban será ignorado quando a otimização do planejamento estiver habilitada. O tipo de ordem padrão para kanban criará um aviso durante o planejamento mestre e as ordens de compra planejadas serão criadas para cobrir a demanda relacionada. | Ciclo futuro |
| Estado do ciclo de vida do produto | Estados do ciclo de vida do produto não ativos para planejamento: *\#* | Este recurso agora tem suporte. Para obter informações adicionais, consulte [Excluir produtos que têm estados específicos do ciclo de vida do produto](product-lifecycle-state.md) | Suportado |
| Produção | Linhas de BOM com arredondamento ou configuração múltipla: *\#* | Este recurso está pendente. No momento, o arredondamento e várias configurações são ignorados nas linhas da BOM quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Ciclo futuro|
| Produção | Linhas de fórmula/BOM com medida de fórmula: *\#* | Este recurso está pendente. No momento, a medida da fórmula é ignorada na BOM e linhas de fórmula quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Produção | Linhas de fórmula/BOM com substituição de itens (grupos de planos): *\#* | Este recurso está pendente. No momento, substituição de item (grupos de planejamento) é ignorada na BOM e linhas de fórmula quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Produção | Linhas de fórmula/BOM com quantidade negativa: *\#* | Este recurso está pendente. As linhas de BOM e fórmulas que têm quantidade negativa serão incluídas em uma quantidade de 0 (zero) e um aviso será emitido quando a otimização do planejamento for habilitada. Atualize os dados mestres para evitar avisos. | Ciclo de lançamentos 2 de 2022 |
| Produção | Linhas de fórmula/BOM com consumo de recursos: *\#* | Este recurso está pendente. No momento, as linhas da BOM e da fórmula que têm consumo de recursos são ignoradas quando a otimização do planejamento for habilitada. Quando esse recurso é compatível, o requisito de material será definido para a data de início da produção. Até que esse recurso seja compatível, os requisitos não serão gerados para materiais marcados com um sinalizador de consumo de recursos. | Ciclo de lançamentos 2 de 2022 |
| Produção | Linhas de fórmula/BOM com consumo em etapas: *\#* | Este recurso está pendente. No momento, consumo de etapa é ignorado na BOM e linhas de fórmula quando a otimização do planejamento for habilitada. | Ciclo de lançamentos 2 de 2022 |
| Produção | BOMs com sucata constante ou sucata variável definida: *\#* | Este recurso está pendente. No momento, a sucata constante e a sucata variável definidas nas BOMs são ignoradas quando a otimização do planejamento for habilitada. | Ciclo de lançamentos 2 de 2022 |
| Produção | BOMs com subcontratação: *\#* | Este recurso agora tem suporte. | Com suporte |
| Produção | BOMs sem um site: *\#* | Este recurso agora tem suporte. Para obter informações adicionais, consulte [Planejamento de produção](production-planning.md) | Com suporte |
| Produção | Demanda com requisitos específicos de BOM ou roteiro definidos: *\#* | Este recurso está pendente. No momento, os requisitos específicos da BOM ou do roteiro definidos na demanda (como uma sub-BOM ou um sub-roteiro em uma ordem de venda) são ignorados quando a otimização do planejamento é habilitada. A BOM ou o roteiro padrão será usado, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Produção | Versões de fórmula com Coprodutos/Subprodutos: *\#* | Este recurso está pendente. No momento, os coprodutos e subprodutos associados à versão da fórmula são ignorados quando a otimização do planejamento é habilitada. | Ciclo de lançamentos 2 de 2022 |
| Produção | Versões de fórmula com Produção: *\#* | Este recurso está pendente. No momento, o rendimento associado à versão da fórmula é ignorado quando a otimização do planejamento é habilitada. | Ciclo de lançamentos 2 de 2022 |
| Produção | Planos que incluem sequenciamento: *\#* | Este recurso está pendente. No momento, o sequenciamento é ignorado quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Produção | Ordens de produção liberadas que não foram iniciadas, nas quais o início agendado é anterior a hoje: *\#* | Este recurso está pendente. Atualmente, se uma ordem de produção estiver atrasada, o planejamento mestre presumirá que ela será concluída hoje. Isso é relevante para ordens de produção lançadas em que uma data de entrega está no passado, mas ainda não foi concluída. | Ciclo futuro |
| Produção | Recursos agendados com capacidade finita: *\#* | Este recurso agora tem suporte.| Suportado |
| Produção | Roteiros usados no planejamento: *\#* | Este recurso é suportado. | Com suporte |
| Produção | Reserva de linha de vendas usando detalhamento: *\#* | A reserva de linha de venda que usa detalhamento não tem suporte quando a otimização de planejamento está habilitada. | Ciclo futuro |
| Produção | Agendamento com detalhamento das ordens de produção: *\#* | Agendamento que usa explosão de ordens de produção não tem suporte quando a otimização de planejamento está habilitada. As ordens de produção podem ser planejadas individualmente. | Ciclo futuro |
| Solicitação de cotação | Planos mestres com solicitações de cotação habilitadas: *\#* | Este recurso está pendente. No momento, as solicitações de cotação (RFQs) não são consideradas como demandas quando a otimização do planejamento for habilitada. Eles serão ignorados, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 |
| Requisições | Planos mestres com requisições habilitadas: *\#* | Este recurso agora tem suporte. Para obter mais informações, consulte [Requisições de compra](purchase-requisitions.md) | Com suporte |
| Margens de segurança | Grupos de cobertura com margem de segurança: *\#* | Este recurso agora tem suporte. Para obter informações adicionais, consulte [Margens de segurança](safety-margins.md) | Com suporte |
| Margens de segurança | Planos mestres com margem de segurança: *\#* | Este recurso agora tem suporte. Para obter informações adicionais, consulte [Margens de segurança](safety-margins.md) |  Com suporte |
| Atendimento de estoque de segurança | Registros de cobertura de item com "Preencher mínimo" diferente de "Data de hoje + tempo de aquisição": *\#* | A otimização de planejamento sempre usa a *Data de hoje + tempo de aquisição*. Essa alteração é feita para preparar-se para uma configuração de planejamento simplificada no futuro e para fornecer um resultado acionável. Se o tempo de compras não for incluído no estoque de segurança, as ordens planejadas criadas para o estoque baixo atual sempre estarão atrasadas por conta do prazo de entrega. Esse comportamento pode causar um ruído significativo e ordens planejadas indesejadas. A prática recomendada é alterar a configuração de forma que a *Data de hoje + tempo de aquisição* seja usada. Atualize os dados mestres para evitar avisos. | N/D |
| Cotações de venda | Planos mestres com cotações de venda habilitadas: *\#* | Este recurso está pendente. No momento, cotações não são consideradas quando a otimização do planejamento for habilitada. Eles serão ignorados, independentemente dessa configuração. | Ciclo de lançamentos 2 de 2022 ou posterior |
| Validade | Planos mestres com validade habilitada: *\#* | Este recurso está pendente. No momento, a validade não é configurada quando a otimização do planejamento é habilitada, independentemente dessa configuração. | Com suporte |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da Otimização do Planejamento](planning-optimization-overview.md)

[Introdução à Otimização do Planejamento](get-started.md)

[Diferenças entre o planejamento mestre clássico e a Otimização de Planejamento](planning-optimization-differences-with-built-in.md)

[Parâmetros não usados pela Otimização de Planejamento](not-used-parameters.md)

[Exibir histórico e logs de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

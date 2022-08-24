---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.20 (agosto de 2021)
description: Este artigo descreve os recursos novos ou alterados no Dynamics 365 Supply Chain Management 10.0.20.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d99a7a7d0261ba0afd19efbb237dff329527723d
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219144"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10020-august-2021"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.20 (agosto de 2021)

[!include [banner](../includes/banner.md)]

Este artigo lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.20. Esta versão tem um número de compilação de 10.0.886 e está disponível da seguinte maneira:

- **Versão preliminar:** maio de 2021
- **Disponibilidade geral da versão (autoatualização):** julho de 2021
- **Disponibilidade geral da versão (atualização automática):** agosto de 2021

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. A coluna *Recurso* fornece links para o [plano de lançamento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), no qual é possível ver as datas de lançamento oficiais de cada recurso. A coluna *Mais informações* fornece mais detalhes e/ou links para documentação relacionada.

A maioria desses recursos deve ser habilitada usando [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) antes que você possa usá-los.

| Área de recursos | Recurso | Mais informações |
|---|---|---|
| Estoque&nbsp;e&nbsp;logística | [Aprimoramento de desempenho dos detalhes da ordem de venda](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Este recurso torna a interface do usuário mais ágil ao abrir ordens de vendas, especialmente aquelas que incluem muitas linhas. |
| Fabricação | [Invocar fluxos de automação de processos para criar ordens de qualidade](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [Invocar fluxos de automação de processos para criar ordens de qualidade](../production-control/process-automation-quality-orders.md ) |
| Fabricação | [Interface de execução de piso de produção aprimorada para fabricação](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [Configurar a interface de execução de piso de produção](../production-control/production-floor-execution-configure.md) |
| Planejamento | [Agendamento da capacidade infinita para a Otimização do Planejamento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | [Agendamento com capacidade infinita](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Gerenciamento de informações sobre o produto | [Gerenciar alterações nas fórmulas e seus ingredientes](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [Gerenciar alterações nas fórmulas e seus ingredientes](../engineering-change-management/manage-formula-changes.md) |
| Gerenciamento de informações sobre o produto | [Verificações de preparação do produto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [Preparação do produto](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um deles fornece uma melhoria incremental para um recurso existente. Por serem apenas melhorias, não estão listados no [plano de liberação](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária). Se você quiser usar qualquer um desses recursos, deve ativá-los explicitamente em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome&nbsp;do recurso&nbsp;no gerenciamento&nbsp;de recursos | Mais informações |
|---|---|---|
| Planejamento Mestre | Autorização paralela da previsão de demanda ajustada | Este recurso permite a autorização paralela da previsão de demanda ajustada da página **Previsão de demanda ajustada**. A intenção deste recurso é aumentar o desempenho quando um grande número de previsões está sendo autorizado. Ao autorizar, o usuário pode especificar o **Número de threads** na caixa de diálogo de autorização. |
| Planejamento Mestre | Consolidação executável em lote e consolidação para ordens planejadas em massa e em lote | Este recurso permite usar trabalhos em lotes para consolidar ordens planejadas em massa e em pacote. |
| Controle de produção | Copiar roteiros genéricos | Este recurso aprimora a função de cópia de rota para permitir que os usuários copiem rotas que não são específicas do item. Permite que o sistema atualize todas as informações relevantes (como site, grupo de roteiros, requisitos de recursos e vários horários) após a função de cópia de roteiro ter sido usada para substituir um roteiro que ainda não foi atribuído a um item. |
| Controle de produção | Atualizar requisitos de recursos relacionados quando uma operação de roteiro for alterada | Este recurso permite que o sistema atualize os requisitos de recursos relacionados depois que um usuário altera a operação de uma etapa de roteiro existente. |
| Gerenciamento de informações sobre o produto | Pré-processamento do relatório da lista de materiais para evitar tempo limite | Este recurso faz com que o relatório da lista de materiais seja pré-processado. Isso evitará problemas de tempo limite quando houver uma grande carga de dados para o relatório. |
| Compras | Habilitar redefinição de fluxos de trabalho relacionados a compras | Esta versão prévia do recurso permite redefinir os seguintes fluxos de trabalho para o status de rascunho: Ordem de compra, Alteração de fornecedor e Requisições de compra. |
| Gerenciamento de transporte | Habilitar a criação de um diário de faturas de fornecedor ao descartar uma nota de frete | Quando este recurso está habilitado, um diário de fatura de fornecedor correspondente só será criado por motivos de reconciliação quando você estiver usando a opção de fornecedor de pagamento. Caso contrário, o diário de fatura sempre será criado. |
| Gerenciamento de depósito | Validar modelos selecionados para trabalhos de reabastecimento | Este recurso ajuda a garantir que os usuários selecionem modelos de reabastecimento válidos ao configurar um trabalho de reabastecimento. Ele evita que os usuários criem um trabalho de reabastecimento sem um modelo e selecionem modelos do tipo *Demanda de ciclos*, que não criará nenhum trabalho de reabastecimento e pode levar muito tempo para ser processado. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes artigos de ajuda: Eles não estão necessariamente relacionados aos novos recursos adicionados para esta versão, conforme listado na seção anterior, mas podem ajudar você a obter mais dos recursos existentes.

| Área de recursos | Artigos novos ou atualizados |
|---|---|
| Gerenciamento de alteração de engenharia | [Estados e transações de ciclo de vida do produto](../engineering-change-management/product-lifecycle-state-transactions.md) |
| Gerenciamento de estoque | [Suplemento de Visibilidade de Estoque](../inventory/inventory-visibility.md)<br><br>[Visão geral do gerenciamento de qualidade e não conformidade](../inventory/quality-management-processes.md) (além de todos os artigos de gerenciamento de qualidade relacionados) |
| Compras | [Manter a certificação do fornecedor](../../finance/public-sector/manage-vendor-certification.md) |
| Controle de produção | [Estilizar a interface de execução de piso de produção](../production-control/production-floor-execution-styles.md) |
| Gerenciamento de depósito | [Atribuir títulos e ícones de etapa ao aplicativo móvel Warehouse Management](../warehousing/step-icons-titles.md)<br><br>[Processamento adiado de movimento de estoque manual](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos de finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.20 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações da plataforma para a versão 10.0.20 de aplicativos de finanças e operações (julho de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.20, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8). 

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: plano do ciclo de lançamentos 1 de 2021

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira o [Dynamics 365: plano do ciclo de lançamentos 1 de 2021](/dynamics365-release-plan/2021wave1/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Recursos removidos e preteridos do Supply Chain Management

O artigo [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no artigo [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]


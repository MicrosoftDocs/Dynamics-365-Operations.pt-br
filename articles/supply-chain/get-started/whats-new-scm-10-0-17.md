---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.17 (Abril de 2021)
description: Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Supply Chain Management 10.0.17.
author: kamaybac
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ef6b7c619cfce70c2f0b3f676d3cae988674c858
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474593"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10017-april-2021"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.17 (Abril de 2021)

[!include [banner](../includes/banner.md)]

Este tópico lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.17. Esta versão tem um número de compilação de 10.0.761 e está disponível da seguinte maneira:

- **Versão preliminar:** fevereiro de 2021
- **Disponibilidade geral da versão (autoatualização):** março de 2021
- **Disponibilidade geral da versão (atualização automática):** abril de 2021

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

Os seguintes recursos estão incluídos nesta versão.  Siga os links para o [plano de versão](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features) para ver as datas de lançamento oficiais de cada recurso.

A maioria desses recursos deve ser habilitada usando [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) antes que você possa usá-los.

### <a name="asset-management"></a>Gerenciamento de ativos

- [Aplicar regras para agrupar ordens de serviço ao executar um plano de manutenção](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/apply-rules-grouping-work-orders-while-running-maintenance-plan)<br> - Para obter mais informações, consulte [Criar ordens de serviço](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md).

- [Cobrar clientes por trabalho de manutenção](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/bill-customers-maintenance-work)<br> - Para obter mais informações, consulte [Conta de manutenção em ativos de propriedade do cliente](../asset-management/integration-to-project-management-and-accounting/customer-billing.md).

- [Planejar manutenção com base em valores do contador de ativos acumulados](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/plan-maintenance-based-accumulated-asset-counter-values)<br> - Para obter mais informações, consulte [Planos de manutenção](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md).

### <a name="inventory-and-logistics"></a>Estoque e logística

- [Estrutura de integração do equipamento de manuseio de materiais para processos automatizados de depósito (antigo MHAX)](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/integration-framework-material-handling-equipment-automated-warehouse-processes-previously-mhax)<br> - Para obter mais informações, consulte [Interface de equipamento de manuseio de materiais (MHAX)](../warehousing/mhax.md).

- [Custo de entrega](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/landed-cost)<br> - Para obter mais informações, consulte [Módulo Custo de entrega](../landed-cost/landed-cost-overview.md).

- [Dimensões de embalagem vs. armazenamento](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/packing-vs.-storage-dimensions)<br> - Para obter mais informações, consulte [Definir dimensões diferentes para embalagem e armazenamento](../warehousing/packing-vs-storage-dimensions.md).

- [Alocação de ciclo paralelo](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/parallel-wave-allocation)<br> - Para obter mais informações, consulte [Alocação de ciclo](../warehousing/wave-allocation-method.md).

- [Exibições salvas para estoque e logística](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-inventory-logistics)<br> - Para obter mais informações, consulte [Exibições salvas padrão para o Supply Chain Management](saved-views-scm.md).

- [Agendar a criação de trabalhos de depósito](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-warehouse-work-creation)<br> - Para obter mais informações, consulte [Agendar a criação de trabalhos durante o ciclo](../warehousing/configure-wave-schedule-work-creation.md).

- [Definir dimensões financeiras padrão para comprovantes de reavaliação de custo padrão de estoque](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/set-default-financial-dimensions-inventory-standard-cost-revaluation-vouchers)<br> - Para obter mais informações, consulte [Gerenciar atualizações de custo padrão](../cost-management/manage-standard-cost-updates.md).

- [Remessa de mercadorias pequenas (small parcel shipping, SPS)](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/small-parcel-shipping-sps)<br> - Para obter mais informações, consulte [Remessa de pacotes pequenos](../warehousing/small-parcel-shipping.md).

- [Execução de depósito com unidades de escala na nuvem](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-scale-units-cloud)<br> - Para obter mais informações, consulte [Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](../cloud-edge/cloud-edge-workload-warehousing.md) e [Ordens de depósito para unidades de escala de nuvem e de borda](../cloud-edge/cloud-edge-warehouse-order.md).

- [Aplicativo móvel de gerenciamento de depósito](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application)<br> - Para obter mais informações, consulte [Instalar e conectar o aplicativo Gerenciamento de Depósito](../warehousing/install-configure-warehouse-management-app.md) e [Configurações de usuário do dispositivo móvel](../warehousing/mobile-device-user-settings.md).

- Notificações de execução do ciclo<br> - Para obter mais informações, consulte [Notificações de execução do ciclo](../warehousing/wave-execution-notifications.md)

### <a name="manufacturing"></a>Fabricação

- [Recursos de gerenciamento de ativos na interface de execução de piso de produção](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/asset-management-capabilities-production-floor-execution-interface)<br> - Para obter mais informações, consulte [Configurar a interface de execução de piso de produção](../production-control/production-floor-execution-configure.md).

- [Execução de fabricação com unidades de escala na nuvem](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-scale-units-cloud)<br> - Para obter mais informações, consulte [Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e de borda](../cloud-edge/cloud-edge-workload-manufacturing.md).

- [Substituir o princípio padrão de reserva de materiais em produção](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/override-default-reservation-principle-materials-production)<br> - Para obter mais informações, consulte [Substituir o princípio de reserva padrão para materiais em produção](../production-control/override-default-reservation-principle.md).

- [Exibições salvas para controle de produção](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-production-control)<br> - Para obter mais informações, consulte [Exibições salvas padrão para o Supply Chain Management](saved-views-scm.md).

- Sequência numérica unificada para IDs de trabalho<br> - Para obter mais informações, consulte [Sequência numérica unificada para IDs de trabalho](../production-control/unified-job-ids.md).

### <a name="planning"></a>Planejamento

- [Suporte ao Limite de tempo de cobertura para a Otimização de Planejamento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/coverage-time-fence-support-planning-optimization)<br> - Para obter mais informações, consulte [Limites de tempo de cobertura](../master-planning/planning-optimization/coverage-time-fence.md).

- [Prever o suporte a submodelos para a Otimização de Planejamento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/forecast-submodel-support-planning-optimization)<br> - Para obter mais informações, consulte [Planejamento mestre com previsões de demanda​](../master-planning/planning-optimization/demand-forecast.md).

- [Suporte à requisição de compra para a Otimização de Planejamento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/purchase-requisition-support-planning-optimization)<br> - Para obter mais informações, consulte [Requisições de compra](../master-planning/planning-optimization/purchase-requisitions.md).

- [Exibições salvas de ordens planejadas](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-planned-orders)<br> - Para obter mais informações, consulte [Exibições salvas padrão para o Supply Chain Management](saved-views-scm.md).

### <a name="product-information-management"></a>Gerenciamento de informações do produto

- [Habilitar gerenciamento de modificações em produtos existentes](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enable-change-management-existing-products)<br> - Para obter mais informações, consulte [Habilitar o gerenciamento de alterações em produtos existentes](../engineering-change-management/change-management-existing-products.md).

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes tópicos de ajuda. Eles não estão necessariamente relacionados aos novos recursos adicionados para esta versão, conforme listado na seção anterior, mas podem ajudar você a obter mais dos recursos existentes.

### <a name="asset-management"></a>Gerenciamento de ativos

- [Configurar o espaço de trabalho móvel de gerenciamento de ativos](../asset-management/set-up-asset-management-mobile.md)

### <a name="inventory-and-logistics"></a>Estoque e logística

- [Configurar filtros de produto para transações de depósito](../warehousing/filters-and-filter-codes.md)

- [Contagem cíclica parcial do local](../warehousing/partial-location-cycle-counting.md)

- [Agrupamento de linhas de separação](../warehousing/pick-line-grouping.md)

- [Slots de depósito](../warehousing/warehouse-slotting.md)

### <a name="manufacturing"></a>Fabricação

- [Criar a interface de execução de piso de produção](../production-control/production-floor-execution-tabs.md)

### <a name="planning"></a>Planejamento

- [Planejamento intercompanhia](../master-planning/planning-optimization/Intercompany-planning.md)

- [Marca de estoque com Otimização do Planejamento](../master-planning/planning-optimization/marking.md)

- [Planejamento de produção](../master-planning/planning-optimization/production-planning.md)

- [Requisições de compra no planejamento mestre](../master-planning/planning-optimization/purchase-requisitions.md)

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para os aplicativos do Finance and Operations

O Microsoft Dynamics 365 Supply Chain Management 10.0.17 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.17 dos aplicativos do Finance and Operations (abril de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.17, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=551039&dbType=3&qc=91219e7c3fc585acb17b810c915c3cbea499403538520c40e54de43a53aea6a8).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: plano do ciclo de lançamentos 1 de 2021

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira o [Dynamics 365: plano do ciclo de lançamentos 1 de 2021](/dynamics365-release-plan/2021wave1/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Recursos removidos e preteridos do Supply Chain Management

O tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

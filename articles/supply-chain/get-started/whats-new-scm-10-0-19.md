---
title: Versão preliminar do Dynamics 365 Supply Chain Management 10.0.19 (julho de 2021)
description: Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8bb4a7c8085b40ab3eca72675dbe7a3be412d8c1
ms.sourcegitcommit: 2eb7a9ae544f504155657c5c584cbac66c21dba4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2021
ms.locfileid: "5961672"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10019-july-2021"></a>Versão preliminar do Dynamics 365 Supply Chain Management 10.0.19 (julho de 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico lista os recursos novos ou alterados na versão preliminar da versão 10.0.19 do Microsoft Dynamics 365 Supply Chain Management. Esta versão tem um número de compilação de 10.0.837 e está disponível da seguinte maneira:

- **Versão preliminar:** abril de 2021
- **Disponibilidade geral da versão (autoatualização):** junho de 2021
- **Disponibilidade geral da versão (atualização automática):** julho de 2021

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. A coluna *Recurso* fornece links para o [plano de lançamento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), no qual é possível ver as datas de lançamento oficiais de cada recurso. A coluna *Mais informações* fornece links para a documentação relacionada.

A maioria desses recursos deve ser habilitada usando [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) antes que você possa usá-los. Alguns dos recursos listados ainda estão na versão preliminar, enquanto outros já estão disponíveis.

| Área de recursos | Recurso | Mais informações |
|---|---|---|
| Estoque e logística | [Otimização de exportação de entidade de dados da pessoa de contato](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | *Não disponível* |
| Estoque e logística | [Aprimoramentos incrementais para recursos de execução de depósito com unidades de escala](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Mensagens do processador de mensagens](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Ajuste de estoque do depósito](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e borda](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Estoque e logística | [Funcionalidade de pesquisa para os campos Introdução do documento e Conclusão do documento na página Cotação de venda](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | *Não disponível* |
| Estoque e logística | [Execução de depósito com unidades de escala de borda em hardware personalizado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Implantar unidades de escala de borda em hardware personalizado usando LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Fabricação | [Execução de fabricação com unidades de escala de borda em hardware personalizado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Implantar unidades de escala de borda em hardware personalizado usando LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planejamento | Confirmação de ordens planejadas baseadas em consulta | [Confirmar ordens planejadas](../master-planning/planning-optimization/planned-order-firming.md) |
| Gerenciamento de informações do produto | [Aprimoramentos na página de sugestões de grade](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Criar grades de produtos predefinidas](../pim/tasks/create-predefined-product-variants.md) |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes tópicos de ajuda. Eles não estão necessariamente relacionados aos novos recursos adicionados para esta versão, conforme listado na seção anterior, mas podem ajudar você a obter mais dos recursos existentes.

| Área de recursos | Tópicos novos ou atualizados |
|---|---|
| Gerenciamento de alteração de engenharia | [Perguntas frequentes sobre o gerenciamento de alterações de engenharia](../engineering-change-management/change-management-faq.md) |
| Compras | [Solicitações de categoria de fornecedores](../procurement/category-requests-from-vendors.md) |
| Gerenciamento de informações do produto | [Gerenciar unidade de medida](../pim/tasks/manage-unit-measure.md)<br><br>[Cálculos para modelo de configuração de produtos](../pim/config-model-calculations.md) |
| Controle de produção | [Sequência numérica unificada para IDs de trabalho](../production-control/unified-job-ids.md) |
| Gerenciamento de transporte | [Classes LTL](../transportation/ltl-class.md)<br><br>[Códigos NMFC](../transportation/nmfc-codes.md) |
| Gerenciamento de depósito | [Solucionar problemas de hierarquias de reserva serial e lote de depósito](../warehousing/troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md) |
| Gerenciamento de depósito, criação e processamento de ciclos | [Criação e processamento de ciclos](../warehousing/wave-processing.md)<br><br>[Parâmetros de depósito para o processamento de ciclo](../warehousing/wave-warehouse-parameters.md)<br><br>[Modelos de ciclo](../warehousing/wave-templates.md)<br><br>[Alocação de ciclo](../warehousing/wave-allocation-method.md)<br><br>[Agendar criação de trabalho durante o ciclo](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Transporte em contêineres](../warehousing/wave-containerization.md)<br><br>[Notificações de execução do ciclo](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para os aplicativos do Finance and Operations

O Microsoft Dynamics 365 Supply Chain Management 10.0.19 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.19 dos aplicativos do Finance and Operations (Julho de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.19, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

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

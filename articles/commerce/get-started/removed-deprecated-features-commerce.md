---
title: Recursos removidos ou obsoletos do Dynamics 365 Commerce
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 64241ef1c25359c7b3b305c4e8f2b24de7e8f5e4
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443909"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Recursos removidos ou obsoletos do Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Recursos removidos ou substituídos na versão 10.0.11 do Commerce
### <a name="data-action-hooks"></a>Ganchos de ação de dados
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O recurso de ganchos de ação de dados foi substituído devido a problemas de desempenho. |
| **Substituída por outro recurso?**   | Em vez disso, recomenda-se usar [substituições de ação de dados](../e-commerce-extensibility/data-action-overrides.md) para modificar a lógica comercial na camada de ação de dados.|
| **Áreas afetadas do produto**         | Ações de dados de extensibilidade do comércio eletrônico |
| **Opção de implantação**              | Todas |
| **Status**                         | botãoPreterido: a partir da versão 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Recursos removidos ou substituídos na versão 10.0.10 do Commerce
### <a name="pos-operation-803---picking-and-receiving"></a>Operação PDV 803 - Separação e Recebimento
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As operações de separação e recebimento estão sendo preteridas devido à nova reestruturação da operação. |
| **Substituída por outro recurso?**   | Sim. Ele é substituído por duas novas operações PDV: operação de entrada (804) e operação de saída (805).|
| **Áreas afetadas do produto**         | Aplicativo de ponto de venda (PDV) |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.10, a operação de separação e recebimento não receberá mais nenhuma atualização de recurso nova. Somente correções críticas de bugs serão realizadas para esta operação em versões futuras. Todos os clientes são incentivados a mudar para as novas [operações de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) e de [saída](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), o que continuará a ser parte de nosso roteiro de produtos de longo prazo. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Recursos removidos ou substituídos na versão 10.0.7 do Commerce
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API de GetProductAvailabilities e GetAvailableInventoryNearby comerciais
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | APIs novas e otimizadas foram criadas para substituir APIs GetProductAvailabilities e GetAvailableInventoryNearby. |
| **Substituída por outro recurso?**   | Sim: ele é substituído por APIs de GetEstimatedAvailabilty e GetEstimatedProductWarehouseAvailability. |
| **Áreas afetadas do produto**         | Aplicativo SDK de comércio eletrônico |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir da versão 10.0.7, não terão mais investimentos em engenharia feitos para GetProductAvailabilities e GetAvailableInventoryNearby. As organizações que usam essas APIs em suas implantações de comércio eletrônico devem ser convertidas em novas APIs de GetEstimatedAvailability e GetEstimatedProductWarehouseAvailability e habilitar o [Recurso de cálculo de disponibilidade de produtos otimizados](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).

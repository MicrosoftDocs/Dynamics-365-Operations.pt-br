---
title: "Ajustes de preço e descontos"
description: "Este artigo fornece informações sobre os ajustes de preço e descontos no varejo e comércio no Microsoft Dynamics 365 para as operações."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 01f249cbdabc6febf23dcd7103d4587cecdaad08
ms.lasthandoff: 03/31/2017


---

# <a name="price-adjustments-and-discounts"></a>Ajustes de preço e descontos

Este artigo fornece informações sobre os ajustes de preço e descontos no varejo e comércio no Microsoft Dynamics 365 para as operações.

Em dynamics 365 - venda para operações de varejo, você pode fazer ajustes de preço a produtos, e também pode configurar descontos aplicados a um item de linha ou uma transação de venda (POS), ordem de venda call center, ou ordem online. Os ajustes de preço e descontos podem ser vinculados a grupos de preços. Para ajustes de preço e descontos, você pode especificar uma única data inicial e data final ou um período recorrente, um código do desconto e alguns atributos adicionais. Os ajustes de preço e os descontos podem ser aplicados a produtos, a variantes ou categorias. Se mais de um desconto for aplicado a um produto, um cliente poderá receber um dos descontos ou um desconto combinado, dependendo da configuração do desconto. O dynamics 365 para operações aplicar automaticamente o desconto ou a combinação de descontos que oferecem o melhor preço para o cliente. Quando você configura um ajuste de preço ou um desconto, certifique-se de confirmar que os grupos de preços serão atribuídos aos canais, aos catálogos, às afiliações ou aos programas de fidelidade corretos aos quais você deseja que o desconto seja aplicado. Além disso, se quiser gerar automaticamente a ID de desconto, você poderá configurar sequências numéricas na página **Parâmetros de varejo** antes de definir um novo desconto ou ajuste de preço. **Observação:** Você pode excluir um ajuste de preço ou um desconto. No entanto, as informações estatísticas serão perdidas.

### <a name="types-of-discounts"></a>Tipos de descontos

Há quatro tipos de descontos de varejo:

-   **Desconto simples** – Uma única porcentagem ou valor.
-   **Desconto por quantidade** – Um desconto que é aplicado quando dois ou mais produtos são comprados.
-   **Desconto da compra combinada** – Um desconto que é aplicado quando uma combinação específica de produtos é comprada.
-   **Desconto de limite** – Um desconto que é aplicado quando o total da transação for maior do que um valor especificado.

Os ajustes de preço e descontos podem ser associados aos grupos de preços. Os grupos de preços podem ser associados aos canais, aos catálogos, às afiliações e aos programas de fidelidade.



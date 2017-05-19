---
title: "Ajustes de preço e descontos"
description: "Este artigo oferece informações sobre ajustes de preço e descontos no Varejo e comércio no Microsoft Dynamics 365 for Operations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: cb4f189b1f51788dea84702e4410cfaf8f570865
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="price-adjustments-and-discounts"></a>Ajustes de preço e descontos

[!include[banner](includes/banner.md)]


Este artigo oferece informações sobre ajustes de preço e descontos no Varejo e comércio no Microsoft Dynamics 365 for Operations.

No Microsoft Dynamics 365 for Operations - Varejo, você pode fazer ajustes de preço a produtos, e também pode configurar descontos aplicados a um item de linha ou a uma transação no ponto de venda (PDV), em uma ordem de venda do call center ou em uma ordem online. Os ajustes de preço e descontos podem ser vinculados a grupos de preços. Para ajustes de preço e descontos, você pode especificar uma única data inicial e data final ou um período recorrente, um código do desconto e alguns atributos adicionais. Os ajustes de preço e os descontos podem ser aplicados a produtos, a variantes ou categorias. Se mais de um desconto for aplicado a um produto, um cliente poderá receber um dos descontos ou um desconto combinado, dependendo da configuração do desconto. O Microsoft Dynamics 365 for Operations aplica automaticamente o desconto ou a combinação de descontos que oferecem o melhor preço ao cliente. Quando você configura um ajuste de preço ou um desconto, certifique-se de confirmar que os grupos de preços serão atribuídos aos canais, aos catálogos, às afiliações ou aos programas de fidelidade corretos aos quais você deseja que o desconto seja aplicado. Além disso, se quiser gerar automaticamente a ID de desconto, você poderá configurar sequências numéricas na página **Parâmetros de varejo** antes de definir um novo desconto ou ajuste de preço. **Observação:** Você pode excluir um ajuste de preço ou um desconto. No entanto, as informações estatísticas serão perdidas.

### <a name="types-of-discounts"></a>Tipos de descontos

Há quatro tipos de descontos de varejo:

-   **Desconto simples** – Uma única porcentagem ou valor.
-   **Desconto por quantidade** – Um desconto que é aplicado quando dois ou mais produtos são comprados.
-   **Desconto da compra combinada** – Um desconto que é aplicado quando uma combinação específica de produtos é comprada.
-   **Desconto de limite** – Um desconto que é aplicado quando o total da transação for maior do que um valor especificado.

Os ajustes de preço e descontos podem ser associados aos grupos de preços. Os grupos de preços podem ser associados aos canais, aos catálogos, às afiliações e aos programas de fidelidade.





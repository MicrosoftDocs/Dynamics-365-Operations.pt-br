---
title: "Ajustes de preço e descontos"
description: "Este artigo oferece informações sobre ajustes de preço e descontos no Varejo e comércio no Microsoft Dynamics para Varejo."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 9220cc12abf7134d425e088939d20ea03239a75a
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="price-adjustments-and-discounts"></a>Ajustes de preço e descontos

[!include [banner](includes/banner.md)]

Este artigo oferece informações sobre ajustes de preço e descontos no Varejo e comércio no Microsoft Dynamics para Varejo.

No Microsoft Dynamics 365 para Varejo, você pode fazer ajustes de preço a produtos, e também pode configurar descontos aplicados a um item de linha ou a uma transação no ponto de venda (PDV), em uma ordem de venda do call center ou em uma ordem online. Os ajustes de preço e descontos podem ser vinculados a grupos de preços. Para ajustes de preço e descontos, você pode especificar uma única data inicial e data final ou um período recorrente, um código do desconto e alguns atributos adicionais. Os ajustes de preço e os descontos podem ser aplicados a produtos, a variantes ou categorias. Se mais de um desconto for aplicado a um produto, um cliente poderá receber um dos descontos ou um desconto combinado, dependendo da configuração do desconto. O Microsoft Dynamics 365 para Varejo aplica automaticamente o desconto ou a combinação de descontos que oferecem o melhor preço ao cliente. Quando você configura um ajuste de preço ou um desconto, certifique-se de confirmar que os grupos de preços serão atribuídos aos canais, aos catálogos, às afiliações ou aos programas de fidelidade corretos aos quais você deseja que o desconto seja aplicado. Além disso, se quiser gerar automaticamente a ID de desconto, você poderá configurar sequências numéricas na página **Parâmetros de varejo** antes de definir um novo desconto ou ajuste de preço. **Observação:** Você pode excluir um ajuste de preço ou um desconto. No entanto, as informações estatísticas serão perdidas.

### <a name="types-of-discounts"></a>Tipos de descontos

Há quatro tipos de descontos de varejo:

-   **Desconto simples** – Uma única porcentagem ou valor.
-   **Desconto por quantidade** – Um desconto que é aplicado quando dois ou mais produtos são comprados.
-   **Desconto da compra combinada** – Um desconto que é aplicado quando uma combinação específica de produtos é comprada.
-   **Desconto de limite** – Um desconto que é aplicado quando o total da transação for maior do que um valor especificado.

Os ajustes de preço e descontos podem ser associados aos grupos de preços. Os grupos de preços podem ser associados aos canais, aos catálogos, às afiliações e aos programas de fidelidade.





---
title: Ajustes de preço e descontos
description: Este artigo oferece informações sobre ajustes de preço e descontos no Dynamics 365 Commerce.
author: scott-tucker
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d64632d7726fa5093bd04232790cae3f75938ae5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231214"
---
# <a name="price-adjustments-and-discounts"></a>Ajustes de preço e descontos

[!include [banner](includes/banner.md)]

Este artigo oferece informações sobre ajustes de preço e descontos no Dynamics 365 Commerce.

No Commerce, você pode fazer ajustes de preços nos produtos e também configurar descontos para serem aplicados a um item de linha ou uma transação no ponto de venda (PDV), em uma ordem de venda do call center ou em uma ordem online. Os ajustes de preço e descontos podem ser vinculados a grupos de preços. Para ajustes de preço e descontos, você pode especificar uma única data inicial e data final ou um período recorrente, um código do desconto e alguns atributos adicionais. 

Os ajustes de preço e os descontos podem ser aplicados a produtos, a variantes ou categorias. Se mais de um desconto for aplicado a um produto, um cliente poderá receber um dos descontos ou um desconto combinado, dependendo da configuração do desconto. O Commerce aplica automaticamente o desconto ou a combinação de descontos que oferecem o melhor preço ao cliente. Quando você configura um ajuste de preço ou um desconto, certifique-se de confirmar que os grupos de preços serão atribuídos aos canais, aos catálogos, às afiliações ou aos programas de fidelidade corretos aos quais você deseja que o desconto seja aplicado. Além disso, se quiser gerar automaticamente a ID de desconto, você poderá configurar sequências numéricas na página **Parâmetros do Commerce** antes de definir um novo desconto ou ajuste de preço.

> [!NOTE]
> Você pode excluir um ajuste de preço ou um desconto. No entanto, as informações estatísticas serão perdidas.

## <a name="types-of-discounts"></a>Tipos de descontos

Há muitos tipos de descontos:

- **Desconto simples** – Uma única porcentagem ou valor.
- **Desconto por quantidade** – Um desconto que é aplicado quando dois ou mais produtos são comprados.
- **Desconto da compra combinada** – Um desconto que é aplicado quando uma combinação específica de produtos é comprada.
- **Desconto de limite** – Um desconto que é aplicado quando o total da transação for maior do que um valor especificado.
- **Desconto com base no meio de pagamento** – Um desconto aplicado quando o total da transação é maior do que um valor especificado e um tipo de pagamento específico (por exemplo, dinheiro, cartão de crédito ou de débito) é usado para o pagamento.
- **Desconto de remessa** – Um desconto aplicado quando o total da transação é maior do que um valor especificado e um modo de entrega específico (por exemplo, remessa em dois dias ou remessa em 24h) é usado na ordem.

Os ajustes de preço e descontos podem ser associados aos grupos de preços. Os grupos de preços podem ser associados aos canais, aos catálogos, às afiliações e aos programas de fidelidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
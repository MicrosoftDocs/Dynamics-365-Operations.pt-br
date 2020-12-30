---
title: Usar o mecanismo de definição de preços do Dynamics 365 Commerce com o Dynamics 365 Sales
description: Este tópico descreve como usar o mecanismo de definição de preços no Microsoft Dynamics 365 Commerce para criar cotações de vendas no Dynamics 365 Sales.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: fad5c21d75db62b85efe803f1667dd3f9164a5fc
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594909"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Usar o mecanismo de definição de preços do Dynamics 365 Commerce com o Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Este tópico descreve como usar o mecanismo de definição de preços no Microsoft Dynamics 365 Commerce para criar cotações de vendas no Dynamics 365 Sales.

O mecanismo de definição de preços do Dynamics 365 Commerce oferece suporte à maioria dos cenários de precificação de business-to-consumer (B2C), como definição de preços no nível de armazenamento, definição de preços com base em fidelidade e afiliação, descontos de compra combinada, descontos de quantidade e descontos de limite. O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem.

Ao usar a [gravação dupla](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), você tem três opções para as necessidades de definição de preços. Você pode usar a precificação estática que vem da lista de preços no Dynamics 365 Sales, o mecanismo de precificação no Dynamics 365 Supply Chain Management ou o mecanismo de precificação no Dynamics 365 Commerce. Entre essas opções, o mecanismo de precificação comercial é mais adequado para os cenários B2C.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Usar o mecanismo de precificação comercial em Vendas

> [!NOTE]
> No momento, o mecanismo de precificação comercial pode ser usado somente para a criação de cotações nas Vendas. A integração da ordem de venda com o mecanismo de precificação comercial ainda não está disponível.

Quando os usuários iniciarem uma cotação nas Vendas, a estrutura de gravação dupla copiará os detalhes da cotação para o Commerce. As alterações nas linhas de cotação existentes ou em quaisquer linhas de cotação adicionadas recentemente nas vendas são copiadas para o Commerce. Quando os usuários desejarem usar o mecanismo de precificação do Commerce para calcular o preço da cotação, eles poderão selecionar **Cotação de preços** para atualizar os preços da cotação, com base no mecanismo de precificação do Commerce. Os preços são atualizados automaticamente no Sales and Commerce.

## <a name="prerequisites"></a>Pré-requisitos

- Antes de usar o mecanismo de precificação do Commerce no Sales, você deve seguir as etapas do [Cliente potencial com pagamento à vista em gravação dupla](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).
- Você deve desativar a avaliação do contrato comercial para a entrada manual seguindo estas etapas:

    1. No ambiente do Commerce, vá para **Contas a receber \> Configuração \> parâmetros de Contas a receber**.
    1. Na guia **Preços**, na guia rápida **Avaliação de contrato comercial**, desmarque a caixa de seleção **Entrada manual**.

## <a name="additional-resources"></a>Recursos adicionais

[Cliente potencial com pagamento à vista em gravação dupla](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)

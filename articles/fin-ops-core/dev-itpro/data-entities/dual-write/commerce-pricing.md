---
title: Usar o mecanismo de definição de preços do Dynamics 365 Commerce com o Dynamics 365 Sales
description: Este artigo descreve como usar o mecanismo de definição de preços no Microsoft Dynamics 365 Commerce para criar cotações de vendas no Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 11a164ec15c8b7a69172a153b961011a8b324712
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881384"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Usar o mecanismo de definição de preços do Dynamics 365 Commerce com o Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Este artigo descreve como usar o mecanismo de definição de preços no Microsoft Dynamics 365 Commerce para criar cotações de vendas no Dynamics 365 Sales.

O mecanismo de definição de preços do Dynamics 365 Commerce oferece suporte à maioria dos cenários de precificação de business-to-consumer (B2C), como definição de preços no nível de armazenamento, definição de preços com base em fidelidade e afiliação, descontos de compra combinada, descontos de quantidade e descontos de limite. O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem.

Ao usar a [gravação dupla](./dual-write-overview.md), você tem três opções para as necessidades de definição de preços. Você pode usar a precificação estática que vem da lista de preços no Dynamics 365 Sales, o mecanismo de precificação no Dynamics 365 Supply Chain Management ou o mecanismo de precificação no Dynamics 365 Commerce. Entre essas opções, o mecanismo de precificação comercial é mais adequado para os cenários B2C.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Usar o mecanismo de precificação comercial em Vendas

> [!NOTE]
> No momento, o mecanismo de precificação comercial pode ser usado somente para a criação de cotações nas Vendas. A integração da ordem de venda com o mecanismo de precificação comercial ainda não está disponível.

Quando os usuários iniciarem uma cotação nas Vendas, a estrutura de gravação dupla copiará os detalhes da cotação para o Commerce. As alterações nas linhas de cotação existentes ou em quaisquer linhas de cotação adicionadas recentemente nas vendas são copiadas para o Commerce. Quando os usuários desejarem usar o mecanismo de precificação do Commerce para calcular o preço da cotação, eles poderão selecionar **Cotação de preços** para atualizar os preços da cotação, com base no mecanismo de precificação do Commerce. Os preços são atualizados automaticamente no Sales and Commerce.

## <a name="prerequisites"></a>Pré-requisitos

- Antes de usar o mecanismo de precificação do Commerce no Sales, você deve seguir as etapas do [Cliente potencial com pagamento à vista em gravação dupla](./dual-write-prospect-to-cash.md).
- Você deve desativar a avaliação do contrato comercial para a entrada manual seguindo estas etapas:

    1. No ambiente do Commerce, Acesse **Contas a receber \> Configuração \> parâmetros de Contas a receber**.
    1. Na guia **Preços**, na guia rápida **Avaliação de contrato comercial**, desmarque a caixa de seleção **Entrada manual**.

## <a name="additional-resources"></a>Recursos adicionais

[Cliente potencial com pagamento à vista em gravação dupla](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
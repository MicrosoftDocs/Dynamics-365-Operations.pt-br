---
title: Ajustes de preço de varejo
description: Este procedimento orienta na criação de um ajuste de preço comercial.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0506c78a1a5191ff467f5bd65c0403113336cc9720ea4a447d77331dfe366232
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764504"
---
# <a name="retail-price-adjustments"></a>Ajustes de preço de varejo

[!include [banner](../includes/banner.md)]

Este procedimento orienta na criação de um ajuste de preço comercial. Um ajuste de preço pode definir o preço de venda de um item diretamente ou modificar o preço base de venda ou o preço de venda do contrato comercial. Este procedimento usa a empresa de dados de demonstração USRT.

1. Clique em Gerenciamento de preços e descontos.
2. Clique na guia Ajustes de preço.
3. Clique em Novo.
    * Aqui você pode criar todas as regras de preços e descontos mais comumente usadas, incluindo descontos, ajustes de preço, diários de contratos comerciais e regras de preços de categoria.  
4. Clique em Ajuste de preço.
5. No campo Nome, digite um valor.
6. Expandir a seção Linhas.
7. Clique em Adicionar.
    * Neste exemplo, insira '81126' no campo Produto. Em seguida, insira '10,0' no campo Porcentagem de desconto.  
    * Um ajuste de preço do tipo porcentagem de desconto reduzirá um preço base de venda ou um preço de venda do contrato comercial.  
8. Clique em Adicionar.
    * Para este exemplo, insira '81125' no campo Produto. Depois, selecione 'Valor do desconto à vista' no campo Método de desconto.    Por último, insira '5,0' no campo Valor do desconto à vista.  
    * Um tipo de desconto de valor de desconto à vista é um valor deduzido de um preço base ou de um preço do contrato comercial.  
9. Clique em Grupos de preços.
    * Selecione 'RP-Houston' no campo Grupo de preços.  
    * Isso associará o ajuste de preço à loja Houston.  
10. Clique em Salvar.
11. Feche a página.
12. No campo Status, selecione 'Habilitado'.
13. Clique em Salvar.
14. Feche a página.
15. Atualize a página.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
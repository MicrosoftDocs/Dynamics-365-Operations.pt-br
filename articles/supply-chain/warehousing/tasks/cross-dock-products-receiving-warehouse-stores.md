---
title: Produtos de distribuição integrada de recebimento de depósitos para armazenamento
description: Este procedimento orienta nas etapas para criar e processar uma distribuição integrada dos produtos do local de recebimento de uma ordem de compra para uma ou várias lojas.
author: ShylaThompson
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c660534053793b454f8558a114eb4db1d715472c126f55dc97171a31e2a1ab9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724715"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Produtos de distribuição integrada de recebimento de depósitos para armazenamento

[!include [banner](../../includes/banner.md)]

Este procedimento orienta nas etapas para criar e processar uma distribuição integrada dos produtos do local de recebimento de uma ordem de compra para uma ou várias lojas. O usuário pode definir várias configurações e fazer com que o sistema sugira como distribuir os produtos ou inserir manualmente onde os produtos serão distribuídos e a quantidade distribuída em cada loja. O procedimento não inclui a instalação de dados que possam ser usados na distribuição integrada, como regras de reabastecimento, hierarquias das organizações e pesos das lojas. Este procedimento usa a empresa de dados de demonstração USRT.

1. Ir para Todas as ordens de compra.
2. Selecione uma ordem de compra na lista e clique no link para abrir a ordem.
3. No Painel de Ação, clique em Varejo e Comércio.
4. Clique em Distribuição integrada.
5. Clique em Editar.
    * A categoria pode ser usada para filtrar os itens na seção Linhas.  
6. Na lista, localize e selecione o PDV desejado.
7. No campo Quantidade de distribuição integrada, digite um valor para especificar a quantidade do produto selecionado sendo comprado que deve ser distribuída.
8. No campo Quantidade de distribuição integrada adicional, insira um valor para especificar as quantidades de distribuição para os produtos disponíveis que estão sendo comprados.
9. No campo Distribuição, insira 'Peso da localização'.
    * Você pode selecionar os outros tipos para usar regras diferentes para a distribuição.  
10. No campo Hierarquia de reabastecimento, selecione um valor.
11. Selecione Sim no campo Respeitar classificações.
12. Clique em Calcular quantidades.
13. Clique em Criar ordem.
14. Clique em Sim.
15. Na lista, localize e selecione um depósito que tenha recebido produtos.
16. Clicar em Ordem para exibir as ordens criadas para o depósito selecionado



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
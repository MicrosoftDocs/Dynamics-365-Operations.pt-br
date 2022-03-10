---
title: Produtos de distribuição integrada de recebimento de depósitos para armazenamento
description: Este procedimento orienta nas etapas para criar e processar uma distribuição integrada dos produtos do local de recebimento de uma ordem de compra para uma ou várias lojas.
author: Mirzaab
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e65535a1879eab229f185e0e97d81a304fd292d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572952"
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
---
title: Mover produtos do centro de distribuição para a loja usando a compra centralizada
description: Este procedimento orienta nas etapas para criar e processar uma compra centralizada para distribuir produtos de um localização para uma ou várias lojas.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62eeb29e348c558e8954f656b89d90792b0c347b
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021591"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a>Mover produtos do centro de distribuição para a loja usando a compra centralizada

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta nas etapas para criar e processar uma compra centralizada para distribuir produtos de um localização para uma ou várias lojas. O usuário pode definir várias configurações e fazer com que o sistema sugira como distribuir os produtos ou inserir manualmente onde os produtos serão distribuídos e a quantidade distribuída em cada loja. Este procedimento não inclui a instalação de dados que possam ser usados na compra centralizada, como regras de reabastecimento, hierarquias das organizações e pesos das lojas. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Compra centralizada.
2. Clique em Novo.
3. No campo Descrição, digite um valor.
4. No campo Local, insira ou selecione um valor.
5. No campo Depósito, insira ou selecione um depósito que tenha produtos com quantidades disponíveis.
6. Clique em Adicionar.
7. Na lista, marque a linha selecionada.
8. No campo Número do item, insira ou selecione um produto.
9. Clique em Adicionar.
10. Na lista, marque a linha selecionada.
11. No campo Número do item, insira ou selecione uma grade de produto.
    * Ao inserir uma grade de produto, serão criadas linhas para cada grade.  
12. Na lista, marque uma linha.
13. No campo Quantidade de compra centralizada, digite a quantidade do produto selecionado que você deseja distribuir.
14. No campo Quantidade de compra centralizada adicional, insira a quantidade de produtos com quantidade disponível para serem distribuídos.
15. No campo Distribuição, insira 'Peso da localização'.
    * Você pode selecionar outros tipos para usar outras regras para a distribuição.  
16. No campo Hierarquia de reabastecimento, selecione um valor.
17. Selecione Sim no campo Respeitar classificações.
18. Clique em Calcular quantidades e examine as quantidades que são adicionadas às linhas na seção Depósito.
19. Clique em Criar ordem.
20. Clique em Sim.


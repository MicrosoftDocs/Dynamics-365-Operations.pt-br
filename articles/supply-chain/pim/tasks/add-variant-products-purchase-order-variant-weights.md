--- 
title: Adicionar produtos de variante a ordens de compra usando pesos de variante
description: Este procedimento mostra as etapas para usar pesos de variante para preencher automaticamente as linhas da ordem de compra para cada variante de um produto.
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 410b3a88b3decb31ed6ce9373f14a11bf354acce
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>Adicionar produtos de variante a ordens de compra usando pesos de variante

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra as etapas para usar pesos de variante para preencher automaticamente as linhas da ordem de compra para cada variante de um produto. Quando você seleciona a quantidade do produto que você deseja comprar, as linhas da ordem de compra são criadas para todas as variantes do produto com as quantidades sugeridas com base nos pesos configurados nas variantes do produto. Este procedimento não inclui etapas para configurar valores de peso nas dimensões do produto e nas variantes de produto. Este procedimento usa a empresa USRT nos dados de demonstração.

1. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.
5. Alternar a expansão da seção Geral.
6. No campo Local, clique no botão suspenso para abrir a pesquisa.
7. Na lista, clique no link na linha selecionada.
8. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o PDV desejado.
10. Na lista, clique no link na linha selecionada.
11. Clique em OK.
12. Ative a expansão da seção Detalhes de linha.
13. Clique na guia Variantes.
14. Clique em Adicionar nova linha.
15. Na lista, marque a linha selecionada.
16. No campo Número de item, digite '0140'.
17. Defina a quantidade como '1000'.
18. Clique em Salvar.


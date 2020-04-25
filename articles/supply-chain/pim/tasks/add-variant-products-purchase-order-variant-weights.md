---
title: Adicionar produtos de variante a ordens de compra usando pesos de variante
description: Este procedimento mostra as etapas para usar pesos de variante para preencher automaticamente as linhas da ordem de compra para cada variante de um produto.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0199f4b05c23eec5c03c770c37111a6ee6d13efe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208377"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>Adicionar produtos de variante a ordens de compra usando pesos de variante

[!include [banner](../../includes/banner.md)]

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


--- 
title: "Configurar regras e parâmetros para a distribuição integrada e a compra centralizada"
description: Este procedimento demonstra as etapas para criar regras de reabastecimento.
author: josaw1
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 08f047ab38aea4958da97d80d7d274644b735cd7
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a>Configurar regras e parâmetros para a distribuição integrada e a compra centralizada

[!include [task guide banner](../includes/task-guide-banner.md)]

Este procedimento demonstra as etapas para criar regras de reabastecimento. As regras de reabastecimento podem ser usadas para controlar como os produtos são distribuídos para as lojas ao usar a distribuição integrada e a compra centralizada. As regras de reabastecimento podem ser configuradas para lojas ou grupos de lojas. O peso definido para cada linha em uma regra controlará como as quantidades de produtos serão distribuídas entre as lojas ao usar regras de reabastecimento como o método de distribuição em distribuições integradas ou compras centralizadas. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Regras de reabastecimento.
2. Clique em Novo.
3. No campo Regra de reabastecimento, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Clique em Adicionar.
7. Na lista, marque a linha selecionada.
    * Você pode escolher Hierarquia de reabastecimento ou Canal para o tipo. O valor controla se a seleção em Nome será uma hierarquia de canais ou um canal específico.  Neste exemplo, deixe-o definido como uma hierarquia de reabastecimento.  
8. No campo Nome, selecione um valor.
    * O valor padrão do peso é preenchido a partir do peso definido no depósito.  Esse peso pode ser usado para a regra de reabastecimento ou você pode inserir um novo peso no campo Peso.  
9. No campo Peso, insira um número.
10. Clique em Adicionar.
11. Na lista, marque a linha selecionada.
12. No campo Tipo, selecione 'Canal'.
13. No campo Nome, insira ou selecione um valor.
14. No campo Peso, insira um número.
15. Clique em Salvar.



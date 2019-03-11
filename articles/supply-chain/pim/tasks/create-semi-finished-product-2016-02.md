---
title: Criar um produto semifinalizado (Fevereiro de 2016)
description: Esta tarefa tem como foco criar um produto semifinalizado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9caeae552471eed1cb1d8630f387ca31107fcece
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "362846"
---
# <a name="create-a-semi-finished-product-february-2016"></a>Criar um produto semifinalizado (Fevereiro de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarefa tem como foco criar um produto semifinalizado. Trata-se da segunda tarefa na série de cálculo BOM. A empresa de dados demo usada para criar esta tarefa é USMF.

1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Clique em Novo.
3. No campo Número do produto, digite um valor.
    * Neste exemplo, digite BOM_2.  
4. No campo Grupo de modelos do item, insira ou selecione um valor.
    * Selecione STD. STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.  
5. No campo Grupo de itens, insira ou selecione um valor.
    * Por exemplo, selecione Áudio. Isso não tem impacto sobre os cálculos de custo.  
6. No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.
    * Selecione SiteWH. Apenas Site e Depósito serão usados neste exemplo.  
7. No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.
    * A dimensão de rastreamento não será usada neste exemplo. Selecione Nenhuma.  
8. Clique em OK.
9. No Painel de Ação, clique em Gerenciar estoque.
10. Clique em Configurações de ordem padrão.
11. No campo Tipo de ordem padrão, selecione "Produção".
    * Como se trata de um produto semifinalizado que será produzido, selecione Produção.  
12. No campo Site de compra, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
13. No campo Site de estoque, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
14. No campo Site de vendas, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
15. Feche a página.
16. No Painel de Ação, clique em Gerenciar custos.
17. Clique em Preço de item.
18. Clique em Novo.
19. Na lista, marque a linha selecionada.
20. No campo Versão, insira ou selecione um valor.
    * Neste exemplo, selecione Versão 10.  
21. No campo Local, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
22. Defina o preço como "10".
    * Neste exemplo, digite um preço de custo de 10.  
23. Clique em Salvar.
24. Clique em Ativar preço(s) pendente(s).
25. Feche a página.
26. Feche a página.
27. Clique em BOM_2 para abri-lo.
28. Expanda a seção Gerenciar custos.
29. No campo Grupo de custos, insira ou selecione um valor.
    * Neste exemplo, selecione Grupo de custos M1.  
30. Use o atalho para salvar um registro.
31. Feche a página.


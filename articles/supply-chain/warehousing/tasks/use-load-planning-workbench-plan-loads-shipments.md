--- 
title: Planejar cargas e remessas usando a Bancada de planejamento de carga
description: Este procedimento mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f840a4c15305af5f55451ae7f1cec2da25e685a4
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planejar cargas e remessas usando a Bancada de planejamento de carga

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda. Como um pré-requisito iremos criar a ordem de venda primeiro. Este procedimento é parte do trabalho diário do coordenador de transporte. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-sales-order"></a>Criar uma ordem de venda
1. Vá para Contas a receber > Ordens > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Selecione a conta US-004.
5. Clique em OK.
6. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
7. Selecione o item A0001.
    * A0001 está habilitado para o gerenciamento de transporte.  
8. Na lista, clique no link na linha selecionada.
9. No campo Quantidade, insira um número.
10. No campo Depósito, digite '24'.
    * Neste exemplo selecione o depósito 24. Este depósito está habilitado para o gerenciamento de transporte e para o gerenciamento de depósito avançado.  
11. Clique em Salvar.
12. Feche a página.

## <a name="create-a-new-load"></a>Criar uma nova carga
1. Vá para Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.
2. Clique na aba Linhas de Vendas.
    * Agora você irá montar a carga para a ordem de venda que você acabou de criar. Cargas podem ser montadas de acordo com a oferta e procura das ordens de compra, ordens de transferência, e ordens de venda.  
3. No Painel de Ação, clique em Oferta e demanda.
4. Clique em Para nova carga.
5. No campo ID do modelo de carga, clique no botão suspenso para abrir a pesquisa.
    * O modelo de carga define as medidas máximas para peso e volume da carga total. Por exemplo, o modelo de carga pode representar o tamanho de um contêiner ou caminhão.  
6. Na lista, clique no link na linha selecionada.
7. Clique em OK.

## <a name="rate-and-route-the-load"></a>Avaliar e encaminhar a carga
1. Clique em Classificação e roteiro.
2. Clique em Bancada do roteiro de taxa.
3. Clique em Loja de taxas.
4. Na lista, localize e selecione o PDV desejado.
5. Clique em Atribuir.
6. Feche a página.
7. Feche a página.



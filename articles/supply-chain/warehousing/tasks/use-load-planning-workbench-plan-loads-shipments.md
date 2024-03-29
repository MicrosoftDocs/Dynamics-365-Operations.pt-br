---
title: Planejar cargas e remessas usando a Bancada de planejamento de carga
description: Este artigo mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.
author: Mirzaab
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e53b7667dd4589a7c6c14b8aaf8ba51017eee0d
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068320"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planejar cargas e remessas usando a Bancada de planejamento de carga

[!include [banner](../../includes/banner.md)]

Este artigo mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda. Como um pré-requisito iremos criar a ordem de venda primeiro. Este procedimento é parte do trabalho diário do coordenador de transporte. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-sales-order"></a>Criar uma ordem de venda
1. Acesse o **Painel de navegação > Módulos > Contas a receber > Ordens > Todas as ordens de venda**.
2. Selecione **Novo**.
3. No campo **Conta do cliente**, selecione o botão suspenso para abrir a pesquisa.
4. Selecione a conta **US-004**.
5. Selecione **OK**.
6. No campo **Número do item**, selecione o botão suspenso para abrir a pesquisa.
7. Selecione o item **A0001**. **A0001** está habilitado para o gerenciamento de transporte.  
8. No campo **Site**, selecione o botão suspenso para abrir a pesquisa e então selecione um item.
9. No campo **Quantidade.**, insira um número
10. No campo **Depósito**, digite '24' neste exemplo. Este depósito está habilitado para o gerenciamento de transporte e para os processos do gerenciamento de depósito (WMS).  
11. Selecione **Salvar**.
12. Feche a página.

## <a name="create-a-new-load"></a>Criar uma nova carga
1. Acesse o **Painel de navegação > Módulos > Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga**.
2. Selecione a guia **Linhas de vendas**. Agora você irá montar a carga para a ordem de venda que você acabou de criar. Cargas podem ser montadas de acordo com a oferta e procura das ordens de compra, ordens de transferência, e ordens de venda.  
3. No Painel de Ação, selecione **Oferta e demanda**.
4. Selecione **Para nova carga**.
5. No campo **ID do modelo de carga**, selecione o botão suspenso para abrir a pesquisa. O modelo de carga define as medidas máximas para peso e volume da carga total. Por exemplo, o modelo de carga pode representar o tamanho de um contêiner ou caminhão. Selecione um item.
6. Selecione **OK**.

## <a name="rate-and-route-the-load"></a>Avaliar e encaminhar a carga
1. Selecione **Classificação e roteiro**.
2. Selecione **Bancada da taxa de roteiro**.
3. Selecione **Loja de taxas**.
4. Na lista, localize e selecione o registro desejado.
5. Selecionar **Atribuir**.
6. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
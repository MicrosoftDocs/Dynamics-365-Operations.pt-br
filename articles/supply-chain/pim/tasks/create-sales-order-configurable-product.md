---
title: Criar uma ordem de venda para um produto configurável
description: Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e42f121d1efa66f85a3dd811606962b907ed177d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570576"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Criar uma ordem de venda para um produto configurável

[!include [banner](../../includes/banner.md)]

Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda. Este exemplo usa o modelo do Palestrante D0006 na empresa de dados demo USMF. Normalmente, um processador de ordens de venda usa este procedimento.

## <a name="create-a-sales-order"></a>Criar uma ordem de venda

1. Acesse **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.
1. Selecione **Novo**.
1. Selecione **Ordem de venda**.
1. No campo **Conta do cliente**, selecione *US-001*. 
1. Selecione **OK**.
1. No campo **Número de item**, selecione *D0006*.
    * Para essa tarefa, você deve selecionar um produto configurável.  
1. Selecione **Produto e fornecimento**.
1. Selecione **Configurar linha**.
    * Observe que o preço foi alterado, com base na configuração selecionada, e que o campo **Incluir cabo** agora foi configurado como *Verdadeiro*.  
    * Anote o preço padrão e as configurações que estão selecionadas para o período.  
1. Selecione **Carregar modelo**.
    * Esse exemplo mostra como é possível aplicar um modelo para selecionar uma configuração predefinida. Se você estiver usando este procedimento como um guia de tarefas e deseja consultar outros valores de atributo que estão disponíveis, selecione o botão **Desbloquear**.  
1. Selecione **OK**.
1. Selecione **OK**.
1. Expanda a seção **Detalhes da linha**.
1. Selecione a guia **Produto**.
    * A configuração do item está listada agora nas dimensões do produto.  
1. Feche a página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
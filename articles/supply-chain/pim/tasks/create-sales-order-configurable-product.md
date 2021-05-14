---
title: Criar uma ordem de venda para um produto configurável
description: Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921280"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Criar uma ordem de venda para um produto configurável

[!include [banner](../../includes/banner.md)]

Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda. Este exemplo usa o modelo do Palestrante D0006 na empresa de dados demo USMF. Normalmente, um processador de ordens de venda usa este procedimento.

## <a name="create-a-sales-order"></a>Criar uma ordem de venda

1. Vá para **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.
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
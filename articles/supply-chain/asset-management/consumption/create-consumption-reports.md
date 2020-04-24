---
title: Criar relatórios de consumo
description: Este tópico explica como criar relatórios de consumo no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d28acbccc35b3f59f9cca7236dd721a1d9bdead8
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216427"
---
# <a name="create-consumption-reports"></a>Criar relatórios de consumo

[!include [banner](../../includes/banner.md)]

 

Quando você cria e publica registros de consumo em ordens de serviço no Gerenciamento de Ativos, dois relatórios estão disponíveis para exibir detalhes do consumo.


## <a name="asset-consumption-report"></a>Relatório de consumo de ativos

Após o cancelamento do consumo nas ordens de serviço, é possível imprimir um relatório de consumo de ativos. O relatório exibe horas, custos de horas, custos de itens e despesas lançados em ativos.

1. Clique em **Gerenciamento de ativos** > **Relatórios** > **Ativos** > **Consumo de ativos**.

2. Na caixa de diálogo **Consumo de ativos**, selecione os parâmetros e o nível de detalhe que deseja ver selecionando **Sim** nos botões de alternância relevantes e inserindo um nível de localização funcional na seção **Mostrar**.
    - Você pode usar o campo **Níveis** para indicar o nível de detalhamento desejado das linhas de ativo em relação aos locais funcionais. 
    
        Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de localização funcional em vários níveis, todos os ativos de um local funcional serão mostrados no nível superior e, portanto, uma linha poderá ser adicionadas em locais funcionais localizados em um nível inferior. 
        
        Se você inserir o número "0" no campo **Níveis**, verá um resultado detalhado mostrando todos os ativos em todos os níveis do local funcional ao qual elas estão relacionadas. 
        
    - Selecione **Sim** no botão **Soma em todos os subativos** para alternar entre as somas de cada subativo no relatório.

3. Selecione um intervalo de datas na seção **Datas**.

4. Na Guia Rápida **Destination**, selecione se deseja exibir o relatório na tela, imprimi-lo ou salvá-lo como um arquivo ou email.

5. Se necessário, você pode selecionar ativos específicos a serem exibidos no relatório. Na Guia Rápida **Registros a serem incluídos**, clique em **Filtrar** e adicione os ativos que você deseja incluir no relatório.

6. Clique em **OK** para gerar o relatório.


## <a name="work-order-consumption-report"></a>Relatório de consumo de ordem de serviço

Após o cancelamento do consumo nas ordens de serviço, é possível imprimir um relatório de consumo de ordem de serviço. O relatório exibe horas, custos de horas, custos de itens e despesas lançados em ordens de serviço.

1. Clique em **Gerenciamento de ativos** > **Relatórios** > **Ordens de trabalho** > **Consumo de ordem de serviço**.

2. Na caixa de diálogo **Consumo de ordem de serviço**, selecione os parâmetros que deseja incluir no relatório, selecionando **Sim** nos botões de alternância relevantes na seção **Mostrar**.

3. Selecione um intervalo de datas na seção **Datas**.

4. Na Guia Rápida **Destination**, selecione se deseja exibir o relatório na tela, imprimi-lo ou salvá-lo como um arquivo ou email.

5. Se necessário, você pode selecionar ordens de serviço específicas a serem exibidas no relatório. Na Guia Rápida **Registros a serem incluídos**, clique em **Filtrar** e adicione as ordens de serviço que você deseja incluir no relatório.

6. Clique em **OK** para gerar o relatório.


>[!NOTE]
>Você também pode gerar um [relatório de ordem de serviço](../work-orders/work-order-report.md), que contém mais detalhes sobre a ordem de serviço.


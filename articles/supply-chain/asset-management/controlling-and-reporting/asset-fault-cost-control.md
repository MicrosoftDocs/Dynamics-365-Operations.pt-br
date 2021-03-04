---
title: Controle de custo de falhas de ativos
description: Este tópico explica o controle de custo de falhas de ativos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 93bd6fb320822f17af5725e227936df623f8d0be
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422082"
---
# <a name="asset-fault-cost-control"></a>Controle de custo de falhas de ativos

[!include [banner](../../includes/banner.md)]

 

No Gerenciamento de Ativos, é possível calcular os custos nos registros de falhas de ativos para obter uma visão geral dos custos reais em comparação com os custos de orçamento. Os custos reais são baseados em transações lançadas. A data é a data da falha na qual o sintoma foi registrado.

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Controle de custo de falhas de ativos**.

2. Na caixa de diálogo **Controle de custo de falhas de ativos**, selecione uma dimensão financeira definida para ser incluída no cálculo, se necessário.

4. Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados com custo zero.

5. Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de controle de custo em relação aos locais funcionais. 

    Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de localização funcional em vários níveis, todas as linhas de controle de custo de falhas de ativos para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior. 
    
    Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de controle de custos de falhas de ativos em todo o nível do local funcional ao qual elas estão relacionadas.

6. Para limitar a pesquisa, você poderá selecionar ativos específicos, datas de falha e causas de falha na Guia Rápida **Registros a serem incluídos**.

7. Clique em **OK** para iniciar o cálculo.

8. Clique nos botões **Agrupar por** para mostrar o nível de detalhes necessário para o cálculo. Os botões selecionados de **Agrupar por** são realçados. Clique em um botão para ativá-los ou desativá-los.

## <a name="example"></a>Exemplo

Esse exemplo mostra um cálculo de controle de custo de falha de ativo.

- O campo **Orçamento original** mostra os custos do orçamento da previsão da ordem de serviço. 
- O campo **Custo real** mostra os custos lançados nas ordens de serviço. 
- O campo **Custo comprometido** mostra os custos totais com os quais sua empresa está comprometida em relação às ordens de serviço.

    ![Figura 1](media/05-controlling-and-reporting.png)

Para obter informações sobre como configurar as falhas, consulte o tópico [Gerenciamento de falhas](../setup-for-work-orders/fault-management.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
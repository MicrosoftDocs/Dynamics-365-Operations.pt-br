---
title: "Pré-requisitos para uma conversão em custo padrão"
description: "Este tópico descreve as tarefas executadas antes da execução de uma conversão em custo padrão."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 50891
ms.assetid: 73af66cf-c924-45be-837a-a648dbd05a31
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 65844bd78363dc6638b16b3fd4ca163a3fde6a23
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="prerequisites-for-a-standard-cost-conversion"></a>Pré-requisitos para uma conversão em custo padrão

[!include [banner](../includes/banner.md)]

Este tópico descreve as tarefas executadas antes da execução de uma conversão em custo padrão. 

Antes de executar uma conversão de custo padrão, siga estas etapas:

1.  Defina um **grupo de modelos de item** para custos padrão. Use a página Grupos de modelos de item para criar um grupo de modelos de item que use um modelo de estoque de custo padrão. Ao configurar uma conversão em custo padrão, você atribui esse grupo de modelos de item aos itens que serão convertidos.
2.  Atribua um **grupo de custos** a cada item.
    -   O grupo de custos atribuído a um item comprado pode servir de base para atribuir contas contábeis relacionadas aos custos padrão. Isso pode incluir a atribuição de contas contáveis para variações de preço de compra. Em um ambiente de fabricação, o grupo de custos atribuído aos componentes comprados também fornece a segmentação do custo nos custos calculados de um item fabricado.
    -   O grupo de custos atribuído a um item fabricado pode agir como a base para atribuir contas contábeis relacionadas aos custos padrão, como atribuir contas contábeis para variações de produção.

3.  Atribua uma **quantidade de ordem padrão** a um item manufaturado quando ele tiver custos constantes. A quantidade de ordem padrão para um item fabricado serve como um tamanho de lote contábil para amortização, ou rateio, de custos constantes. Isso inclui os tempos de configuração em operações bancárias ou uma quantidade constante de componentes na lista de materiais (BOM).
4.  Atribua **contas contábeis** que estão relacionadas a custos padrão, principalmente à variação de reavaliação. Use a página **Lançamento** (**Gerenciamento de estoque** &gt; **Configuração**) para atribuir contas contábeis relacionadas aos custos padrão. Como mínimo do processo de conversão em custo padrão, você deve atribuir a conta para a variação da reavaliação de todos os itens e todos os grupos de custos. Use o **Plano de contas** para definir as contas contábeis necessárias para os custos padrão. Use a página **Combinações de transações** para habilitar o uso de relações de custo (para tabelas, grupos e tudo) antes de definir as regras de lançamento de item.
5.  Defina os parâmetros de estoque relacionados a custos padrão. Use a guia **Sequências numéricas** na página **Parâmetros de gerenciamento de estoque e depósito** para atribuir uma sequência numérica para comprovantes de reavaliação. Gera-se um comprovante de reavaliação quando a conversão em custo padrão gera uma alteração no valor de estoque de um item. Use a página **Parâmetros de gerenciamento de estoque e depósito** para definir parâmetros de Controle de Custo (na guia **Contabilidade de estoque**) para definir dois parâmetros relacionados a custos padrão.
    -   Use o campo **Divisão de custo** para selecionar Não ou Sub-razão. A seleção de Sub-razão é determinada como uma divisão de custo ativa. Uma divisão de custo ativa é muito importante para calcular, reter e exibir segmentações de grupo de custo em uma estrutura de produto de vários níveis para itens de custo padrão. Quando a divisão de custo está ativa, você pode relatar e analisar o seguinte em um único nível, em vários níveis ou em formato total:
        1.  Estoque
        2.  Trabalho em andamento (WIP)
        3.  Custo dos produtos vendidos (COGS) por grupo de custos

        Uma divisão de custo ativa significa que se você habilitar o custo de um item fabricado, o resultado será armazenado na segmentação do grupo de custos no registro de custo do item. Se nenhum valor for especificado no campo **Divisão de custo**, a segmentação do grupo de custos não será mantida para itens de custo padrão. Isso é, o custo padrão de um item fabricado será calculado e mantido como um valor único sem a segmentação de grupo de custo e as contribuições de custo de componentes fabricados será agregada no valor único.
    -   Use o campo **Variações do Padrão** para selecionar o grupo resumido ou por custo. A seleção de grupo por custo permite identificar variações de preço de compra e variações de produção por grupo de custos. Isso permite identificar os quatro tipos de variações de produção (o tamanho do lote, a quantidade, o preço e as variações de substituição). Se a seleção for resumida, não será possível identificar variações por grupo de custo e você não poderá identificar os quatro tipos de variações de produção. É possível visualizar somente a variação de produção resumida. A política sobre variação de padrão é independente da política de divisão de custo. Isso é, você pode selecione uma política de divisão de custo de nenhuma e selecionar variações por grupo de custo de forma que as variações de produção por grupo de custo ainda seja capturada.







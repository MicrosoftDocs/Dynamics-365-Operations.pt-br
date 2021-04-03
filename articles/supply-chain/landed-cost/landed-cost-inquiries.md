---
title: Consultas de custo de entrega
description: Este tópico descreve como localizar e usar os vários tipos de consultas que estão disponíveis para o módulo de custo de entrega.
author: sherry-zheng
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 10f5948b4e3df089aef982269143254d9ac1e8a9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500347"
---
# <a name="landed-cost-inquiries"></a>Consultas de custo de entrega

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="voyage-line-inquiries"></a>Consultas de linha de viagem

A consulta de **Linhas de viagem** mostra todas as linhas de viagem pertencentes ao estoque. Essa consulta pode ser usada como um filtro para ajudar a encontrar um item, uma ordem de compra ou outras informações úteis. Ela também pode ser usada para identificar a data de entrega esperada de um item que pode estar em uma ou mais viagens. Dessa forma, ela pode ajudá-lo a gerenciar o recebimento de estoque esperado.

Para abrir essa consulta, acesse **Custo de entrega \> Consultas \> Linhas de viagem**.

### <a name="overview-tab"></a>guia Visão geral

A guia **Visão geral** da página de consulta **Linhas de viagem** inclui uma grade que mostra informações básicas sobre cada linha da viagem relevante. A tabela a seguir descreve as colunas na grade.

| Coluna | Descrição |
|---|---|
| **Número do item** | O item da linha de viagem. |
| **Referência** | O tipo de ordem (ordem de compra ou ordem de transferência). |
| **Número** | O número da ordem de compra ou o número da ordem de transferência. |
| **Fólio** | O fólio associado à linha de viagem. |
| **Contêiner de remessa** | O contêiner de remessa associado à linha de viagem. |
| **Viagem** | A viagem associada à linha de viagem. |
| **Quantidade** | A quantidade do item para a linha de viagem. |
| (Outras dimensões) | Você pode mostrar colunas para dimensões adicionais, conforme necessário. Essas dimensões incluem o número do lote, o status do estoque e o depósito. No Painel de Ações, selecione **Estoque \> Exibir dimensões** para abrir uma caixa de diálogo na qual é possível selecionar as dimensões a serem incluídas. |

### <a name="general-tab"></a>Guia Geral

Selecione a guia **Geral** para exibir mais informações sobre a linha selecionada no momento na guia **Visão geral**.

### <a name="dimensions-tab"></a>Guia Dimensões

Selecione a guia **Dimensões** para exibir valores para todas as dimensões disponíveis para a linha selecionada no momento na guia **Visão geral**, independentemente das dimensões selecionadas para exibição nessa guia.

## <a name="cost-estimate-inquiries"></a>Consultas de previsão de custo

Toda vez que você gera uma estimativa de custo, a estimativa é adicionada à página de consulta **Estimativas de custo**. Para obter detalhes completos sobre como gerar, exibir e trabalhar com estimativas de custo (incluindo estimativas na página de consulta), consulte [Estimar e gerenciar custos de entrega](estimate-manage-landed-costs.md).

## <a name="item-tracking"></a>Acompanhamento de itens

Use a página **Acompanhamento de itens** para exibir linhas de ordens de compra abertas e o status atual. As linhas não precisam ser associadas a uma viagem para aparecerem aqui. No entanto, se um item estiver associado a uma viagem, a linha do registro de acompanhamento de itens mostrará a ID da viagem.

Para abrir esta página, acesse **Custo de entrega \> Consultas \> Acompanhamento \> Acompanhamento de itens**.

Como o sistema provavelmente contém muitas linhas da ordem de compra, a página **Acompanhamento de itens** inicialmente não mostra registros. Comece usando os campos de filtro na parte superior da página para definir o conjunto de linhas de ordem de compra que você está procurando. Selecione **Atualizar** no Painel de Ações para gerar a lista. Você pode usar um asterisco (\*) como um caractere curinga em um dos campos de filtro. Por exemplo, para localizar todas as linhas de ordem de compra para itens que incluam a palavra "DVD" no nome, defina o campo **Tipo** como **Nome do produto** e insira *\*DVD\** no campo **Valor do campo**.

> [!NOTE]
> No momento, as ordens pendentes incluem somente ordens de venda. As cotações de venda não são mostradas ou consideradas ordens pendentes.

A tabela a seguir descreve as colunas na grade na página **Acompanhamento de itens**.

| Coluna | Descrição |
|---|---|
| **Porta de destino** | O destino final. |
| **Confirmada** | A data confirmada da linha da ordem de compra. |
| **Data de Entrega** | A data de entrega da linha da ordem de compra. |
| **Viagem** | Se a linha for associada a uma viagem, a ID da viagem. |
| **Contêiner de Remessa** | Se a linha estiver anexada a um contêiner de remessa, a ID do contêiner. |
| **Porta de remessa** | A porta atual, com base no primeiro trecho do formulário de acompanhamento, em que nenhuma data real é definida para o contêiner de remessa associado à linha da ordem de compra. |
| **Atividade** | A atividade atual, com base no primeiro trecho do formulário de acompanhamento, em que nenhuma data real é definida para o contêiner de remessa associado à linha da ordem de compra. |
| **Data de término estimada** | A data na qual a viagem deve ser recebida no depósito de destino. |
| **Nome** | O nome do fornecedor. |
| **Status da Viagem** | O status de remessa anexado à linha da ordem de compra. |
| **Número do item** | O número de item da linha da ordem de compra. |
| **Externo** | O nome do item do fornecedor. |
| **Nome do Produto** | O nome do item para a linha da ordem de compra. |
| **Quantidade** | A quantidade da linha da ordem de compra para a linha da ordem de compra. |
| **Unidade** | A unidade de medida da linha da ordem de compra. |
| **Referência** | O tipo de ordem (ordem de compra ou ordem de transferência) |
| **Número de referência** | O número da ordem de compra ou o número da ordem de transferência. |
| **Ordem pendente** | Um símbolo indica que há ordens pendentes de venda para o item. |
| (Outras dimensões) | Você pode mostrar colunas para dimensões adicionais, conforme necessário. Essas dimensões incluem o número do lote, o status do estoque e o depósito. No Painel de Ações, selecione **Exibir dimensões** para abrir uma caixa de diálogo na qual é possível selecionar as dimensões a serem incluídas. |

### <a name="related-information-about-backorders"></a>Informações relacionadas sobre ordens pendentes

Para exibir mais informações sobre ordens pendentes, selecione a guia **Informações relacionadas** no lado direito da página e, depois, selecione **Ordens pendentes**. Para exibir ainda mais informações sobre uma ordem pendente específica, selecione a linha e, depois, selecione o link **Mais**.

## <a name="individual-shipping-container-tracking"></a>Acompanhamento do contêiner de remessa individual

A consulta **Acompanhamento do contêiner de remessa individual** fornece um filtro que permite localizar um contêiner de remessa e, em seguida, identificar todas as linhas de viagem nesse contêiner.

Para abrir esta consulta, acesse **Custo de entrega \> Consultas \> Acompanhamento \> Acompanhamento de contêiner de remessa individual**.

## <a name="multiple-shipping-container-tracking"></a>Acompanhamento de vários contêineres de remessa

A consulta **Acompanhamento de vários contêineres de remessa** fornece um filtro que permite localizar uma coleção de contêineres de remessa e, em seguida, identificar todas as linhas de viagem nesses contêineres.

Para abrir esta consulta, acesse **Custo de entrega \> Consultas \> Acompanhamento \> Acompanhamento de vários contêineres de remessa**.

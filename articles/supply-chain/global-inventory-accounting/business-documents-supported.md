---
title: Documentos de negócios compatíveis com a Contabilidade de estoque global
description: Este artigo lista os documentos de negócios que são compatíveis com a Contabilidade de estoque global. Ele também fornece um exemplo detalhado para documentos de ordem de compra.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0dee558de2defa7baae4bc4097c750e974c12a14
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135679"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>Documentos de negócios compatíveis com a Contabilidade de estoque global

[!include [banner](../includes/banner.md)]

Depois que o Complemento Contabilidade de estoque global estiver totalmente configurado, ele estará pronto para processar documentos relacionados ao inventário que são inseridos na Microsoft Dynamics 365 Supply Chain Management.

## <a name="supported-business-documents"></a>Documentos de negócios compatíveis

Há dois tipos de documentos de negócios:

- **Documentos que possuem um diário** – Esses documentos incluem recibo do produto, fatura de compra, guia de remessa e fatura de venda.
- **Documentos que não possuem um diário** – Esses documentos incluem documentos de contagem, movimentação e ajuste de inventário.

Posteriormente neste artigo, as ordens de compra serão usadas como exemplo para ilustrar o processo.

A tabela a seguir lista os documentos que a versão atual permite.

| Tipo de documento      | Documento        |
|--------------------|-----------------|
| Ordem de compra     | Recebimento de produto |
| Ordem de compra     | Fatura         |
| Ordem de venda        | Guia de Remessa    |
| Ordem de venda        | Fatura         |
| Diários de estoque | Movimentação        |
| Diários de estoque | Ajuste      |
| Diários de estoque | Contagem        |
| Diários de estoque | Transferir        |
| Ordem de transferência     | Remessa        |
| Ordem de transferência     | Receber         |

> [!IMPORTANT]
> A Contabilidade de estoque global processa de forma assíncrona os documentos inseridos no Supply Chain Management. Não serão exibidas mensagens de erro para documentos problemáticos.

## <a name="example-purchase-order"></a>Exemplo: ordem de compra

### <a name="product-receipt"></a>Recebimento de produtos

Poste recibos de produtos da maneira comum. Na página **Todas as ordens de compra**, selecione uma ordem de compra e então, no Painel de Ações, na guia **Receber**, selecione **Recebimento de produto** para abrir a página **Diário de recebimento do produto**. Um evento de operação e um evento da Contabilidade de estoque global são gerados para cada linha. Portanto, selecione a guia **Linhas** e selecione **Inventário e \> Eventos e medições** para abrir a página **Eventos e medições**.

A Contabilidade de estoque global é um sistema contábil baseado em eventos e medições. A grade da linha de medição na página **Eventos e medições** mostra uma lista de medições. Cada medição tem uma lista de dimensões.

Para cada evento de operação, existem dois tipos de medição:

- **Medições de operações** – Essas medidas descrevem documentos de negócios em termos genéricos. Uma das medidas é a quantidade do produto que utiliza a unidade de medida que é utilizada no documento. Há também medidas que afetam o valor do inventário, como preço bruto, desconto, percentual de desconto e taxa de linha.
- **Medições contábeis de recursos** – Essas medidas são do ponto de vista do registro de inventário. Eles descrevem o impacto do documento no inventário da unidade de medida do inventário. Se houver vários registros de inventário, existirão várias linhas de medição contábil de recursos.

As dimensões são organizadas da seguinte forma:

- **Dualidade** – Dualidade descreve os agentes que participam dos eventos econômicos. Para documentos comerciais externos, as dimensões individuais descrevem a pessoa jurídica em que o documento é inserido, enquanto as dimensões duplas descrevem o fornecedor, o cliente e assim por diante. Para documentos comerciais internos (por exemplo, ordens de transferência), as dimensões duplas descrevem o depósito de contrapartidas.
- **Tipo de dimensão** – Os tipos de dimensão categorizam as dimensões.
- **Dimensão** – O nome da dimensão.
- **Valor da dimensão** – O valor da dimensão.

### <a name="global-inventory-accounting-event"></a>Evento da Contabilidade de estoque global

A Contabilidade de estoque global considera os eventos operacionais e medições como entrada. Em seguida, ela faz a contabilidade apropriada para cada razão relacionado, com base na moeda e convenção anexadas. Você pode selecionar **Eventos e medições da Contabilidade de estoque global** para exibir o evento da Contabilidade de estoque global. O evento da Contabilidade de estoque global segue a mesma metodologia dos eventos de operação, mas utiliza medições diferentes. Existem três tipos principais de medição: quantidade de custo do produto, custo do produto e variação.

As contas do sub-razão são usadas para classificar ainda mais as medidas. Pode haver vários razões. Esses razões estão vinculados à pessoa jurídica em que o documento é inserido. Você pode visualizar os eventos e medições de cada razão alterando o valor do campo **Razão**.

### <a name="cost-element"></a>Elemento de custo

Com base na política de elemento de custo que está anexada ao razão, o sistema atribui um elemento de custo a cada medição de evento de operação contabilizada que afeta o custo do inventário. Essas medidas incluem preço bruto, desconto, percentual de desconto e taxa de linha.

### <a name="measurement-line-details"></a>Detalhes da linha de medida

A guia **Visão geral** mostra os detalhes das políticas anexadas. As dimensões do objeto de custo mostram o objeto de custo, com base na política de objeto de custo. As dimensões específicas de identificação mostram o número de lote se a suposição de fluxo de custo for *Específico – Lote*.

### <a name="purchase-invoice"></a>Fatura de compra

Poste a fatura da maneira comum. Em seguida, no Painel de Ações, na guia **Fatura**, no grupo **Diários**, selecione **Fatura** para abrir o diário de faturas. Um evento de operação e um evento da Contabilidade de estoque global são gerados para cada linha. Portanto, selecione a guia **Linhas** e selecione **Inventário e \> Eventos e medições** para abrir a página **Eventos e medições**. A página **Eventos e medições** mostra o mesmo tipo de medida. No entanto, como a página mostra uma função de medida e modificador de medida diferente, o impacto no agente (pessoa jurídica) varia.

Selecione **Eventos e medições da Contabilidade de estoque global** para exibir o evento da Contabilidade de estoque global. A quantidade e o custo de inventário agora partem da conta do sub-razão *Inventário de mercadorias recebidas e não faturadas* para a conta do sub-razão *Custo das mercadorias compradas*.

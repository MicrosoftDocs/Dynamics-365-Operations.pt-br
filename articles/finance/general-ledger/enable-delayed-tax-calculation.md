---
title: Habilitar o cálculo de impostos atrasados no diário
description: Este tópico explica como usar o recurso **Habilitar o cálculo de impostos atrasados no diário** para melhorar o desempenho de cálculo de impostos quando o volume de linhas do diário é enorme.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176375"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a>Habilitar o cálculo de impostos atrasados no diário
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como usar o recurso **Habilitar o cálculo de impostos atrasados no diário** para melhorar o desempenho de cálculo de impostos quando o volume de linhas do diário é enorme.

O comportamento atual de cálculo de impostos no diário é acionado em tempo real quando o usuário atualiza campos relacionadas a impostos, por exemplo, o grupo de impostos sobre vendas/grupo de impostos do item. Qualquer atualização em nível de linha do diário recalculará o valor do imposto em todas as linhas do diário. Isso ajuda a usuário a ver o valor do imposto calculado em tempo real, mas também poderá causar problemas de desempenho, se o volume de linhas do diário for muito grande.

Este recurso fornece uma opção para atrasar o cálculo do imposto para resolver o problema de desempenho. Se o recurso estiver ativado, o valor do imposto será calculado somente quando o usuário clicar no comando “Imposto” ou lançar o diário.

O usuário pode ativar/desativar o parâmetro em três níveis:
- Por entidade legal
- Por nome do diário
- Por cabeçalho do diário

O sistema assumirá o valor do parâmetro no cabeçalho do diário como o final. O valor do parâmetro no cabeçalho do diário usará como padrão o nome do diário. O valor do parâmetro no nome de diário usará como padrão o parâmetro de contabilidade quando o nome do diário for criado.

Os campos "Valor real do imposto" e "Valor do imposto calculado" no diário ficarão ocultos se esse parâmetro estiver ativado. O objetivo disso é não confundir o usuário porque o valor desses dois campos sempre mostrará 0, até que o usuário dispare o cálculo do imposto.

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a>Habilitar o cálculo de impostos atrasados por entidade legal

1. Vá para **Contabilidade > Configuração do razão > Parâmetros da contabilidade**.
2. Clique na guia **Imposto**
3. Na Guia Rápida **Geral**, localize o parâmetro **Cálculo de impostos atrasados**, ative-o ou desative-o

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a>Habilitar o cálculo de impostos atrasados por nome do diário

1. Vá para **Contabilidade > Configuração do diário > Nomes de diário**.
2. Na Guia Rápida **Geral**, localize o parâmetro **Cálculo de impostos atrasados**, ative-o ou desative-o

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a>Habilitar o cálculo de impostos atrasados por diário

1. Vá para **Contabilidade > Entradas de diário > Diários gerais**.
2. Clique em **Novo**
3. Selecione um nome de diário
4. Clique em **Configuração**
5. Localize o parâmetro **Cálculo de impostos atrasados**, ative-o ou desative-o

![](media/delayed-tax-calculation-journal-header.png)

---
title: Visão geral de instantâneos (versão preliminar)
description: Este tópico descreve o recurso de instantâneos, que permite salvar uma previsão de fluxo de caixa para análise ou comparação com dados efetivos posteriormente. Ao gerar uma previsão de fluxo de caixa, você poderá salvar essa previsão como um "instantâneo". Em seguida, você pode usar esses instantâneos para editar as contas que foram incluídas na previsão ou comparar a previsão no instantâneo com os valores reais.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: a07749533e84cb26ce59b80e4bde12c96eaf0a3f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009334"
---
# <a name="snapshots-overview-preview"></a>Visão geral de instantâneos (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Os instantâneos permitem que as organizações editem e salvem informações sobre sua posição de caixa e previsões de dinheiro em um ponto no tempo. Você pode comparar o instantâneo com os financeiros reais, examinar a variação e usar essas informações para melhorar as previsões de fluxo de caixa ao longo do tempo. Mais especificamente, os instantâneos podem ser usados das seguintes formas:

- Rastrear a posição de caixa e as previsões de caixa ao longo do tempo.
- Filtre os dados para mostrar um subconjunto de entidades legais para as quais o instantâneo foi criado.
- Edite a posição de caixa e a previsão de caixa geradas pelo sistema.
- Realize a análise hipotética para considerar os modos de exibição otimista, pessimista e mais provável do fluxo de caixa.
- Compare o desempenho financeiro real com a previsão salva no instantâneo.

Você pode criar um instantâneo selecionando **Novo instantâneo** na guia **Posição de caixa** ou na guia **Previsão de caixa** no espaço de trabalho **Previsões de fluxo de caixa**. Depois que um instantâneo é criado, as entradas de caixa e saídas de caixa nele podem ser editadas e salvas. Todos os instantâneos salvos estão disponíveis na guia **Instantâneos**. Para abrir um instantâneo, selecione seu nome.

Os fluxos de entrada e saída de caixa nos instantâneos podem ser editados a qualquer momento. Quando um valor de entrada ou de saída de caixa é editado, o valor atualizado é rateado para as contas de liquidez que fizeram o saldo original. Quando você terminar de editar um instantâneo, selecione **Salvar** para salvar as alterações.

Para comparar vários instantâneos, selecione **Comparar instantâneos**. Você pode comparar dois instantâneos ao mesmo tempo. Selecione os dois instantâneos que devem ser comparados e selecione **OK**. A página **Comparar instantâneo** mostrará uma comparação dos instantâneos selecionados. O gráfico na seção superior da página mostra uma comparação entre as entradas de caixa, as saídas de caixa e os saldos bancários nos períodos sobrepostos entre os dois instantâneos. A grade na seção inferior mostra uma comparação detalhada das duas previsões para cada valor de liquidez. A coluna **Variação** na grade mostra a diferença entre os saldos em um período.

Para comparar os resultados financeiros reais com uma previsão salva como um instantâneo, selecione **Comparar com reais**. A página **Comparar instantâneo** mostrará uma comparação entre os valores reais e a previsão. O gráfico na seção superior da página mostra uma comparação entre as entradas de caixa, as saídas de caixa e os saldos bancários nos períodos sobrepostos entre os dois instantâneos. A grade na seção inferior mostra uma comparação detalhada dos saldos reais por período e o saldo previsto para cada valor de liquidez. A coluna **Variação** na grade mostra a diferença entre o saldo real em um período e o saldo previsto.

#### <a name="privacy-notice"></a>Aviso de privacidade
As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.

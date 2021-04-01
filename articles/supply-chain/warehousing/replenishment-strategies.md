---
title: Estratégias de reabastecimento
description: Este tópico fornece informações sobre estratégias de reabastecimento e explica como você pode usar o campo Estratégia de reabastecimento nas linhas do modelo de reabastecimento de demanda do ciclo para selecionar como o reabastecimento é feito.
author: mirzaab
manager: tfehr
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: a66d48c6636f9f2012c92945868728d8430c1cbe
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256030"
---
# <a name="replenishment-strategies"></a>Estratégias de reabastecimento

[!include [banner](../includes/banner.md)]

Os modelos definidos na página **Modelos de reabastecimento** incluem linhas de modelo de reabastecimento de demanda de ciclo que permitem selecionar como o reabastecimento é feito. Cada linha agora inclui um campo **Estratégia de reabastecimento**.

A estratégia *Quantidade por demanda de ciclos* é a estratégia padrão. É a estratégia de reabastecimento usada antes da introdução do campo **Estratégia de reabastecimento**. Ele usa as diretivas de localização de reabastecimento para localizar locais que podem ser reabastecidos. Em seguida, ele reabastecerá esses locais até que a demanda seja coberta.

A estratégia *Capacidade máxima local* introduz uma nova funcionalidade. Como a estratégia *Quantidade por demanda de ciclos*, essa estratégia usa as diretivas de localização de reabastecimento para encontrar locais que podem ser reabastecidos e reabastecem esses locais até que a demanda seja coberta. Ele difere da estratégia *Quantidade por demanda de ciclos*, pois todos os locais reabastecidos são reabastecidos para sua capacidade máxima, conforme definido pelos limites de estoque do local. A estratégia *Capacidade máxima do local* tenta criar um trabalho para trazer a quantidade solicitada, além de uma quantidade extra, para preencher os locais que estão sendo reabastecidos. No entanto, em alguns casos, essa tentativa poderá falhar. Por exemplo, os locais de massa talvez não tenham estoque suficiente para cobrir a quantidade extra. Nesses casos, o sistema detecta a falha e tenta recuperar.

Pico de época é um exemplo de uma situação em que a estratégia *Capacidade máxima do local* é em comparação à estratégia *Quantidade por demanda de ciclos*. Durante a época de pico, alguns itens podem estar vendendo em alto volume. Portanto, você pode desejar reabastecer proativamente as localizações de separação relevantes o máximo possível para reduzir o número de IDs de trabalho criadas para reabastecimento.

> [!IMPORTANT]
> Para aproveitar totalmente a estratégia *Capacidade máxima local*, você deve redefinir os limites de estoque para os locais relevantes. Caso contrário, essa estratégia funcionará da mesma forma que a estratégia *Quantidade por demanda de ciclo*.

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a>Ativar o reabastecimento para máximo com base no recurso de limites de estoque

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Ativar o reabastecimento para máximo com base nos limites de estoque*

## <a name="set-up-replenishment-strategies"></a>Definir estratégias de reabastecimento

Para acessar os modelos, acesse **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**. Na seção **Visão geral**, selecione ou crie um modelo de reabastecimento de demanda de ondas onde o campo **Tipo de reabastecimento** está definido como *Demanda de ciclo*. Em seguida, configure as linhas do modelo de reabastecimento na seção **Detalhes do modelo de reabastecimento**. Para cada linha, no campo **Estratégia de reabastecimento**, selecione a estratégia de reabastecimento que deseja usar.

![Página de modelos de reabastecimento](media/ReplenTempWaveDmdMaxLocCap.png "Página de modelos de reabastecimento")

Se a coluna **Estratégia de reabastecimento** não aparecer na grade na seção **Detalhes do modelo de reabastecimento**, verifique se o recurso foi ativado e se o modelo de reabastecimento selecionado tem um tipo de reabastecimento *Demanda de ciclo*.

> [!NOTE]
> A estratégia *Quantidade por demanda de ciclos* é a estratégia padrão. Portanto, basta atualizar as linhas do modelo de reabastecimento em que você deseja usar a estratégia *Capacidade máxima local*.

## <a name="example-scenarios"></a>Cenários de exemplo

### <a name="example-1"></a>Exemplo 1

Neste exemplo, há apenas um modelo de reabastecimento que tem apenas uma linha de modelo de reabastecimento.

Você cria uma ordem de venda de 130 peças (pcs) do item A0001. Antes de liberar a ordem para o depósito, o depósito é configurado da seguinte maneira:

- Existe apenas um local de massa e tem 500 pcs de estoque disponível.
- Há três locais de separação, cada qual com um limite de estoque de 100 pcs. (Lembre-se de que os limites de estoque são necessários para a estratégia *Capacidade máxima de local*.)
- O reabastecimento de locais put é o mesmo que os de locais pick de vendas.
- A unidade de reabastecimento é uma caixa (1 caixa = 20 pcs).

No momento da ordem, o seguinte estoque está disponível nos locais de separação de vendas:

- **Grupo-001:** 20 pcs (1 caixa)
- **Grupo-002:** 0 pcs
- **Grupo-003:** 0 pcs

Inicialmente, a estratégia de reabastecimento é definida como *Quantidade de demanda de ciclos*.

Depois que você libera a ordem de venda para o depósito e o processamento de ciclos é executado para o ciclo, você obtém o seguinte trabalho de reabastecimento:

- **Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.
- **Trabalho de reabastecimento 2:** Escolha 2 caixas do local em massa e coloque-as na localização pick-002.

Você obtém duas IDs de trabalho de reabastecimento porque deve reabastecer dois locais e não há suporte para vários lugares.

Se você definir a estratégia de reabastecimento como *Capacidade máxima do local*, obterá o seguinte trabalho de reabastecimento:

- **Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.
- **Trabalho de reabastecimento 2:** Escolha 5 caixas do local em massa e coloque-as na localização pick-002.

[![Exemplo 1](media/ReplenTemp_example_1.png "Exemplo 1")](media/ReplenTemp_example_1_large.png)

### <a name="example-2"></a>Exemplo 2

Este exemplo mostra o que acontece quando o local de massa não tem estoque suficiente para cobrir a quantidade extra. Ele usa o mesmo cenário que o exemplo 1, mas o local de massa tem 160 pcs (8 caixas).

A estratégia *Quantidade por demanda de ciclos* cria o mesmo trabalho feito no exemplo 1.

No entanto, como a estratégia *Capacidade máxima de localização* tenta criar as IDs de trabalho como fazia no exemplo 1, ela pode falhar. Nesse ponto, o sistema tenta recuperar.

Dependendo da configuração da opção **Permitir divisão** nas diretivas de localização para a separação de reabastecimento, dois resultados são possíveis:

- Se a opção **Permitir divisão** estiver definida como *Sim*, o trabalho de reabastecimento a seguir será criado:

    - **Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.
    - **Trabalho de reabastecimento 2:** Escolha 4 caixas do local em massa e coloque-as na localização pick-002.

- Se a opção **Permitir divisão** estiver definida como *Não*, o trabalho de reabastecimento a seguir será criado:

    - **Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.
    - **Trabalho de reabastecimento 2:** Escolha 2 caixas do local em massa e coloque-as na localização pick-002.

Os resultados são diferentes devido às informações disponíveis quando você cria o trabalho. Quando **Permitir divisão** é definida como *Sim* nas diretivas de localização para a separação de reabastecimento, você sabe que gerencia para encontrar 160 pcs. Portanto, você pode criar trabalho para essa quantidade. No entanto, quando a opção **Permitir divisão** está definida como *Não*, você não sabe a existência das 160 pcs. Como a quantidade extra que você decidiu reabastecer era de 3 caixas, você pode soltar essa quantidade extra e tentar a quantidade original novamente.

[![Exemplo 2](media/ReplenTemp_example_2.png "Exemplo 2")](media/ReplenTemp_example_2_large.png)

Portanto, para obter a quantidade máxima para os locais reabastecidos, você deve definir a opção **Permitir divisão** como *Sim* nas diretivas de localização para a separação de reabastecimento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
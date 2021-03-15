---
title: Limites de estoque de localização
description: Este tópico descreve a funcionalidade para limites de estoque de localização.
author: perlynne
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e0adb9d05f0db9bbfe6bfbe72564a4e5e839f163
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004560"
---
# <a name="location-stocking-limits"></a>Limites de estoque de localização

[!include [banner](../includes/banner.md)]

Você pode usar a página **Limites de estoque de localização** (**Gerenciamento de depósito \> Configuração \> Depósito \> Limites de estoque de localização**) para controlar a capacidade de carga em localizações de depósitos sem precisar usar os processos mais avançados para cálculos volumétricos de produtos físicos.

A finalidade dos limites de estoque de localização é avaliar a quantidade máxima que uma localização pode conter. Você pode configurar o recurso em qualquer um dos três níveis, cada um deles tem sua própria guia na página **Limites de estoque de localização**:

- Produtos
- Variantes de produtos
- Tipos de contêiner

Para cada nível, você pode definir valores de campo diferentes. Em seguida, o sistema avaliará a capacidade de uma localização específica, com base nos valores **Quantidade** e **Unidade** de cada linha. Ele selecionará o registro correspondente mais detalhado primeiro. Por exemplo, uma linha com um valor no campo **ID do perfil de localização** será avaliada antes de uma linha com um valor apenas no campo **Depósito**. A capacidade restante também será avaliada, com base no valor **Quantidade** do registro de limite de estoque de localização usado.

Na seção **Produtos** da página, você pode definir os seguintes valores de campo para a pesquisa de limites de estoque de localização:

- Depósito
- ID do perfil de localização
- Localização
- ID da categoria de tamanho do pacote
- Nº de itens
- Unidade

> [!NOTE]
> Não é necessário definir um valor **Unidade** para cada registro de limite de estoque de localização. Os cálculos de capacidade de localização se basearão nas quantidades de unidades de estoque. Se nenhuma conversão de unidades for definida para um valor usado, o registro de limite de estoque de localização será ignorado, como se outro valor **Número de item** fosse definido para ele.

## <a name="example--purchase-order-receiving"></a>Exemplo – Recebimento de ordem de compra

Este exemplo se baseia em um conjunto de dados de demonstração *USMF* limpo, no qual os valores a seguir são definidos na guia **Grades de produtos** da página **Limites de estoque de localização**.

| Depósito | ID do perfil de localização | Nº de itens | Tamanho | Quantidade | Unidade |
|-----------|---------------------|-------------|------|----------|------|
| 24        | FLOOR               | D0013       | S    | 300      | Cada   |
| 24        | FLOOR               | D0013       | L    | 240      | Cada   |
| 24        | FLOOR               | D0013       | S    | 360      | Cada   |

Grades de produtos com unidades de medida diferentes são configuradas para os produtos. Essas grades são alinhadas com os limites de estoque de localização de três paletes (PL):

- **Tamanho M:** 1 PL = 100 cada (Ea)
- **Tamanho G:** 1 PL = 80 Ea
- **Tamanho P:** 1 PL = 120 Ea

Portanto, cada localização em que o valor **ID do perfil de localização** estiver definido como *FLOOR* poderá conter *3* *PL* do número de item *D0013*.

### <a name="prepare-for-the-example"></a>Preparar-se para o exemplo

Neste exemplo, você executará um fluxo de recebimento de ordem de compra para duas linhas. No entanto, primeiro você deve atualizar os dados de demonstração da seguinte maneira para garantir que as localizações permitam o transporte de itens mistos, que somente as localizações vazias de *FL-002* a *FL-004* sejam usadas e que não haja nenhum trabalho de entrada aberto.

1. Para a localização *FL-001*, altere o valor do campo **Perfil de localização** de *FLOOR* para *FLOOR-05*.
1. Para o perfil de localização *FLOOR*, defina a opção **Permitir itens mistos** como *Sim*.
1. Crie uma ordem de compra com as duas linhas a seguir.

    | Depósito | Nº de itens | Tamanho | Quantidade | Unidade |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | S    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>Processar o exemplo

Primeiro, você receberá uma quantidade de *4* da unidade *PL* no tamanho *P* e analisará as localizações das linhas de colocação para o trabalho criado. Depois, você receberá uma quantidade de *4* da unidade *PL* no tamanho *G* e analisará as localizações das linhas de colocação para o trabalho criado.

1. No aplicativo de depósito, entre usando *24* como a ID de usuário e *1* como a senha.
1. Selecione **Entrada** \> **Recebimento de Compra**.
1. Receba *4* *PL* do número de item *D0013* no tamanho *P*.
1. Analise o trabalho de armazenamento que foi criado. Você verá o seguinte resultado:

    - 3 PL -\> FL-002
    - 1 PL -\> FL-003

1. Receba *4* *PL* do número de item *D0013* no tamanho *G*.
1. Analise o trabalho de armazenamento que foi criado. Você verá o seguinte resultado:

    - 1 PL -\> FL-003
    - 3 PL -\> FL-004

Com base nos resultados, você pode concluir que o sistema não alocou as localizações de armazenamento corretas. Caso contrário, por que o sistema adicionou somente *1* *PL* de tamanho *G* à localização *FL-003* na última etapa, não *2* *PL*? Ou seja, por que não há um total de *3* *PL* para armazenamento nessa localização?

Para explicar essa falha aparente, você deve entender os critérios de seleção para os limites de estoque de localização. O sistema seleciona o registro correspondente mais detalhado. Neste exemplo, o registro correspondente mais detalhado é a linha em que o valor **Tamanho** é *G*, o valor **Quantidade** é *240* e o valor **Unidade** é *Ea*. Como você já tem um trabalho em aberto do recebimento anterior de uma quantidade de *120* *Ea* de tamanho *P*, a capacidade restante é calculada como *240* – *120* = *120* *Ea*. Portanto, a capacidade restante pode conter apenas *1* *PL* de *80* *Ea*.

> [!NOTE]
> Não é possível usar limites de estoque de localização para controlar, por exemplo, o reabastecimento de itens com quantidades diferentes na mesma localização. Nesse caso, use um *modelo de reabastecimento*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
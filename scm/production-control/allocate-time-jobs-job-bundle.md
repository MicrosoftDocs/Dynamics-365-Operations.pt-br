---
title: Alocar tempo para trabalhos em um pacote de trabalhos
description: "Em Execução de fabricação, você pode agrupar trabalhos. Você poderá iniciar vários trabalhos ao mesmo tempo na página Lista de trabalhos."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgBundleSlize, JmgProdParameters, JmgRegistration
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 55591
ms.assetid: 358efce7-73c8-4d2a-a7f7-cb99b88ab6ee
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a7d824048c37b69240385644eb15514918f17d9e
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="allocate-time-to-jobs-in-a-job-bundle"></a>Alocar tempo para trabalhos em um pacote de trabalhos

[!include[banner](../includes/banner.md)]


Em Execução de fabricação, você pode agrupar trabalhos. Você poderá iniciar vários trabalhos ao mesmo tempo na página Lista de trabalhos.

Se você agrupar trabalhos, deverá definir como o tempo total registrado para todos os trabalhos deve ser alocado a cada trabalho. Você define a alocação ao selecionar uma das opções a seguir no campo **Tipo de pacote** na página **Chaves de alocação**:

-   **Estimativa** – o tempo é dividido entre os trabalhos com base no tempo estimado para os trabalhos.
-   **trabalhos** – o tempo é dividido de acordo com o total de trabalhos agrupados e o tempo gasto para concluir todos os trabalhos.
-   **Tempo líquido** – o tempo é dividido igualmente entre os trabalhos agrupados a qualquer momento.
-   **Tempo real** – o tempo real do trabalho alocado. O custo pode ser calculado com base no custo real da folha de pagamento. **Observação:** a chave de alocação **Tempo real** só estará disponível se sua empresa usar a funcionalidade de folha de pagamento em Horário e presença.

Os exemplos a seguir mostram os resultados das diversas chaves de alocação.

## <a name="example-scenario"></a>Cenário de exemplo
Três trabalhos contidos na fila de trabalho devem ser concluídos. Inicie o primeiro trabalho e, enquanto ele estiver em andamento, inicie o segundo e o terceiro trabalhos. Consequentemente, há um pacote de três trabalhos. A tabela a seguir mostra o tempo de produção previsto para cada trabalho.

| Cargo   | Tempo de produção |
|-------|-----------------|
| Trabalho 1 | 1 hora          |
| Trabalho 2 | 3 horas         |
| Trabalho 3 | 4 horas         |
| Total | 8 horas         |

A tabela a seguir mostra as horas de trabalho reais gastas em cada trabalho.

| Cargo    | Hora inicial | Hora final | Tempo agrupado |
|--------|------------|----------|-------------|
| Trabalho 1  | 09:00:00      | 11:00:00    | 2 horas     |
| Trabalho 2  | 10:00:00      | 13:00:00    | 3 horas     |
| Trabalho 3  | 10:00:00      | 15:00    | 5 horas     |
| Grupo | 09:00:00      | 15:00    | 6 horas     |

As seções a seguir descrevem os resultados de tempo calculado para cada chave de alocação.

## <a name="estimation-allocation-key"></a>Chave de Alocação da Estimativa
A tabela a seguir ilustra a fórmula para calcular o tempo alocado. Esta é a fórmula: Tempo por trabalho = Tempo total do pacote × (Tempo estimado do trabalho/Tempo estimado total)

| Trabalho   | Fórmula           | Tempo distribuído |
|-------|-------------------|----------------|
| Trabalho 1 | 6 × (1 ÷ 8) horas | 0,75 hora      |
| Trabalho 2 | 6 × (3 ÷ 8) horas | 2,25 horas     |
| Trabalho 3 | 6 × (4 ÷ 8) horas | 3,00 horas     |

## <a name="jobs-allocation-key"></a>Chave de Alocação dos Trabalhos
A tabela a seguir ilustra a fórmula para calcular o tempo alocado. Esta é a fórmula: Tempo por trabalho = Tempo total do pacote ÷ Número de trabalhos

| Trabalho   | Fórmula | Tempo distribuído |
|-------|---------|----------------|
| Trabalho 1 | 6 ÷ 3   | 2 horas        |
| Trabalho 2 | 6 ÷ 3   | 2 horas        |
| Trabalho 3 | 6 ÷ 3   | 2 horas        |

## <a name="net-time-allocation-key"></a>Chave de Alocação do Período Líquido
A tabela a seguir ilustra a fórmula para calcular o tempo alocado. Esta é a fórmula: Tempo calculado por relatório = Tempo do pacote ÷ Número de trabalhos

|                              | 09:00 – 10:00 (1 hora) | 10:00 – 11:00 (1 hora) | 11:00 – 13:00 (2 horas) | 13:00 – 15:00 (2 horas) | Tempo distribuído |
|------------------------------|----------------------|----------------------|-----------------------|-----------------------|----------------|
| Número de trabalhos no grupo | 1                    | 3                    | 2                     | 1                     | Não aplicável |
| Trabalho 1                        | 1 ÷ 1 = 1 hora       | 1 ÷ 3 = 0,33 hora    | Não aplicável        | Não aplicável        | 1,33 hora     |
| Trabalho 2                        | Não aplicável       | 1 ÷ 3 = 0,33 hora    | 2 ÷ 2 = 1 hora        | Não aplicável        | 1,33 hora     |
| Trabalho 3                        | Não aplicável       | 1 ÷ 3 = 0,33 hora    | 2 ÷ 2 = 1 hora        | 2 ÷ 1 = 2 horas       | 3,33 horas     |

## <a name="real-time-allocation-key"></a>Chave de alocação de tempo real
Se desejar que os custos de produção sejam calculados com base no custo real, desmarque a opção **Categoria de custo** na página **Padrões da ordem de produção**. A tabela a seguir ilustra a fórmula para calcular o tempo alocado. Esta é a fórmula: Tempo real por trabalho = Tempo real no pacote

| Trabalho   | Hora atual |
|-------|-------------|
| Trabalho 1 | 2 horas     |
| Trabalho 2 | 3 horas     |
| Trabalho 3 | 5 horas     |

Considere os três trabalhos executados por um trabalhador com um salário por hora de BRL 12,00. Não foram recebidos bônus de hora extra nem prêmios no tempo gasto nos trabalhos. O trabalhador trabalhou nos três trabalhos agrupados por um total de seis horas. Consequentemente, o custo de salário é 6 × BRL 12,00 = BRL 72,00. Quando você usa a alocação de tempo real, o custo por hora é recalculado com o fator da fórmula Tempo líquido. Em seguida, o tempo real gasto em cada trabalho é transferido junto com o preço de custo corrigido por hora. No exemplo, são gastas seis horas, embora haja 10 alocadas. A tabela a seguir ilustra a fórmula para calcular o custo. Esta é a fórmula: Custo por hora = (Tempo total agrupado por trabalho (Tempo líquido) ÷ Tempo real por trabalho) × Preço de custo padrão por hora

| Trabalho   | Cálculo do custo corrigido por hora | Custo corrigido por hora | Tempo distribuído | Custo total do trabalho |
|-------|----------------------------------------|-------------------------|----------------|-------------------|
| Trabalho 1 | (1,33 ÷ 2) × BRL 12,00                 | USD 8,00                | 2 horas        | USD 16,00         |
| Trabalho 2 | (1,33 ÷ 3) × BRL 12,00                 | USD 5,33                | 3 horas        | USD 16,00         |
| Trabalho 3 | (3,33 ÷ 5) × BRL 12,00                 | USD 8,00                | 5 horas        | USD 40,00         |

O custo corrigido por hora e o tempo de trabalho são lançados em um diário de produção. **Observação:** se você selecionar a opção **Categoria de custo** na guia **Geral** da página **Padrões da ordem de produção**, o tempo real de cada trabalho será transferido para um diário de produção em que os custos serão aplicados à categoria de custo do trabalho específico.





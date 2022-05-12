---
title: Cobrança de assinatura de conteúdo do Power BI
description: Este tópico descreve o que está incluído na cobrança de assinatura do conteúdo do Microsoft Power BI.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-04-13
ms.openlocfilehash: fad96bdaf60e7772e9ea1ff937435b0274303505
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645383"
---
# <a name="subscription-billing-power-bi-content"></a>Cobrança de assinatura de conteúdo do Power BI

[!include[banner](../includes/banner.md)]

Este tópico descreve o que está incluído na cobrança de assinatura do conteúdo do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo. 

## <a name="overview"></a>Visão geral

A cobrança de assinatura do conteúdo do Power BI foi criada para auxiliares e gerentes de cobrança de assinatura. Ela fornece métricas importantes da cobrança de assinatura, como a receita recorrente mensal (MRR) para agendas de cobrança e o saldo decrescente e informações em cascata para agendas de adiamento. Ela usa os dados das agendas de cobrança e das agendas de adiamento para fornecer uma visão geral do rendimento e da receita recorrentes.

O conteúdo do Power BI tem as três guias a seguir, que fornecem um total de quatro relatórios analíticos: 

- **Análise – MRR** – essa guia fornece o relatório de **Cobrança recorrente mensal** e o relatório **Detalhes da agenda de cobrança**.
- **Análise – Cascata** – essa guia fornece o relatório de **Receita em cascata**.
- **Análise – Saldo decrescente** – essa guia fornece o relatório de **Saldo decrescente**.

## <a name="view-data-on-the-analytical-reports"></a>Exibir dados nos relatórios analíticos

Antes de poder exibir dados nos relatórios analíticos, você deve executar um processo periódico que gera os dados de relatório para cada relatório. Esses dados exigidos pelos relatórios devem ser gerados porque não são armazenados diretamente no banco de dados. 

1. Acesse **Cobrança de assinatura \> Cobrança de contrato recorrente \> Tarefas periódicas \> Processamento em lotes de relatório analítico de MRR** e siga estas etapas:

    1. Insira um intervalo de datas de, no máximo, três anos.
    2. Opcional: configure um trabalho recorrente de processamento em lote para atualizar periodicamente os dados.
    3. Selecione **OK**.

2. Depois que o trabalho em lote for concluído, acesse **Administração do sistema \> Configuração \> Repositório de Entidades** e atualize a medição agregada de **Relatório de MRR**. 
3. Acesse **Cobrança de assinatura \> Adiamentos de receita e despesa \> Tarefas periódicas \> Processamento em lotes de relatório analítico em cascata** e siga estas etapas:

    1. Insira uma data de início e uma data de término que não ultrapassem 26 períodos. 
    2. Se desejar exibir o valor previsto dos períodos passados no período atual, defina a opção **Prever valores passados no período atual** como **Sim**.
    3. Opcional: configure um trabalho recorrente de processamento em lote para atualizar periodicamente os dados.
    4. Selecione **OK**. 

4. Depois que o trabalho em lote for concluído, acesse **Administração do sistema \> Configuração \> Repositório de Entidades** e atualize a medição agregada de **Relatório em cascata**.
5. Acesse **Cobrança de assinatura \> Adiamentos de receita e despesa \> Tarefas periódicas \> Processamento em lotes de relatório analítico de saldo decrescente** e siga estas etapas:

    1. Insira uma data de início e uma data de término que não ultrapassem 26 períodos. 
    2. Se desejar exibir o valor previsto dos períodos passados no período atual, defina a opção **Prever valores passados no período atual** como **Sim**.
    3. Opcional: configure um trabalho recorrente de processamento em lote para atualizar periodicamente os dados.
    4. Selecione **OK**.

6. Depois que o trabalho em lote for concluído, acesse **Administração do sistema \> Configuração \> Repositório de Entidades** e atualize a medição agregada de **Relatório de saldo decrescente**.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI

A cobrança de assinatura de conteúdo do Power BI é exibida no espaço de trabalho **Cobrança de assinatura**.

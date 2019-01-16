---
title: Demonstrativos de varejo
description: "Este tópico descreve como os demonstrativos são criados e lançados."
author: ashishmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 9e88a8b22b73aca5c2cee6984ecad3c62e597102
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---

# <a name="retail-statements"></a>Demonstrativos de varejo

[!include [banner](includes/banner.md)]

No Microsoft Dynamics 365 for Retail, o processo de lançamento de demonstrativo é usado para registrar contabilmente as transações que ocorrem no ponto de venda (PDV) da nuvem ou Modern POS (MPOS). O processos de lançamentos de demonstrativos usa a agenda de distribuição para receber um conjunto de transações PDV no cliente das sedes (HQ). Os parâmetros definidos nas páginas **Parâmetros de varejo** e **Lojas** são usados para selecionar as transações que são recebidas em demonstrativos individuais.

A ilustração a seguir mostra o processo de lançamento do demonstrativo. Nesse processo, as transações que são registradas no PDV são transmitidas para o cliente usando o agendador do Retail. Depois que o cliente receber as transações, você poderá criar, calcular e lançar o demonstrativo de transação para a loja.

[![Processo de lançamento de demonstrativo](./media/retail-statements.png)](./media/retail-statements.png)

## <a name="creating-and-posting-statements"></a>Criação e lançamento de demonstrativos

Você pode criar um demonstrativo manualmente ou usar os processos em lote que você configurou para serem executados periodicamente ao longo do dia. Nos dois casos, as etapas a seguir são usadas para criar e lançar demonstrativos.

### <a name="create-the-statement"></a>Criar o demonstrativo

Esta etapa identifica a loja onde o demonstrativo foi criado manualmente. Se você configurar um processo em lote, poderá criar automaticamente demonstrativos para todas as lojas com base em uma agenda definida.

### <a name="calculate-the-statement"></a>Calcular o demonstrativo

Nesta etapa, as linhas de transação são selecionadas com base nos critérios definidos para cada loja nas páginas **Parâmetros de varejo** e **Lojas**. Nestas páginas, você define os critérios e especifica como as transações são calculadas. Para exibir uma lista de transações que são incluídas no demonstrativo antes de calculá-lo, use a página **Transações**.

O cálculo do demonstrativo usa declarações da proposta dos terminais de acordo com o valor contado. Como alternativa, você poderá inserir manualmente o valor contato. O demonstrativo mostra a diferença entre o valor de venda das transações e o valor real contado em todos os métodos de pagamento. O demonstrativo será lançado apenas se a diferença for menor do que a diferença máxima de lançamento definida para a loja.

> [!NOTE]
> O processo de cálculo do demonstrativo usa a sequência numérica global.

Quando você calcula um demonstrativo, o cálculo inclui as tarefas a seguir:

- Para o intervalo de datas selecionado, marque as transações que não foram incluídas em um cálculo de demonstrativo anterior.
- Calcule os valores totais que foram propostos nas transações selecionadas. Os resultados são exibidos nas linhas do demonstrativo, dependendo do método do demonstrativo:

    - Se o método do demonstrativo for **Total**, será criada uma linha para cada método de pagamento nas transações selecionadas.
    - Se o método do demonstrativo for **Equipe**, será criada uma linha para cada método de pagamento nas transações realizadas pelo membro da equipe selecionado.
    - Se o método de demonstrativo for **Terminal de PDV**, será criada uma linha para método de pagamento nas transações realizadas no terminal selecionado.
    - Se o método de demonstrativo for **Turno**, será criada uma linha para método de pagamento nas transações realizadas durante um turno.

Se a caixa de seleção **Método Dividir por Demonstrativo** estiver marcada na página **Lojas**, uma instrução separada é criada com base no valor selecionado no campo **Método de demonstrativo**.

Se as horas de operação da loja se estenderam após a meia-noite, você pode configurar lançamento de demonstrativos com base no final do dia útil, em vez de no final do dia do calendário.

Na página **Lojas**, na Guia Rápida **Demonstrativo/fechamento**, no campo **Fim do dia útil**, insira a hora em que a última transação deve ser registrada para ser incluída no demonstrativo do dia útil. Marque a caixa de seleção **Lançar como dia útil** para lançar as transações dentro do mesmo dia útil. Quando o demonstrativo é lançado, as transações que são registradas no mesmo dia útil podem ser incluídas na mesma ordem de venda, mesmo que algumas transações ocorram antes e outras depois da meia-noite.

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a>Exemplo: lançar um demonstrativo para um dia útil que se estenda sobre dois dias do calendário

Uma loja é aberta entre 8:00 e 3:00 e a caixa de seleção **Lançar como dia útil** é marcada na configuração da loja. Em 31 de maio, a loja registra transações entre 8:00 e meia-noite. A loja também registra transações entre 12:01 e 3:00 em 1º de junho.

Quando a loja lança seu demonstrativo para o fechamento do dia útil, a ordem de venda que é gerada inclui todas as transações que foram registradas entre 8:00 e 3:00h, mesmo que as transações tenham ocorrido em dois dias, 31 de maio e 1° de junho.

Se a caixa de seleção **Lançar como dia útil** for desmarcada para a mesma loja, as ordens de venda separada são geradas quando a loja lança seu demonstrativo para o fechamento do dia útil. Uma ordem de venda inclui as transações que foram registradas entre os horários 8:00 e a meia-noite de 31 de maio, e a segunda ordem de venda inclui transações que foram registradas entre 12:01 e 3:00 de 1º de junho do horário comercial.

> [!NOTE]
> Antes de criar demonstrativos, você deve fechar os turnos no período do demonstrativo.

### <a name="post-the-statement"></a>Lançar o demonstrativo

Quando você lançar um demonstrativo, as ordens de venda e faturas são criadas para as vendas de varejo no demonstrativo.

- As vendas à vista e realizadas são agregadas em ordens de venda e são faturadas para o cliente padrão que está atribuído à loja.
- As vendas de varejo para as quais um cliente foi adicionado à transação no Microsoft Dynamics 365 for Retail POS geram ordens de venda e faturas separadas, uma para cada cliente exclusivo.

Os diários de pagamentos são criados automaticamente para os pagamentos no demonstrativo e o estoque é atualizado para a loja POS.


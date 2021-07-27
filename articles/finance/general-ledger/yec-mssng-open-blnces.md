---
title: Saldos iniciais ausentes do fechamento do exercício
description: Este tópico explica por que os saldos iniciais podem estar ausentes no fechamento de um exercício e como recriar esses saldos, se eles estiverem ausentes.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4bebf35a8959d4f72d46d4b40e5487f499b2756d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356643"
---
# <a name="year-end-close-missing-opening-balances"></a>Saldos iniciais ausentes do fechamento do exercício

[!include [banner](../includes/banner.md)]

Este tópico explica por que os saldos iniciais podem estar ausentes no fechamento de um exercício e como recriar esses saldos, se eles estiverem ausentes.

### <a name="symptom"></a>Sintoma

Por que não há saldos iniciais após a execução do fechamento do exercício da Contabilidade? 

### <a name="resolution"></a>Resolução

Veja os itens que devem ser verificados se você tiver fechado um exercício na Contabilidade e, em seguida, gerado um balancete que não exibe os saldos iniciais para o próximo ano fiscal.

Se o campo **Desfazer fechamento anterior** estiver definido como **Sim**, o fechamento do exercício anterior para o mesmo ano fiscal será revertido. Ao executar um processo para reverter o fechamento do exercício, todas as entradas de saldo de fechamento e de saldo inicial serão excluídas, como se o fechamento do exercício nunca tivesse sido executado. Os comprovantes também serão excluídos. O processo de fechamento do exercício não será executado de forma automática novamente. Você deverá iniciar o processo novamente, desta vez atualizando a opção **Desfazer fechamento anterior** para **Não**.

Esse cenário é abordado no tópico Perguntas frequentes sobre fechamento do exercício. Para obter mais informações, consulte [Perguntas frequentes sobre fechamento do exercício](faq-year-end-activities.md).

### <a name="symptom"></a>Sintoma

Executei o fechamento do exercício com a opção **Desfazer fechamento anterior** definida como **Não** e ainda não tenho saldos iniciais para meu ano fiscal.

### <a name="resolution"></a>Resolução

Primeiramente, verifique o status do trabalho em lote. O fechamento de um exercício inclui várias tarefas separadas, mas a etapa mais importante é a tarefa em lote com a etapa de descrição **Tarefa 5.0.0**. O lançamento das transações de abertura e, opcionalmente, das transações de fechamento na Contabilidade ocorre durante essa etapa. 

[![Lista de histórico de lotes.](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

Se essa etapa foi concluída com êxito, mas você não vê os saldos iniciais na página **Consulta de balancete** (**Contabilidade > Consultas e relatórios > Balancete**), examine os resultados do trabalho em lotes do fechamento do exercício para ver se a etapa Recriar saldos foi concluída com êxito.

[![Resultados do trabalho em lotes do fechamento do exercício.](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

Se houve falha nessa etapa por algum motivo, provavelmente as transações de abertura (e opcionalmente as de fechamento) foram lançadas com êxito. É possível verificar se as transações da Contabilidade foram lançadas com êxito usando a página **Consulta de transações de comprovante** especificando o número do comprovante e a data fornecidos na caixa de diálogo de fechamento do exercício para o exercício fechado, (**Contabilidade > Consultas e relatórios > Transações de comprovante**).

[![Consulta de transações de comprovante.](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

Se os comprovantes de abertura (e, opcionalmente, de fechamento) estiverem presentes, não será necessário executar o fechamento do exercício novamente. Em vez disso, consulte a próxima seção para obter mais informações sobre como avançar.

### <a name="symptom"></a>Sintoma

Há falha na etapa "Recriar saldos" no fechamento do exercício. Devo executar novamente o processo inteiro de fechamento do exercício?

### <a name="resolution"></a>Resolução

A etapa Recriar saldos atualiza os saldos da Contabilidade usados quando a Consulta de balancete é gerada.  É a etapa final do processo de fechamento do exercício.  Se essa etapa for a única etapa com falha, as transações da Contabilidade foram lançadas com êxito.  Não será necessário executar o fechamento do exercício novamente. Você pode executar o processo para recriar os saldos manualmente usando a página **Conjuntos de dimensões financeiras** (**Contabilidade > Plano de contas > Dimensões > Conjuntos de dimensões financeiras**).

[![Botão Recriar saldos na página Conjuntos de dimensões financeiras.](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

Se essa etapa levar muito tempo para ser processada, recomendamos que você examine as práticas recomendadas para conjuntos de dimensões financeiras, conforme descrito em [Práticas recomendadas para atualizar Conjuntos de dimensões financeiras](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets). 


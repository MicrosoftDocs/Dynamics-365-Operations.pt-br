---
title: "Reavaliação de moeda estrangeira para Contas a pagar e Contas a receber"
description: "As flutuações nas taxas de câmbio fazem com que o valor teórico (valor contábil) de transações abertas em moedas estrangeiras varie ao longo do tempo. Este artigo oferece informações sobre o processo de reavaliação de moeda estrangeira executado para atualizar o valor de transação abertas em Contas a pagar e em Contas a receber."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: adb1f7a2d709b607c3065f4c2fb4d24cb4849ec1
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="foreign-currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>Reavaliação de moeda estrangeira para Contas a pagar e Contas a receber

[!include[banner](../includes/banner.md)]


As flutuações nas taxas de câmbio fazem com que o valor teórico (valor contábil) de transações abertas em moedas estrangeiras varie ao longo do tempo. Este artigo oferece informações sobre o processo de reavaliação de moeda estrangeira executado para atualizar o valor de transação abertas em Contas a pagar e em Contas a receber. 

O valor teórico, ou valor contábil, de transações de fornecedor abertas em moedas estrangeiras varia ao longo do tempo por causa de flutuações em taxas de câmbio. Para atualizar o valor de transação abertas em Contas a pagar e em Contas a receber, execute o processo de reavaliação de moeda estrangeira. A reavaliação de moeda estrangeira pode ser executada para Contas a pagar e Contas a receber. O processo usa uma nova taxa de câmbio para reavaliar valores abertos, ou valores não liquidados, em uma data especificada. As diferenças entre as quantias originais lançadas e as quantias reavaliadas causarão lucro ou perda não realizada para cada transação aberta. Os sub-razões de Contas a pagar e de Contas a receber são então atualizados para refletirem o lucro ou a perda não realizado, e uma entrada contábil é lançada na Contabilidade.

## <a name="simulate-a-foreign-currency-revaluation"></a>Simular uma reavaliação de moeda estrangeira
Antes que você reavalie valores em moeda estrangeira em transações de cliente abertas para uma data específica, é possível executar um relatório da reavaliação em moeda estrangeira para a mesma data e método. Para executar o relatório de simulação, na página **Reavaliação de moeda estrangeira**, clique no botão **Simulação**. O relatório fornece uma visualização do valor do lucro ou da perda não realizado nos parâmetros definidos para a simulação.

## <a name="process-a-foreign-currency-revaluation"></a>Processar uma reavaliação de moeda estrangeira
Use a página **Reavaliação de moeda estrangeira** nas **Tarefas periódicas** para reavaliar as transações abertas. Você pode executar o processo em tempo real ou agendá-lo para execução usando um lote. Quando você definir as configurações para o processo de reavaliação, verifique se deseja imprimir um relatório dos resultados O relatório de reavaliação não pode ser reimpresso depois que o processo for concluído. Se você gerar o relatório de reavaliação de moeda estrangeira, ele mostrará vários saldos no nível do cliente/fornecedor e no nível da moeda:

-   Os saldos de clientes ou de fornecedores com transações de moeda estrangeira que foram reavaliados. Os saldos a seguir são mostrados:
    -   O saldo total original na moeda estrangeira.
    -   O valor total de moeda estrangeira na moeda contábil como na reavaliação anterior.
    -   O valor total de moeda estrangeira na moeda contábil como na reavaliação atual.
    -   A diferença entre a reavaliação anterior e atual. Essa diferença é o lucro ou a perda não realizado adicional.
-   O lucro ou a perda não realizado total para cada moeda.

Um registro é mantido sempre que você execute uma reavaliação de moeda estrangeira. No registro da página **Avaliação de moeda estrangeira**, selecione **Transações** para exibir a lista detalhada de transações criadas por causa da reavaliação. Cada transação de comprovante representa a transação aberta que foi reavaliada. Se uma transação aberta tiver sido reavaliada mais de uma vez, você verá dois registros que usam o mesmo comprovante. Um registro será para reversão de lucro ou perda não realizado anterior, e outro registro será para o novo lucro ou perda não realizado. Para executar o processo de reavaliação, clique no botão **Reavaliação de moeda estrangeira**. Defina as configurações apropriadas para os seguintes parâmetros:

-   **Método** – o método usado no trabalho de reavaliação de moeda estrangeira selecionado:
    -   **Padrão** – os trabalhos de reavaliação de moeda estrangeira são lançados independentemente de o resultado ser lucro ou perda.
    -   **Mínimo**– os trabalhos de reavaliação de moeda estrangeira só serão lançados se o resultado for uma perda.
    -   **Data da fatura** – os trabalhos de reavaliação de moeda estrangeira usam a taxa de câmbio original das transações, que são reavaliadas para seu valor original na moeda contábil. O efeito de qualquer reavaliação de moeda estrangeira prévia é cancelado.
-   **Data considerada** – a data em que todas as transações que possuem valores em aberto (não liquidados) nessa data são encontradas. Os valores de moeda estrangeira são reavaliados usando as taxas de câmbio inseridas na página **Taxas de câmbio de moeda** para a data considerada. Quando os valores de moeda estrangeira são reavaliados em uma data específica, essa data será a data da última de reavaliação em moeda estrangeira para as transações ajustadas. Se você decidir executar uma reavaliação de moeda estrangeira para uma data específica que seja anterior à data da última reavaliação de moeda estrangeira em transações que já tenham sido ajustadas, o trabalho periódico não ajustará as transações que estiverem em aberto na data específica anterior, mas que tiverem uma data mais recente para a reavaliação de moeda estrangeira não serão ajustadas pelo trabalho periódico.
-   **Data da taxa** – a data que determina a taxa de câmbio usada na reavaliação de moeda estrangeira.
-   **Usar o perfil de lançamentos de** – o perfil de lançamento usado para inserir a conta principal padrão para Contas a receber ou Contas a pagar para as entradas contábeis das transações de reavaliação de moeda estrangeira:
    -   **Lançamento** – o perfil de lançamento da transação do cliente é usado.
    -   **Selecionar** - insira o perfil de lançamento no campo **Perfil de lançamento**.
-   **Perfil de lançamento** – Se **Selecionar** estiver escolhido no campo **Usar perfil de lançamentos de**, o perfil de lançamento inserido nesse campo determinará o perfil de lançamento das transações de reavaliação de moeda estrangeira.
-   **Dimensões financeiras** – as dimensões financeiras lançadas nas entradas contábeis das transações de reavaliação de moeda estrangeira:
    -   **Nenhuma** – nenhuma dimensão financeira é lançada. Se você tiver uma dimensão financeira exigida na estrutura da conta, o processo de reavaliação ainda será executado e criará as entradas contábeis sem dimensões financeiras. Você receberá uma mensagem de aviso primeiro para depois poder cancelar a reavaliação.
    -   **Tabela** – as dimensões financeiras da conta do cliente ou na conta do fornecedor são lançadas nas transações de reavaliação de moeda estrangeira.
    -   **Lançamento** – as dimensões financeiras da transação que estão sendo reavaliadas são lançadas nas transações de reavaliação de moeda estrangeira. Por padrão, as dimensões financeiras da conta contábil AR/AP da transação original serão usadas para a conta principal AR/AP da transação de reavaliação, e as dimensões financeiras da conta contábil de despesa/ativo/receita da transação original serão usadas para a conta principal de lucros/perdas não realizados da transação de reavaliação.






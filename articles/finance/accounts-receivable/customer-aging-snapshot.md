---
title: 'Instantâneo de classificação por vencimento de cliente '
description: Este artigo fornece informações sobre os instantâneos de classificação por vencimento de cliente. Um instantâneo de classificação por vencimento calcula os saldos classificados por vencimento de um grupo de clientes em determinado momento.
author: JodiChristiansen
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: e4ccc8ac9b5374ca0713167a17b8704727c687fd
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775227"
---
# <a name="customer-aging-snapshots"></a>Instantâneo de classificação por vencimento de cliente 

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre os instantâneos de classificação por vencimento de cliente. Um instantâneo de classificação por vencimento calcula os saldos classificados por vencimento de um grupo de clientes em determinado momento. Você pode criar registros de instantâneos de classificação por vencimento para todos os clientes ou para os clientes de um grupo de clientes.

As informações dos instantâneos de classificação por vencimento aparecem na página de listagem **Saldos classificados por vencimento** e na página **Cobranças**. Você deve criar um instantâneo de classificação por vencimento antes de usar a página de listagem **Saldos classificados por vencimento**. A página de listagem lista somente clientes para os quais um instantâneo de classificação por vencimento foi criado.

O espaço de trabalho **Crédito e cobranças de clientes** também mostra a classificação por vencimento do cliente. Para obter mais informações, consulte [Conteúdo de gerenciamento de crédito e cobrança do Power BI](credit-collections-power-bi.md).

> [!NOTE]
> Para ajudar a reduzir o tempo necessário para criar um instantâneo de classificação por vencimento, ative os seguintes recursos no espaço de trabalho **Gerenciamento de recursos**: 
> - **Aprimoramento do desempenho de classificação por vencimento de cliente** 
> - **Desempenho de classificação por vencimento do cliente com pools de clientes**  
>Com os dois recursos ativados, é possível usar **Grupos de clientes** ao criar o instantâneo de classificação por vencimento. 

Ao criar um instantâneo de classificação por vencimento de cliente, use os campos a seguir para inserir informações sobre ele:

- No campo **Definição do período de classificação por vencimento**, selecione a definição do período de classificação para o instantâneo de classificação por vencimento. Você pode ter um instantâneo de classificação por vencimento para cada definição do período de classificação por vencimento. O instantâneo de classificação por vencimento e a definição do período de classificação por vencimento devem ser criados separadamente.
- **ID do Grupo** – Esse campo é opcional. Você pode usar um grupo para definir o conjunto de clientes que deve ser processado no instantâneo de classificação por vencimento. Se você selecionar um grupo de clientes neste campo, um instantâneo de classificação por vencimento será criado somente para as contas de cliente que fazem parte desse grupo de clientes. O grupo de clientes selecionado deve ser do tipo **Instantâneo de classificação por vencimento**. Se você deixar este campo em branco, será criado um instantâneo de classificação por vencimento para todas as contas de cliente.


- **Critérios** – o instantâneo de classificação por vencimento terá a duração com base na data selecionada:

    - **Data da transação** – Cada transação terá o vencimento com base na data da transação.
    - **Data de conclusão** – Cada transação terá o vencimento com base em sua data de conclusão.
    - **Data do documento** – Cada transação terá o vencimento com base na data do documento.

- **Classificação por vencimento a partir de** – Selecione a data a ser usada no campo **Data atual** do instantâneo de classificação por vencimento. Os períodos de classificação por vencimento são então calculados com base nessa data. 

    - **Data de hoje** – Usar a data do sistema. Selecione essa opção se o processo estiver configurado para ser executado em um lote recorrente. Em seguida, toda vez que o lote for executado, a data de sistema dessa execução será usada.
    - **Data selecionada** – Use uma data que você especificar. Se você selecionar esta opção, você também deve inserir uma data de classificação por vencimento.

   Por exemplo, o período de classificação por vencimento atual é 30 dias. Se você selecionar **Data de hoje** neste campo, o período de classificação por vencimento atual começará na data de hoje e incluirá os 29 dias anteriores. Se você selecionar **Data selecionada** e informar uma data, o período de classificação por vencimento começará na data especificada e incluirá os 29 dias anteriores.

- **Atualizar status de cobrança** – Defina esta opção como **Sim** para atualizar o status da coleção de transações na página **Cobranças** de **Promessa de pagamento** para **Promessa de pagamento quebrada**, se a data de vencimento for posterior à data no campo **Data da promessa de pagamento**. Defina esta opção como **Não** para deixar o status da cobrança inalterado na página **Cobranças**.
- **Incluir clientes com saldo zero** – Defina esta opção como **Sim** para incluir todos os clientes, independentemente de seu saldo. Se você incluir todos os clientes, recomendamos ativar os recursos **Aumento de desempenho de classificação por vencimento do cliente** e **Aumento de desempenho de classificação por vencimento do cliente com grupos de clientes**. Defina esta opção como **Não** para incluir somente clientes que tenham um saldo. Essa configuração ajudará a melhorar o desempenho, pois os clientes que não tiverem saldo serão ignorados.
- **Ignorar cálculos de limite de crédito durante a classificação por vencimento** - se esta opção for definida como **Sim**, o processo de classificação por vencimento não recalculará o valor do **subtotal da guia de remessa**, o valor do **subtotal da ordem em aberto** e o **crédito disponível** para cada cliente. Esses saldos são mostrados na página **Saldos antigos**, na FactBox em **Limite de crédito**. Para obter melhor desempenho durante o processo de envelhecimento, defina essa opção como **Sim**. Defina como **Não** para recalcular os saldos ao executar o processo de classificação por vencimento. 
- **Intervalo da empresa** – Na guia **Intervalo da empresa**, selecione as entidades legais (empresas) a serem incluídas no instantâneo de classificação por vencimento. Somente as entidades legais configuradas para pagamentos centralizados estão disponíveis para seleção. As transações das entidades legais selecionadas serão então incluídas nos períodos de classificação por vencimento para clientes que têm a mesma ID de participante em todas as entidades legais. Os valores de moeda são convertidos para a moeda da entidade legal que você efetuou logon quando criou o instantâneo de classificação por vencimento.

Recomendamos que você agende esse processo para ser executado em um lote.

> [!NOTE]
> Para ajudar a melhorar o desempenho de lotes quando os instantâneos de classificação por vencimento são criados, insira um número no campo **Número máximo de tarefas em lote** na FastTab **Padrões de cobranças** na guia **Cobranças** da página **Parâmetros de contas a receber**. No campo **Classificar saldos de cliente por vencimento**, recomendamos que você comece com um valor entre **12** e **20** e, em seguida, ajuste o valor para otimizar o processamento de acordo com o seu caso. Não recomendamos definir esse valor como maior que **30**, pois isso afetará o desempenho. 


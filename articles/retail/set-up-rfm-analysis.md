---
title: "Configurar análise RFM"
description: "Este tópico explica como configurar uma análise Recente, Frequência, e Monetária (RFM) dos clientes."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRRFMDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: e66208ccceb4c248c2704bb7358d77447e032205
ms.openlocfilehash: c59d12c54563b883ae6d8ea8594f423f02797f4f
ms.contentlocale: pt-br
ms.lasthandoff: 12/14/2017

---

# <a name="set-up-rfm-analysis"></a>Configurar análise RFM

[!include[banner](includes/banner.md)]


Este tópico explica como configurar uma análise Recente, Frequência, e Monetária (RFM) dos clientes.

A análise RFM (recency, frequência e monetária) é uma ferramenta de marketing que a organização pode usar para avaliar os dados gerados pelas compras dos clientes. Depois de configurar a análise RFM, os clientes são atribuídos a uma contagem de RFM calculada quando eles fazem compras. A contagem de RFM pode ser uma previsão de três dígitos ou um número agregado, dependendo de como sua organização configurou a análise RFM. Veja como a classificação funciona, se a organização usar uma classificação de três dígitos para contagem:

- O primeiro dígito é a classificação de recency do cliente, que é como o cliente fez uma compra recentemente na sua organização. 
- O segundo dígito é a classificação de frequência do cliente, que é a frequência em que o cliente faz compras na sua organização. 
- O terceiro dígito é uma classificação monetária do cliente, que é quanto o cliente gasta quando faz compras na sua organização. 

Por exemplo, a organização definiu as classificações em uma escala de 1 a 5, em que 5 representa a classificação mais alta. Nesse caso, a classificação 535 fornece a você as seguintes informações sobre o cliente:

-   **Classificação de recency 5** – O cliente fez uma compra recentemente.
-   **Classificação de frequência 3** – O cliente compra produtos da sua organização com frequência moderada.
-   **Classificação monetária 5** – Quando o cliente faz uma compra, ele gasta um montante significativo.

Se sua organização usar um número agregado para a pontuação, as classificações individuais serão adicionadas juntas. No mesmo exemplo, o cliente obtém a classificação 13 (5 + 3 + 5).

## <a name="to-set-up-rfm-analysis-for-the-customers-in-your-organization"></a>Para configurar a análise de RFM para clientes de sua organização.

1.  Vá para **Call center** > **Periódico** > **Análise de RFM**.

2.  Na página **Análise de RFM**, selecione **Novo**. No campo **Definição de RFM**, insira um nome para a definição de RFM. Por exemplo, seria possível chamar a definição de RFM-A.

3.  Insira uma data inicial e uma data final para a definição de RFM.

4.  Na Guia Rápida **Geral**, faça o seguinte: 
    - Se cada seção de pontuação de RFM contiver uma contagem igual de clientes, marque a caixa de seleção **Distribuição por igual**. 
    - Marque a caixa de seleção **Adicionar pontuações** para agregar as três pontuações. Por exemplo, isso forneceria a um cliente uma pontuação de RFM de 13, em vez de 535. 
    - Marque a caixa de seleção **Salvar histórico** para exigir que o sistema salve os dados estatísticos para clientes, de forma que seja possível usar os dados para calcular a pontuação de RFM.
  
5.  Na Guia Rápida **Recency**, faça o seguinte: 
    - No campo **Divisões** insira o número de divisões ou grupos, que serão usados para calcular a pontuação recency dos clientes. Por exemplo, se você tiver 100 clientes, uma divisão por 5, significa que há 20 clientes para cada pontuação. Os 20 clientes que fizeram compras recentemente têm uma contagem de recency de 5. Os próximos 20 clientes possuem uma contagem de recency de 4 e assim por diante. Se você tiver 50 clientes, 10 têm uma pontuação recente de 5, 10 têm uma pontuação recente de 4, e assim por diante. 
    - No campo **Prioridade**, selecione quanto peso será fornecido no parâmetro recency em relação a outros parâmetros, quando a pontuação de RFM for calculada para um cliente. Por exemplo, é possível colocar mais valor na pontuação recente do que na pontuação monetária. 
    - No campo **Multiplicador** insira o valor pelo qual a pontuação recency será multiplicada. Se você não inserir um valor, a pontuação não será multiplicada. 
    - No campo **Período** selecione o período de tempo em que a pontuação recente será calculada. Por exemplo, semanal ou mensal.
   
6.  Na Guia Rápida **Frequência**, faça o seguinte: 
    - No campo **Divisões**, insira o número de divisões ou grupos que será usado para calcular a pontuação de frequência dos clientes. 
    - No campo **Prioridade**, selecione quanto peso será fornecido no parâmetro de frequência em relação a outros, quando a pontuação de RFM for calculada para um cliente. 
    - No campo **Multiplicador** insira o valor pelo qual a pontuação de frequência será multiplicada. Se você não inserir um valor, a pontuação não será multiplicada.
   
7.  Na Guia Rápida **Monetária**, faça o seguinte: 
    - No campo **Divisões**, insira o número de divisões ou grupos que serão usados para calcular a pontuação monetária dos clientes. 
    - No campo **Prioridade**, selecione quanto peso será fornecido no parâmetro monetário, em relação a outros, quando a pontuação de RFM for calculada para um cliente. 
    - No campo **Multiplicador** insira o valor pelo qual a pontuação monetária será multiplicada. Se você não inserir um valor, a pontuação não será multiplicada. 
    - No campo **Bruto/líquido**, selecione se a pontuação monetária do cliente deve ser calculada usando o valor bruto ou líquido da fatura. 
    - Se os valores de devolução de um cliente forem subtraídos de cálculo total da fatura do cliente, marque a caixa de seleção **Subtrair devoluções**. 
 
## <a name="view-a-customers-rfm-score"></a>Exibir a contagem de RFM de um cliente
Use esse procedimento para exibir a pontuação RFM de um cliente. 

1.  Vá para **Call center** > **Diários** > **Atendimento ao cliente**. 

2.  Na página **Atendimento ao cliente**, no painel **Atendimento ao cliente**, nos campos de pesquisa, selecione o tipo de palavra-chave a ser pesquisado e digite o texto da pesquisa.

3.  Selecione **Pesquisar**.

4.  Na **Pesquisa de cliente**, selecione o registro do cliente que você deseja, e clique em **Selecionar cliente**. 

A contagem de RFM é exibida no grupo **Histórico da ordem** no lado direito da página **Atendimento ao cliente**. 

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>Exibir ou limpar o histórico de um registro de análise de RFM
Use este procedimento para exibir ou apagar o histórico de um registro de análise de RFM. 

1.  Vá para **Call center** > **Periódico** > **Análise de RFM**.

2.  Na página **Análise de RFM**, selecione o registro que deseja exibir.

3.  Para exibir o histórico de registro, selecione a Guia Rápida **Histórico**.

4.  Para limpar o histórico do registro, selecione **Limpar histórico**.


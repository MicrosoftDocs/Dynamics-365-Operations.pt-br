---
title: Transferir orçamentos do projeto no final do ano fiscal
description: Este artigo fornece informações sobre como transferir os valores de orçamento restantes para os próximos anos e criar detalhes do registro de orçamento.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172321"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a>Transferir orçamentos do projeto no final do ano fiscal

[!include [banner](../includes/banner.md)]

Ao trabalhar em um projeto de vários anos, talvez você tenha o orçamento restante no final do ano fiscal. Você pode transferir os valores de orçamento restantes para um ano futuro e criar detalhes do registro de orçamento para os valores nas contas contábeis associadas. Antes de postergar os valores restantes, revise e analise os valores de orçamento restantes.

## <a name="review-and-analyze-remaining-budget-amounts"></a>Revisar e analisar os valores restantes de orçamento

Conclua as etapas a seguir para revisar os valores do orçamento de final de ano dos projetos, mas não os postergar.

1. Acesse **Gerenciamento e contabilidade do projeto** > **Periódico** > **Orçamentos** > **Postergar orçamentos**. 
2. Na página **Processo de orçamento mantido para uso futuro do projeto**, na guia **Opções de exercício**, verifique se **Postergar valores de orçamento de projeto restantes** está habilitado.
3. Na guia **Parâmetros**, no campo **Ano do orçamento do projeto**, selecione o ano fiscal para o qual deseja visualizar o valor de orçamento restante. 
4. No campo **Ano fiscal de abertura**, selecione o ano fiscal do qual deseja visualizar o valor de orçamento restante. 
5. No campo **Do modelo de previsão**, selecione **Orçamento restante**. 
6. Para incluir projetos que atendem aos critérios selecionados e que não têm orçamento restante, selecione **Mostrar zero restante**.  
7. Na guia **Selecionar orçamentos**, selecione **Recuperar todos os orçamentos** para carregar todos os orçamentos que correspondem aos critérios selecionados e, em seguida, selecione **Processar**. 
8. Para criar uma consulta ao banco de dados que carrega um conjunto específico de orçamentos no painel, selecione **Recuperar orçamentos selecionados**.

Para obter mais informações sobre uma linha específica no painel, selecione a linha e depois **Exibir detalhes do orçamento** ou **Exibir contas**.

## <a name="carry-forward-remaining-budget-amounts"></a>Postergar valores de orçamento restantes 

Ao processar os valores de orçamento restantes, é possível criar transações na contabilidade para os valores que você está postergando. Para criar transações de contabilidade, conclua as etapas na seção [Postergar valores de orçamento e criar transações de contabilidade](#carry-forward). 

> [!NOTE]
> Os valores de orçamento que são postergados são transferidos para o modelo de previsão selecionado na página **Modelos de previsão** como o modelo mantido para uso futuro.  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a>Postergar valores de orçamento e criar transações de contabilidade

1.  Selecione **Gerenciamento e contabilidade do projeto** > **Periódico** > **Orçamentos** > **Postergar orçamentos**. 
2. Na página **Processo de orçamento mantido para uso futuro do projeto**, selecione **Exercício** e habilite **Postergar valores de orçamento de projeto restantes** e **Criar entradas de registro de orçamento na contabilidade**. 
3. Na guia **Parâmetros**, no grupo de campo **Parâmetros do projeto**, selecione o seguinte:

   - **Ano do orçamento do projeto**: selecione o início do ano fiscal para o qual deseja exibir os valores de orçamento restantes. 
   - **Lucros e perdas**: crie transações de lucros e perdas na contabilidade. 
   -  **WIP**: crie transações de trabalho em andamento (WIP) na contabilidade.
   -  **Folha de pagamento**: crie transações de alocação da folha de pagamento na contabilidade. 

5. No grupo de campo **Contabilidade**, forneça as seguintes informações: 

   - No campo **Ano fiscal de abertura**, selecione o ano fiscal para o qual deseja transferir os valores de orçamento restantes para os projetos. O valor padrão é um ano após o valor no campo **Ano do orçamento do projeto**.
   -  No campo **Período de postergação**, selecione o período para o qual deseja criar os detalhes do registro de orçamento na contabilidade. Em geral, é o primeiro período no ano fiscal de abertura.

6. No grupo de campo **Copiar de/para**, forneça as seguintes informações:

   - No campo **Do modelo de previsão**, selecione o modelo de previsão de orçamento de projeto associado aos valores de orçamento restantes que deseja transferir para os projetos. 
   - No campo **Para modelo de orçamento do razão**, selecione o modelo de orçamento do razão associado aos valores restantes de orçamento que deseja transferir para a contabilidade. 
   -  Selecione **Transferir moeda de venda** para usar a moeda de venda do projeto para as transações da contabilidade criadas ao transferir os valores de orçamento para os projetos. Quando a opção não está selecionada, as transações usam a moeda contábil. 
   -  Selecione **Mostrar zero restante** para incluir projetos que não possuem valores de orçamento restantes, mas atenda aos outros critérios selecionados nos projetos exibidos no painel inferior.

7. Na guia **Selecionar orçamentos**, selecione **Recuperar todos os orçamentos** para carregar todos os orçamentos que correspondem aos critérios selecionados. Se você preferir criar uma consulta ao banco de dados que carrega um conjunto específico de orçamentos do projeto no painel, selecione **Recuperar orçamentos selecionados**.
8. Para cada projeto que deseja processar, selecione a opção no início da linha do projeto.

    > [!TIP]
    > Para selecionar todos ou a maioria dos projetos, selecione a marca de seleção no canto superior esquerdo. Para excluir o processamento de qualquer projeto, retire a marca de seleção desse projeto.

9. Para transferir os valores restantes de orçamento dos projetos selecionados para o ano fiscal selecionado e criar detalhes do registro de orçamento na contabilidade, selecione **Processar**.

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a>Postergar valores de orçamento sem criar transações de contabilidade

1. Acesse **Gerenciamento e contabilidade do projeto** > **Periódico** > **Orçamentos** > **Postergar orçamentos**.
2. Na página **Processo de orçamento mantido para uso futuro do projeto**, no campo **Opções de exercício**, selecione **Postergar valores de orçamento de projeto restantes**.
3. No grupo **Parâmetros**, no campo **Ano do orçamento do projeto**, selecione o ano fiscal para o qual deseja visualizar os valores de orçamento restantes.
4. No grupo **Copiar de/para**, forneça as seguintes informações:

   - No campo **Do modelo de previsão**, selecione o modelo de previsão de orçamento de projeto associado aos valores de orçamento restantes que deseja transferir para os projetos. 
   - Selecione **Mostrar zero restante** para incluir projetos que não têm valores de orçamento restantes, mas que atendem aos outros critérios selecionados.
   - No grupo **Selecionar orçamentos**, selecione **Recuperar todos os orçamentos** para carregar todos os orçamentos que correspondem aos critérios selecionados. Para criar uma consulta ao banco de dados que carrega um conjunto específico de orçamentos de projeto no painel, selecione **Recuperar orçamentos selecionados**.

5. Para cada projeto que deseja processar, selecione a opção no início da linha do projeto. 
6. Selecione **Processar** para transferir os valores restantes de orçamento dos projetos selecionados para o ano fiscal selecionado.


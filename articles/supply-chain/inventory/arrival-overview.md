---
title: Visão geral de entrada
description: Este tópico fornece informações sobre o recurso Visão geral de entrada. A página Visão geral de entrada faz parte desse recurso e fornece uma visão geral de todos os itens que devem chegar como itens de entrada.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 30859292f8ec481f018fe0c5a5ca4ca11c246d4c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422257"
---
# <a name="arrival-overview"></a>Visão geral de entrada

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre o recurso Visão geral de entrada. A página Visão geral de entrada faz parte desse recurso e fornece uma visão geral de todos os itens que devem chegar como itens de entrada.

A página **Visão geral de entrada** fornece uma visão geral de todos os itens de entrada esperados. Também mostra as entradas que podem ser inicializadas com base na visão geral. Este tópico concentra-se no processo de recebimento.

## <a name="business-scenario"></a>Cenário de negócios
Considere o seguinte cenário nos processos de entrada.

[![Cenário de negócios](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

Sammy, um funcionário de recebimento, quer saber o que deve ser recebido no dia atual. Na página **Visão geral de entrada**, Sammy pode obter uma visão geral das tarefas atuais e uma previsão aproximada de quantidades, volume, peso, diferentes tipos de ordem etc. Posteriormente, a entrega chega em uma das docas de entrada e Sammy recebe uma lista da entrega. Na página **Visão geral de entrada**, Sammy pode executar as seguintes tarefas:

-   Identificar a ordem de recebimento correspondente e registrar o recibo como **Em andamento**. As linhas necessárias para um registro são geradas automaticamente, e o recebimento pode ser monitorado, mesmo que as transações ainda não tenham sido lançadas como **Registradas**.
-   Acesse a referência do diário de entrada apropriada (isto é, o diário de **Entrada de item** ou o diário de **Entrada de produção**) e identifique os diários que estão prontos para uma atualização de recebimento do produto.

## <a name="arrival-overview-page"></a>Página Visão geral de entrada
Para abrir a página **Visão geral de entrada**, clique em **Gerenciamento de estoque** &gt; **Ordens de entrada** &gt; **Visão geral de entrada**. Você pode exibir uma lista de ordens que devem ser recebidas. A visão geral é dividida em um cabeçalho e linhas. As informações do cabeçalho são agrupadas pelo tipo de ordem, data de recebimento esperada e destino de entrega. Quando uma linha de cabeçalho é selecionada para entrada, todas as linhas de detalhes relacionadas à referência de recebimento são selecionadas para entrada na parte de detalhes da linha da página. Quando todas as linhas relacionadas do diário forem lançadas, estas informações não serão mais mostradas.

### <a name="arrival-overview-profiles"></a>Perfis de visão geral de entrada

A página **Visão geral de entrada** fornece uma visão geral dos itens que devem chegar e a data na qual eles devem chegar. Como parte do processo de entrada, vários conjuntos de configurações pessoais poderão ser usados. Os usuários individuais podem definir suas configurações pessoais na página **Perfis de visão geral de entrada**.

### <a name="set-up-item-arrival"></a>Configurar entrada de item

Em nosso exemplo, Sammy deseja configurar um novo computador em um local que será usado para receber os bens acabados que vêm da produção no Local 1. Na página **Perfis da visão geral de entrada**, Sammy cria uma nova configuração chamada de **Produção do local 1** e especifica as configurações a seguir.

1.  Na Guia Rápida **Opções de entrada**, no grupo de campo **Intervalo**, insira informações sobre um intervalo de dias e os depósitos a serem incluídas na visão geral.
2.  Na Guia Rápida **Opções de entrada**, no grupo de campo **Diário**, insira um depósito de recebimento, um local e um nome do diário (chegada do item/entrada de produção).
3.  Na Guia Rápida **Detalhes da consulta de entrada**, no grupo de campo **Local**, no campo **Restringir ao local**, insira um local para limitar a visão na área da visão geral.
4.  Na Guia Rápida **Detalhes da consulta de entrada**, no grupo de campos **Tipos de transação mostrados**, defina a opção **Ordens de produção** como **Sim**.
5.  Na Guia Rápida **Detalhes da consulta de entrada**, no grupo **Diversos**, defina a opção **Atualização na inicialização** como **Sim** se a exibição for atualizada automaticamente durante a inicialização. Defina a opção **Atualizar em alteração de intervalo** como **Sim** se a exibição for atualizada automaticamente quando valores de intervalo forem alterados.

Para este exemplo, o campo **Nome do perfil de visão geral de entrada** na Guia Rápida **Opções de entrada** da página **Visão geral de entrada** é definido como **Produção do local 1**.

### <a name="prerequisites-for-arrival-journals"></a>Pré-requisitos para os diários de entrada

Para criar automaticamente os diários de entrada da página **Visão geral de entrada**, é necessário definir informações apropriadas no grupo de campos **Diário** na Guia Rápida **Opções de entrada**.

-   É necessário especificar um nome de diário para criar um novo diário.

[![Especificando um nome de diário](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   Se você especificar valores nos campos **Depósito** e **Local**, esses valores serão aplicados nas linhas do diário. Se você não especificar valores, o sistema usará os valores da dimensão especificada nas transações de estoque.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>Itens recebidos de uma ordem de recebimento esperada

Na Guia Rápida **Recebimentos**, Sammy seleciona uma linha e clica em **Iniciar entrada**. Todas as linhas relacionadas que estiverem no intervalo especificado e tiverem uma quantidade a ser registrada serão selecionadas automaticamente. Um diário de entrada do item é gerado com uma correspondência entre a ordem de recebimento esperada e o diário. A quantidade é automaticamente inicializada em todas as linhas criadas.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>Itens recebidos de mais de uma ordem de recebimento esperada

Na Guia Rápida **Recebimentos**, Sammy seleciona várias linhas e depois clica em **Iniciar entrada**. Um diário de entrada do item é gerado com uma correspondência entre todas as ordens de recebimento esperadas e o diário. Todas as linhas são criadas em um cabeçalho de diário de entrada de item, e a quantidade é automaticamente inicializada.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>Receber itens de uma ou mais ordens de recebimento esperadas

#### <a name="view-information"></a>Exibir informações

Para obter uma visão geral de recebimentos esperados em um intervalo de datas, Sammy insere as seguintes informações nos campos na Guia Rápida **Opções de entrada** na página **Visão geral de entrada** e depois clica em **Atualizar** para atualizar a exibição:

-   Nome de perfil da visão geral de entrada: **Consulta**
-   Mostrar linhas: **Todas**
-   Dias anteriores: (Em branco)
-   Dias à frente: **0**
-   Depósitos: **GW, MW**

Sammy pode exibir as seguintes informações:

-   Todas as ordens de recebimento relacionadas para a data do sistema e um número infinito de dias anteriores no intervalo dele (o intervalo **InventTrans.StatusDate**) e os recebimentos nos depósitos GW e MW, independentemente do status.
-   Informações detalhadas de linha para mais de uma ordem. Sammy pode selecionar várias linhas de cabeçalho na visão geral e, em seguida, clicar em **Mostrar todas selecionadas** para exibir todas as informações detalhadas da linha correspondente para todas as ordens selecionadas.
-   Informações sobre uma ordem de compra específica. Para mostrar apenas informações relacionadas a um número de referência específico na visão geral, Sammy pode inserir um número de conta no campo **Número de conta** e um número de ordem no campo **Número de referência**.
-   Uma visão geral das tarefas do registro que estão vencidas para todas as linhas de ordem para as quais um diário de entrada de itens foi criado, mas ainda não foi lançado. Para exibir estas informações, Sammy pode selecionar **Em andamento** no campo **Mostrar linhas**.

### <a name="update-journals"></a>Atualizar diários

Para registrar uma ou mais linhas da ordem vencidas a serem processadas, Sammy pode selecionar as linhas na grade da visão geral ou na grade da linha e clicar em **Diários** &gt; **Mostrar entradas a partir de recebimentos**. Os cabeçalhos de diários de entrada de itens que correspondem às linhas são mostrados. Para atualizar o recebimento de produtos de ordem de compra dos itens registrados, Sammy pode acessar os cabeçalhos do diário de entrada de item prontos para atualização. Para acessar esses cabeçalhos de diários de entrada de itens, ele clica em **Diários** &gt; **Diários prontos de recebimento de produtos**. Todas as linhas de cabeçalho que estão prontas para a atualização do recebimento do produto no intervalo de depósito especificado são mostradas. (As linhas de cabeçalho mostradas que não estão relacionadas ao intervalo de dias.)

### <a name="start-an-arrival-registration"></a>Iniciar um registro de entrada

Selecionando várias linhas na página **Visão geral de entrada**, Sammy pode iniciar uma entrada de mais de uma referência de recibo. Quando ele seleciona uma linha da visão geral de recebimentos, os detalhes da linha correspondente são selecionados. Se houver uma quantidade para registro, o botão **Entrada de Início** estará disponível. Sammy pode usar dois métodos para iniciar o registro de entrada:

-   Para filtrar a página de modo que ela mostre apenas os registros que atendam a critérios específicos, no campo **Referência do fornecedor**, digitaliza um número de referência de um fornecedor, como o código de barras de uma nota de entrega.
-   Na parte da visão geral ou de detalhes da página **Visão geral de entrada**, seleciona manualmente ou cancela a seleção de registros do registro de entrada. Em seguida, quando Sammy clica em **Iniciar entrada**, os registros selecionados são criados automaticamente em um diário de entrada do item. Os registros incluem informações de linha e todas as informações exclusivas de campos são atribuídas.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>Atualizar informações de chegada e processar um recebimento de produtos
Quando todos os bens forem registrados, o gerente de depósito ou o gerente de compras poderá atualizar os itens recebidos com um recebimento do produto para adicionar o custo físico. Para atualizar as informações de entrada e lançar um recebimento do produto, siga essas etapas.

1.  Clique em **Gerenciamento de estoque** &gt; **Ordens de entrada** &gt; **Visão geral de entrada**.
2.  Na página **Visão geral de entrada**, clique em **Diários** &gt; **Diários prontos de recebimento de produtos** para exibir uma lista de diários que estão prontos para a atualização do recebimento de produtos.
3.  Selecione os diários a serem atualizados e clique em **Funções** &gt; **Recebimento de produtos**.
4.  Na página **Lançamento**, insira o número do recebimento de produtos, se ele ainda não estiver disponível no diário, e clique em **OK** para processar o recebimento de produtos.

## <a name="summary"></a>Resumo
A página **Visão geral de entrada** pode ajudar o gerente de depósito e os trabalhadores do depósito a obter uma visão geral do trabalho esperado que deve ser executado como parte de um processo de entrada. A página também pode ser usada para iniciar o processo de entrada de item, para ajudar a garantir que os itens sejam rastreados na primeira entrada no depósito.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
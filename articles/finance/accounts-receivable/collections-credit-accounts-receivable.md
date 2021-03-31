---
title: Cobranças em Contas a receber
description: As informações de cobranças de contas a receber são gerenciadas em uma exibição central usando a página Cobranças do Microsoft Dynamics 365 Finance. Os gerentes de Crédito e cobranças podem usar essa exibição central para gerenciar cobranças. Os agentes de cobranças podem iniciar o processo de cobranças em listas de clientes que são geradas com o uso de critérios de cobrança predefinidos ou na página Clientes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4dd9887debf73b94fb976af873690dcc53b8f53c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224780"
---
# <a name="collections-in-accounts-receivable"></a>Cobranças em Contas a receber

[!include [banner](../includes/banner.md)]

As informações de cobranças de contas a receber são gerenciadas em uma exibição central usando a página Cobranças do Microsoft Dynamics 365 Finance. Os gerentes de Crédito e cobranças podem usar essa exibição central para gerenciar cobranças. Os agentes de cobranças podem iniciar o processo de cobranças a partir das listas de clientes que são geradas usando critérios de cobrança predefinidos ou da página Clientes.

Antes de começar a configurar ou trabalhar com cobranças, você deve entender os seguintes conceitos:
-   Os instantâneos de classificação por vencimento de clientes contêm informações classificadas por vencimento do saldo em um ponto no tempo
-   Os grupos de clientes de cobranças ajudam você a organizar seu trabalho
-   Os agentes de cobranças podem ter seus próprios grupos de clientes
-   As páginas de lista organizam clientes, atividades e casos de cobranças
-   Todas as informações de cobranças de um cliente estão em uma página e você pode agir com base nessa página
-   Renunciar, reaplicar ou reverter juros e taxas podem ser concluídos em uma etapa
-   Criar transações de baixa pode ser concluído em uma etapa
-   Processar pagamentos NSF (insuficiência de fundos) pode ser concluído em uma etapa

As seções a seguir descrevem cada conceito.

## <a name="customer-aging-snapshots"></a>Instantâneo de classificação por vencimento de cliente 
Um instantâneo de classificação por vencimento contém os saldos classificados por vencimento calculados para um cliente em determinado momento. As informações são exibidas na página Lista de saldos classificados por vencimento e na página Cobranças. Um instantâneo de classificação por vencimento deve ser criado para que você possa exibir as informações nas páginas de listagem Cobranças. 

Para cada cliente, um instantâneo de classificação por vencimento contém um cabeçalho do instantâneo de classificação por vencimento e os registros de detalhes que correspondem a cada período de classificação por vencimento na definição do período de classificação por vencimento. 

O cabeçalho do instantâneo de classificação por vencimento contém o valor total devido, o limite de crédito, o valor da guia de remessa, o valor da ordem de venda, o número de transações contestadas e o valor total das transações contestadas para a conta do cliente. Todas as transações do cliente são incluídas no cálculo desses valores. O valor total devido, o limite de crédito, o valor da guia de remessa e o valor da ordem de venda são exibidos no Quadro de Fatos Informações de Crédito da página Cobranças. 

Para cada período de classificação por vencimento na definição do período de classificação por vencimento, um registro de detalhes do instantâneo de classificação por vencimento é criado. Cada registro de detalhes do instantâneo de classificação por vencimento contém a ID do período de classificação por vencimento e o valor total das transações com datas que estão no período de classificação por vencimento. As transações são atribuídas a um período de classificação por vencimento, como 30 dias de atraso. A data é relativa à Classificação por vencimento a partir da data que é especificada quando você cria o instantâneo de classificação por vencimento. As informações são mostradas na página Lista de saldos classificados por vencimento no Quadro de Fatos Saldos classificados por vencimento na página Cobranças.

## <a name="collections-customer-pools"></a> Grupos de clientes de cobranças 
Os grupos de clientes são consultas que definem um grupo de registros de clientes que podem ser exibidos e gerenciados para cobranças ou processos de classificação por vencimento. Use os grupos de clientes para filtrar informações nas página de listagem Saldos classificados por vencimento, Atividades de cobrança e Casos de cobrança. Você também usa grupos de clientes para filtrar as contas de clientes que são incluídas quando os instantâneos de classificação por vencimento são criados.

## <a name="collections-agents"></a>Agentes de cobranças
Por padrão, os usuários podem exibir todas as informações de clientes nas páginas de lista de cobranças. Você pode usar registros de agente de cobranças para determinar os grupos de clientes que estão disponíveis para filtrar as informações nas páginas de lista de cobranças e na página Cobranças. 

Um agente de cobranças é a pessoa que trabalha com clientes para ter certeza de que os pagamentos serão cobrados em tempo hábil. Os agentes de cobranças são funcionários atribuídos a usuários na página Configuração de usuário.

## <a name="collections-list-pages"></a> Páginas de listagem Cobranças 
As seguintes páginas de lista ajudam você a organizar as informações de cobrança.
-   Saldos classificados por vencimento – as colunas na página de listagem exibem saldos do cliente e valores antigos no período de classificação por vencimento. Essas informações ficam armazenadas em um instantâneo de classificação por vencimento. Os períodos de classificação por vencimento são determinados pela definição do período de classificação por vencimento usada. A definição do período de classificação por vencimento é tirada do grupo de clientes, se tiver sido especificada para a consulta de grupo. Se o grupo não tiver uma definição do período de classificação por vencimento, a definição do período de classificação por vencimento padrão especificada na página Parâmetros de contas a receber será usada. Se nenhuma definição do período de classificação por vencimento padrão for especificada, será usada a primeira definição do período de classificação por vencimento na página Definições do período de classificação por vencimento.
-   Atividades de cobranças – as colunas na página de lista exibem as atividades que são identificadas como atividades de cobranças. Essas atividades são criadas usando a página Cobranças. Use atividades para rastrear o trabalho que você relacionou às cobranças.
-   Casos de cobranças – as colunas na página de lista exibem informações para casos que têm uma categoria de caso com um tipo de caso Cobranças.

> [!NOTE]
> Um instantâneo de classificação por vencimento deve ser criado para que você possa exibir as informações nessas páginas de lista. As informações são exibidas somente para os clientes que o instantâneo de classificação por vencimento foi criado. Os registros que são mostrados na página de lista podem ser filtrados adicionalmente, da seguinte maneira:
> <li>Por padrão, um usuário do Finance and Operations tem acesso a todos os clientes com um instantâneo de classificação por vencimento.</li>
> <li>Se os grupos de clientes existem, um usuário deve ser configurado como um agente de cobranças para usar os grupos para filtrar as informações nas páginas de lista de cobranças. As informações são limitadas aos clientes incluídos no grupo de clientes selecionado.</li>
> <li>Se um usuário estiver configurado como um agente de cobranças, apenas os grupos selecionados para esse agente de cobranças estarão disponíveis na página de lista. Se o botão de alternância Permitir que o agente exiba todos os grupos de clientes estiver selecionado na página Agente de cobranças do agente de cobranças, todos os grupos estarão disponíveis para esse agente.</li>


## <a name="collections-page"></a> Página Cobranças
Use a página Cobranças para exibir, gerenciar e adotar uma ação nas informações, atividades e casos de cobranças para um cliente. 

O painel superior exibe as ocorrências do cliente selecionado. O painel central exibe as transações do cliente selecionado. O painel inferior exibe atividades para o cliente. Você pode criar casos de cobranças para controlar as informações de cobranças para uma ou mais transações e atividades. As informações nos painéis superior e inferior podem ser filtradas por caso. 

Os Quadros de Fatos exibem saldos classificados por vencimento e informações de limite de crédito para o cliente selecionado. Essas informações ficam armazenadas no instantâneo de classificação por vencimento. Se necessário, você pode atualizar o instantâneo de classificação por vencimento com informações atuais. 

O Painel de Ação contém os botões que exibem informações relacionadas para o cliente, o caso, a transação ou a atividade selecionada. Você também pode executar ações comuns, como alterar o status de cobranças de uma transação, enviar correspondência por email por meio da integração com seu provedor de email, reembolsar clientes, processar pagamentos NSF e dar baixa em saldos não cobráveis.

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a> Cancelar, restabelecer ou estornar juros ou taxas 
Você pode renunciar, reaplicar ou reverter notas de juros completas, ou taxas e juros de transação que fazem parte das notas de juros. Você pode fazer isso na guia Coletar do Painel de Ação na página de listagem Todos os clientes ao clicar em Nota de juros, em Juros da transação ou em Taxa. 

Esses ajustes afetam somente as notas de juros e os juros e as taxas que elas incluem. Use as etapas descritas na seção “Criar transações de baixa em uma etapa” para dar baixa de todos os encargos devidos por um cliente.

Para obter mais informações, consulte [Criar um código de juros com um intervalo](tasks/create-interest-code-range.md) e [Processar juros](tasks/process-interest.md). 

## <a name="create-writeoff-transactions"></a>Criar transações de baixa
Você pode dar baixa em dívidas perdidas ao clicar em Dar baixa no formulário Cobranças e nas páginas de listagem Saldos classificados por vencimento., Clientes e Faturas de cliente abertas. 

Quando você dá baixa nas transações de um cliente, todas as transações correspondentes são marcadas automaticamente para liquidação. O valor da baixa depende do valor líquido das transações marcadas. A transação de baixa é criada em um diário geral e pode conter até três tipos de linhas de diário.

-   O primeiro tipo de linha do diário contém a entrada de baixa do cliente. Se as transações marcadas contiverem várias combinações de código de moeda, dimensão e perfil de lançamento, uma linha de diário separada será criada para cada combinação.
-   O segundo tipo de linha do diário contém a entrada de baixa de contabilidade. Se as transações marcadas contiverem várias combinações de código de moeda, dimensão e perfil de lançamento, uma linha de diário separada será criada para cada combinação.
-   O terceiro tipo de linha do diário contém as informações de baixa de contabilidade para impostos. Essa linha do diário só será criada se o botão de alternância Imposto separado for selecionado na página Parâmetros de contas a receber. Se as transações marcadas contiverem várias combinações de contas a pagar de imposto, dimensão e código de imposto, uma linha de diário separada será criada para cada combinação.

A transação de baixa é criada na moeda da transação.

Para obter mais informações, consulte [Criar um diário de baixa para um cliente](tasks/create-write-off-journal-customer.md).

<a name="process-not-sufficient-funds-nsf-payments"></a>Processar pagamento de insuficiência de fundos (NSF)  
--------------------------------------------

Você pode processar pagamentos NSF ao clicar em Pagamento NSF na página Cobranças. Quando você clica nesse botão, o pagamento é cancelado. Se uma taxa de NSF for aplica ao cliente, uma transação de encargo será criada em um diário de pagamento. O valor da taxa é baseado nas configurações de encargos automáticos. Os encargos automáticas que se aplicam aos pagamentos NSF são especificados pelo grupo de encargos selecionado na página Contas bancárias para a conta bancária afetada.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Principais conceitos de gerenciamento de cobranças
description: Os tópicos definem os principais conceitos de gerenciamento de cobranças.
author: mikefalkner
manager: AnnBe
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: eb2ec9969bdec985e1f8c731eade1c1a81a4766c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993005"
---
# <a name="collections-management-key-concepts"></a>Principais conceitos de gerenciamento de cobranças

[!include [banner](../includes/banner.md)]

Antes de começar a configurar ou trabalhar com cobranças, você deve entender os seguintes conceitos:

- Os instantâneos de classificação por vencimento de clientes contêm informações de saldo antigo em um determinado ponto no tempo.
- Os grupos de clientes de cobranças ajudam você a organizar seu trabalho.
- Os agentes de cobranças podem ter seus próprios grupos de clientes.
- As páginas de lista organizam clientes, atividades e casos de cobranças.
- Todas as informações de cobranças de um cliente estão em uma página e você pode agir com base nessa página.
- Juros e taxas podem ser cancelados, restabelecidos ou revertidos em uma única etapa.
- Transações de baixa podem ser criadas em uma única etapa.
- Pagamentos NSF (insuficiência de fundos) podem ser processados em uma única etapa.

Este tópico descreve cada conceito.

## <a name="customer-aging-snapshots"></a>Instantâneo de classificação por vencimento de cliente 

Um instantâneo de classificação por vencimento contém os saldos classificados por vencimento calculados de um cliente em um determinado momento. As informações são mostradas na página de lista **Saldos classificados por vencimento** e na página **Cobranças**. Um instantâneo de classificação por vencimento deve ser criado para que você possa ver informações nas páginas de lista de cobranças (**Saldos antigos**, **Atividades de cobranças** e **Casos de cobranças**).

Para cada cliente, um instantâneo de classificação por vencimento tem um cabeçalho do instantâneo de classificação por vencimento e os registros de detalhes que correspondem a cada período de classificação por vencimento na definição do período de classificação por vencimento.

O cabeçalho do instantâneo de classificação por vencimento contém o valor total que é devido, o limite de crédito, o valor da guia de remessa, o valor da ordem de venda, o número de transações contestadas e o valor total das transações contestadas para a conta do cliente. Todas as transações do cliente são incluídas no cálculo desses valores. O valor total que é devido, o limite de crédito, o valor da guia de remessa e o valor da ordem de venda são exibidos no Quadro de Fatos **Informações de crédito** da página **Cobranças**.

Para cada período de classificação por vencimento na definição do período de classificação por vencimento, um registro de detalhes é criado no instantâneo de classificação por vencimento. Cada registro de detalhes contém a ID do período de classificação por vencimento e o valor total das transações que têm datas no período de classificação por vencimento. As transações são atribuídas a um período de classificação por vencimento, como 30 dias de atraso. A data é relativa ao valor da data de **Classificação por vencimento a partir de** especificada quando você cria o instantâneo de classificação por vencimento. As informações são mostradas na página de lista **Saldos antigos** e no Quadro de Fatos **Saldos antigos** da página **Cobranças**.

## <a name="collections-customer-pools"></a> Grupos de clientes de cobranças 

Grupos de clientes são consultas que definem um grupo de registros de clientes. Você pode usar esses registros agrupados para ver informações sobre as contas de cliente incluídas e para gerenciar cobranças ou processos de classificação por vencimento relacionados. Você pode usar grupos de clientes para filtrar informações nas páginas de lista de cobranças. Você também pode usá-los para filtrar as contas de clientes que são incluídas quando os instantâneos de classificação por vencimento são criados.

## <a name="collections-agents"></a>Agentes de cobranças

Por padrão, os usuários podem exibir todas as informações de clientes nas páginas de lista de cobranças. Os registros de agente de cobranças permitem determinar os grupos de clientes que estão podem ser usados para filtrar as informações nas páginas de lista de cobranças e na página **Cobranças**.

Os agentes de cobranças trabalham com os clientes para ter certeza de que os pagamentos serão cobrados em tempo hábil. Eles são os funcionários atribuídos a usuários na página **Configuração de usuário**.

## <a name="collections-list-pages"></a> Páginas de listagem Cobranças 

As seguintes páginas de lista ajudam a organizar as informações de cobrança:

- **Saldos antigos** – As colunas nesta página de lista exibem saldos de cliente e valores antigos no período de classificação por vencimento. Essas informações ficam armazenadas em um instantâneo de classificação por vencimento. Os períodos de classificação por vencimento são determinados pela definição do período de classificação por vencimento usada. A definição do período de classificação por vencimento é tirada do grupo de clientes, se um grupo de clientes tiver sido especificado para a consulta de grupo. Se o grupo não tiver uma definição do período de classificação por vencimento, será usada a definição do período de classificação por vencimento padrão especificada na página **Parâmetros de contas a receber**. Se nenhuma definição do período de classificação por vencimento padrão for especificada, será usada a primeira definição do período de classificação por vencimento na página **Definições do período de classificação por vencimento**.
- **Atividades de cobranças** – As colunas nesta página de lista mostram as atividades identificadas como atividades de cobranças. Essas atividades são criadas na página **Cobranças**. Você usa atividades para rastrear o trabalho relacionado a cobranças feito por você.
- **Casos de cobranças** – As colunas nesta página de lista mostram informações de casos que pertencem a uma categoria de caso que têm um tipo de caso **Cobranças**.

### <a name="aging-snapshots"></a>Instantâneos de classificação por vencimento

Um instantâneo de classificação por vencimento deve ser criado para que você possa exibir as informações nas páginas de lista de cobranças. São mostradas somente as informações dos clientes para os quais foi criado um instantâneo de classificação por vencimento. Os registros mostrados na página de lista podem ser filtrados ainda mais, conforme descrito aqui:

- Por padrão, os usuários têm acesso a todos os clientes que têm um instantâneo de classificação por vencimento.
- Se os grupos de clientes existem, um usuário deve ser configurado como um agente de cobranças para usar os grupos para filtrar as informações nas páginas de lista de cobranças. As informações são limitadas aos clientes incluídos no grupo de clientes selecionado.
- Se um usuário estiver configurado como agente de cobranças, apenas os grupos selecionados para esse agente de cobranças estarão disponíveis nas páginas de lista de cobranças. Se a opção **Permitir que o agente exiba todos os grupos de clientes** estiver selecionada na página **Agente de cobranças** do agente de cobranças, todos os grupos estarão disponíveis para ele.

## <a name="collections-page"></a> Página Cobranças

Você pode usar a página **Cobranças** para exibir, gerenciar e executar uma ação em relação às informações, atividades e casos de cobranças de um cliente.

A seção superior da página mostra os casos do cliente selecionado, a seção do meio mostra as transações do cliente e a seção inferior as atividades do cliente. Você pode criar casos de cobranças para controlar as informações de cobranças para uma ou mais transações e atividades. As informações nas seções superior e inferior podem ser filtradas por caso.

Os Quadros de Fatos mostram saldos antigos e informações de limite de crédito do cliente selecionado. Essas informações ficam armazenadas no instantâneo de classificação por vencimento. Se precisar, você poderá atualizar o instantâneo de classificação por vencimento com informações atuais.

O Painel de Ação contém os botões que permitem ver informações relacionadas do cliente, caso, transação ou atividade selecionada. Você também pode executar ações comuns, como alterar o status de cobranças de uma transação, enviar email pela integração com seu provedor de email, reembolsar clientes, processar pagamentos NSF e dar baixa em saldos não cobráveis.

## <a name="waiving-reinstating-or-reversing-interest-and-fees"></a>Cancelar, restabelecer ou estornar juros e taxas

Você pode cancelar, restabelecer ou estornar notas de juros completas ou as taxas e os juros de transação que fazem parte das notas de juros. Na guia **Coletar** do Painel de Ação da página de lista **Todos os clientes**, selecione **Nota de juros**, **Juros da transação** ou **Taxa**.

Esses ajustes afetam somente as notas de juros e os juros e as taxas que elas incluem. Para obter informações sobre como dar baixa de todos os encargos devidos por um cliente, consulte a seção [Criar transações de baixa](#creating-write-off-transactions) deste tópico.

Para obter mais informações, consulte Criar um código de juros com um intervalo e Processar juros.

## <a name="creating-write-off-transactions"></a>Criar transações de baixa

Você pode dar baixa em dívidas inválidas selecionando **Dar baixa** na página **Cobranças** e nas páginas de lista de cobranças.

Quando você dá baixa nas transações de um cliente, todas as transações dele são marcadas automaticamente para liquidação. O valor da baixa depende do valor líquido das transações marcadas. A transação de baixa é criada em um diário geral e pode conter até três tipos de linhas de diário:

- O primeiro tipo de linha do diário contém a entrada de baixa do cliente. Se as transações marcadas contiverem várias combinações de códigos de moeda, dimensões e perfis de lançamento, uma linha de diário separada será criada para cada combinação.
- O segundo tipo de linha do diário contém a entrada de baixa de contabilidade. Se as transações marcadas contiverem várias combinações de códigos de moeda, dimensões e perfis de lançamento, uma linha de diário separada será criada para cada combinação.
- O terceiro tipo de linha do diário contém as informações de baixa de contabilidade para impostos. Essa linha do diário só será criada se a opção **Separar imposto** for selecionada na página **Parâmetros de contas a receber**. Se as transações marcadas contiverem várias combinações de contas a pagar de imposto, dimensões e códigos de imposto, uma linha de diário separada será criada para cada combinação. A transação de baixa é criada na moeda da transação. Para obter mais informações, consulte Criar um diário de baixa para um cliente.

## <a name="process-nsf-payments"></a>Processar pagamentos NSF

Você pode processar pagamentos NSF selecionando **Pagamento NSF** na página **Cobranças**. Quando você seleciona esse botão, o pagamento é cancelado. Se uma taxa de NSF for aplica ao cliente, uma transação de encargo será criada em um diário de pagamento. O valor da taxa é baseado nas configurações de encargos automáticos. Os encargos automáticos que se aplicam aos pagamentos NSF são especificados pelo grupo de encargos selecionado na página **Contas bancárias** para a conta bancária afetada.

## <a name="additional-resources"></a>Recursos adicionais

[Configuração de parâmetros de gerenciamento de crédito de cliente](./cm-credit-mgmt-setup.md)

[Informações de configuração de gerenciamento de crédito de cliente](./cm-setup-information.md)

[Adicionar informações de gerenciamento de crédito de um cliente](./cm-add-credit-mgmt-information-customer.md)

[Grupos de crédito de cliente](./cm-customer-credit-groups.md)

[Ajustes de limite de crédito de cliente](./cm-credit-limit-adjustments.md)

[Bloqueios de crédito para ordens de venda](./cm-sales-order-credit-holds.md)

[Tarefas periódicas de gerenciamento de crédito de cliente](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
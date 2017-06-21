---
title: "Integração de ativos fixos"
description: "Ativos fixos podem ser integrados à Contabilidade, ao Gerenciamento de estoque, a Contas a receber e a Contas a pagar. Você também pode configurar os Ativos fixos para que sejam integrados às ordens de compra."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 305010c41aa87222c652f98e6aa2b097606052e8
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-assets-integration"></a>Integração de ativos fixos

[!include[banner](../includes/banner.md)]


Ativos fixos podem ser integrados à Contabilidade, ao Gerenciamento de estoque, a Contas a receber e a Contas a pagar. Você também pode configurar os Ativos fixos para que sejam integrados às ordens de compra.

<a name="general-ledger"></a>Contabilidade
--------------

Na Contabilidade, o valor de todos os ativos fixos geralmente é resumido em várias contas principais que são exigidas para relatório financeiro. No entanto, na página **Ativos fixos**, você pode criar muitos registros de ativo fixo. Esses registros podem incluir informações como preço de aquisição, depreciação e avaliação. Toda vez que você lançar uma transação para um ativo fixo, as contas principais adequadas serão atualizadas. As contas principais dos ativos fixos sempre mostram o valor atualizado dos ativos fixos.

Na página **Perfis de lançamentos de ativo fixo**, você define as contas principais nas quais as transações do registro de ativo fixo são lançadas. Você também pode especificar os tipos de transações de ativo fixo que serão lançados em cada conta principal. É possível criar várias combinações de contas principais de ativos fixos, dependendo do nível de detalhes que você deseja para os ativos fixos na contabilidade. As contas principais podem ser baseadas nos tipos de transação, nos registros e em outras contas principais.

## <a name="inventory-management"></a>Gerenciamento de estoque
No diário de estoque para ativos fixos, você pode inserir a aquisição de ativos fixos que a entidade legal gerou ou construiu para si própria. Você pode então transferir itens de estoque para ativos fixos como uma aquisição ou como parte de uma aquisição. 

Também é possível adquirir ativos usando ordens de compra. Quando as ordens de compra contêm itens de estoque designados como ativos fixos, a configuração da opção **Permitir a aquisição de ativos de Compras** na página **Parâmetros de ativos fixos** determina se uma aquisição é lançada para o ativo fixo quando a fatura é lançada. O impacto que a aquisição de ativos fixos tem no estoque depende da configuração da entidade legal. 

Quando um item de estoque se torna uma aquisição de ativo fixo, por meio do diário de estoque, uma ordem de compra ou uma proposta de aquisição, é criada uma transação de aquisição de registros de ativo fixo. Se uma aquisição de registros incluir um registro de depreciações derivado, também será criada uma transação de aquisição de registro de depreciações. 

Postar regras que são definidas na página **Postagem** em controle de gerenciamento de estoque diminui em estoque quando uma aquisição é postada. No entanto, nem sempre é necessário diminuir o estoque ao lançar faturas relacionadas a ativos fixos. Em alguns casos, os ativos fixos podem ser comprados para uso interno. Um exemplo é gerado um laptop comprado para o departamento de vendas. Ao trabalhar com ordens de compra, é possível usar itens configurados tanto para a revenda com para o uso interno. 

Se você usar contas específicas de recebimento e saída em grupos de itens para ativos fixos, é possível usar o mesmo item de estoque para compras internas e como estoque para revenda. 

Os ativos fixos para uso interno são configurados de forma que tenham um tipo de conta **Recebimento de ativo fixo**. Esse tipo de conta é usado para rastrear o recebimento do ativo fixo. Ao lançar uma fatura de fornecedor, use a conta de recebimento de ativo fixo se qualquer uma das seguintes condições se aplicar:

-   A linha da fatura contém um ativo fixo existente para fins internos.
-   A caixa de seleção **Novo ativo fixo?** está marcada para a linha de recebimento de produtos que foi lançada.
-   A caixa de seleção **Criar um novo ativo fixo** é selecionada para a linha de fatura de fornecedor.

Essa conta é tipicamente uma conta de despesa. É possível configurar o tipo de conta **Recebimento de ativo fixo** para um grupo de itens ou para um item individual usando a guia **Ordem de compra** nas páginas **Grupo de itens** ou **Lançamento**.

Da mesma forma, os ativos fixos para uso interno podem ser configurados de forma que tenham um tipo de conta **Emissão de ativo fixo**. Esse tipo de conta é usado para rastrear a emissão do ativo fixo ao destinatário. Quando um ativo é adquirido usando uma ordem de compra, a conta de saída do ativo fixo compensa a conta de débito do ativo fixo. A aquisição de ativo pode ser lançada ao lançar uma fatura de fornecedor ou ao lançar a aquisição do ativo no diário Ativos fixos, provavelmente usando uma proposta de aquisição. É possível configurar o tipo de conta **Emissão de ativo fixo** para um grupo de itens ou para um item individual usando a guia **Estoque** nas páginas **Grupo de itens** ou **Lançamento de item**. 

Por fim, as contas principais que são usadas para lançamento são determinadas pelas opções para integração do razão que são especificadas para o grupo de modelos de item. Além disso, as contas principais que são usadas variam, dependendo de um ativo ter sido atribuído à linha de ordem de compra. As contas são derivadas do perfil de lançamento para cada grupo de itens. 
**Observação:** Se uma reserva de estoque existir quando recebimentos de produtos forem lançados, você não poderá atribuir um ativo fixo nem criar um ativo fixo a partir da linha. 

As contas em que as transações de ativo fixo serão lançadas dependerão de dois fatores: da origem dos ativos, se eles serão comprados ou construídos pela entidade legal, e do tipo de transação do ativo. 

O tipo de transação conecta a transação de estoque ao perfil de lançamentos nos Ativos fixos. Como o perfil de lançamentos nos Ativos fixos define quais contas serão atualizadas, a seleção de um tipo de transação para um ativo fixo também será, indiretamente, uma seleção das contas principais em que a transação será lançada. Para os ativos fixos construídos e comprados, o tipo de transação geralmente será **Aquisição** ou **Ajuste de aquisição**.

## <a name="accounts-receivable"></a>Contas a Receber
A integração de Ativos fixos com Contas a receber usa perfis de lançamento que são configurados nos Ativos fixos. Esses perfis de lançamento são ativados quando um ativo fixo, registro e tipo de transação de ativo fixo são selecionados para uma fatura de cliente antes de seu lançamento. Como os ativos fixos não fazem parte do gerenciamento de estoque, você deverá usar a página **Fatura de texto livre** quando vender um ativo fixo. 

Se o registro incluir um registro de depreciações derivadas, uma transação de registro de depreciações será criada no lançamento da fatura do cliente.

## <a name="accounts-payable"></a>Contas a Pagar
Os ativos fixos são normalmente adquiridos de fornecedores externos. Você pode usar a página **Parâmetros de ativos fixos** para especificar se as aquisições de ativo são sempre lançadas quando as faturas de fornecedor são lançadas, ou se as aquisições de ativo podem ser lançadas somente de Ativos fixos. Se você permitir que aquisições de ativos sejam lançadas de Contas a pagar, as contas de ativo fixo serão atualizadas sempre que uma fatura de fornecedor para uma aquisição de ativo fixo for lançada. 

Se o sistema estiver configurado para lançar uma aquisição de ativo quando uma fatura for lançada, a transação será lançada de acordo com os perfis de lançamentos configurados nos Ativos fixos para os diversos tipos de transação de ativos fixos. O lançamento é controlado pelo ativo fixo, registro e tipo de transação de ativo fixo que são selecionados na página **Ordem de compra** antes do lançamento da fatura de fornecedor. 

Se o registro incluir um registro de depreciações derivadas, uma transação de registro de depreciações será criada no lançamento da fatura do fornecedor.

A integração de cada linha da ordem é ativada na guia **Ativos fixos** da **Guia Rápida Detalhes** da linha na página **Ordem de compra**. Você pode enviar uma ordem de compra para um ativo fixo ao fornecedor. No entanto, os ativos fixos e as contas principais são atualizados somente quando você lança a fatura de fornecedor depois que o ativo fixo é recebido. Como as ordens de compra podem conter somente itens de estoque, o impacto que a aquisição de ativos fixos tem no estoque dependerá da configuração da entidade legal.

## <a name="project-management-and-accounting"></a>Gerenciamento de projetos e de contabilidade
É possível associar um projeto com um ativo que é afetado pelo projeto. Também é possível associar cada fase, tarefa ou subprojeto a um ativo diferente. Um ativo pode ser associado a cada registro do projeto. Você criar a associação ao inserir um número de ativo fixo no campo Número de **ativo fixo** na página **Projetos**. O tipo de projeto deve ser **Interno** ou de **Custo**. 

Também é possível usar a página **Projetos** para exibir os detalhes sobre os ativos associados aos projetos. Para exibir o registro de ativo fixo, clique no link do ativo na Guia Rápida **Configuração** para abrir a página **Ativos fixos**. Em seguida, clique em **Projetos** &gt; **Todos os projetos** para exibir os projetos que estão associados ao ativo fixo. 

É possível associar tipicamente ativos fixos a projetos quando os projetos estão relacionados com trabalho, manutenção ou melhorias para o ativo. Quando o projeto é concluído, um ajuste de valorização para o ativo não será criado automaticamente. Portanto, você deverá criar o ajuste de valorização manualmente, se for necessário. 

Para excluir a associação entre um projeto e um ativo, desmarque o campo **Número do ativo fixo** na página **Projetos**. 

Também é possível designar um ativo fixo que você está criando ou fabricando como parte de um projeto estimado. No fim de um projeto previsto, você pode lançar automaticamente uma transação de aquisição de ativo.

Para obter mais informações, consulte [Adquirir ativos por meio de compras](acquire-assets-procurement.md).





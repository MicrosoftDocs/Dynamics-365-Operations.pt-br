---
title: Faturamento de projeto
description: Este artigo fornece uma visão geral do projeto que fatura por tempo e projetos de preço fixo material. Contém informações sobre propostas de nota fiscal (nota fiscal preliminar), controle de notas fiscais, faturamento por conta, faturamento de fornecedor e notas de crédito.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3d91f6b1ccc3254e2c04d24c5f9bf2014c64e50
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176486"
---
# <a name="project-invoicing"></a>Faturamento de projeto

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do projeto que fatura por tempo e projetos de preço fixo material. Contém informações sobre propostas de nota fiscal (nota fiscal preliminar), controle de notas fiscais, faturamento por conta, faturamento de fornecedor e notas de crédito.

O tipo de projeto determina qual procedimento de faturamento deve ser aplicado. Apenas os dois tipos de projeto externos, por tempo e material e de preço fixo, podem ser faturados. Os projetos por tempo e material e de preço fixo são sempre anexados a um contrato de projeto.

-   **Projetos de preço fixo** – O valor da fatura de cliente é baseado nas agendas de cobrança da fatura. O faturamento é feito através de uma configuração por conta, também conhecida como uma agenda de cobrança. Os projetos de preço fixo podem ser faturados por projeto ou por contrato de projeto.
-   **Projetos por tempo e material** – O valor da fatura de cliente é baseado nas linhas de transação inseridas nos projetos. As transações podem ser faturadas por projeto ou por contrato de projeto.

Projetos por tempo e material e de preço fixo podem ser anexados a faturas de projeto da seguinte forma:

-   **Faturamento por conta** – Projetos por tempo e material e de preço fixo podem ser faturados por conta. Dois tipos de configuração por conta são necessários, um para cada tipo de projeto.
-   **Faturamento na seção de atividades periódicas** – Por meio das funções de atividades periódicas, as transações podem ser faturadas nos projetos. As funções de atividades periódicas fornecem uma visão geral das transações a serem faturadas.
-   **Uso de notas de crédito no faturamento** – Uma nota de crédito pode ser criada para os projetos de preço fixo e por tempo e material.

## <a name="invoice-proposals"></a>Propostas de fatura
Antes de criar uma fatura de cliente para um projeto, é possível criar uma fatura preliminar ou uma proposta de fatura. Em uma proposta de fatura, você pode selecionar as transações de projeto a serem incluídas em uma fatura de projeto. Você pode revisar os detalhes da fatura antes de lançar a fatura do projeto e enviá-la ao cliente ou a outra fonte de financiamento.

### <a name="creating-invoice-proposals"></a>Criando propostas de fatura

Você pode criar propostas de fatura manualmente, selecionando uma lista de transações em um projeto específico. Você também pode configurar as regras de cobrança que especifica quando ao automaticamente uma proposta de fatura. Por exemplo, você pode criar uma regra de cobrança para criar uma proposta de fatura quando o trabalho em um projeto for de 25, 50, 75 e 100 por cento concluído. 

Você pode criar propostas de fatura para as seguintes transações:

-   Horas, despesas, e outras transações do projeto
-   Valores que são retidos por clientes em faturas de projeto anteriores
-   Notas de crédito
-   Valores que são pagos por um cliente antes que um projeto seja iniciado

Você pode criar transações de taxa em uma proposta de fatura. Você também pode alterar o preço de venda por hora, despesa, de itens e transações de taxa. Quando você lança uma proposta de fatura, os preços e as transações atualizadas são adicionados aos relatórios do projeto e ao histórico de transações. 

Para criar várias faturas de cliente para um projeto, você deve criar uma proposta de fatura para cada fatura. Por exemplo, você pode criar faturas com base no tipo de transação. Para especificar as horas em uma fatura de cliente e itens em outra, você deve criar propostas de fatura separadas para transações de hora e transações de taxa. 

Se um projeto tiver mais de uma fonte de financiamento, será possível criar uma proposta de fatura separada para cada fonte de financiamento. Na página **Alocações da regra de financiamento**, você pode definir a porcentagem do valor da transação para a qual alocar cada fonte de financiamento, e a origem para lançar as diferenças de arredondamento.

### <a name="creating-customer-invoices-from-invoice-proposals"></a>Criar faturas de cliente com base nas propostas de fatura

Após criar e lançar uma proposta de fatura, uma fatura de cliente será criada automaticamente para as transações que são incluídas na proposta de fatura. 

Antes de lançar uma proposta de fatura, você pode adicionar transações a ela ou excluir transações dela. Por exemplo, você pode remover as transações de despesa que foram lançadas em um projeto mas que não são passíveis de cobrança para o cliente. 

Se sua organização exige que as propostas de fatura sejam revisadas antes de serem lançadas, uma proposta de fatura precisará ser aprovada por meio do fluxo de trabalho "Revisar propostas de fatura de projeto" antes de ser lançada.

## <a name="on-account-invoicing"></a>Faturamento por conta
O valor inserido para um projeto em uma fatura por conta é baseado no controle de tempo, percentual de conclusão e em outras condições de cobrança especificadas no contrato de projeto. O valor não é calculado com base nas horas, itens, despesas ou taxas que são lançadas no projeto. 

Você deve criar uma transação por conta para um projeto de tempo e material ou um projeto de preço fixo para poder adicionar a transação por conta a uma fatura de projeto. Na transação por conta, insira o valor da fatura de um cliente. Para criar uma fatura de projeto para o valor, crie uma fatura preliminar (proposta de fatura). Na proposta de fatura, selecione a transação por conta. Você pode rever as informações por conta na proposta de fatura antes de criar uma fatura de projeto para ela.

### <a name="fixed-price-projects"></a>Projetos de preço fixo

Para projetos de preço fixo, as transações por conta são baseadas em uma etapa combinada, na unidade de entrega, ou na organização de cobrança parcial que é especificada em um contrato de projeto. Uma linha é criada para cada pagamento que deve ser recebido do cliente do projeto. Nenhuma dedução é necessária.

### <a name="time-and-material-projects"></a>Projetos por tempo e material

Para projetos por tempo e material, você pode cobrar de um cliente ou de outra fonte de financiamento um valor do pagamento antecipado usando uma proposta de fatura por conta. Insira transações por conta como uma linha. Como opção, você pode inserir linhas adicionais como deduções para compensar todos os pagamentos antecipados que o cliente já fez. Para criar linhas de dedução, preceda o valor com um sinal de subtração.

## <a name="invoice-control"></a>Controle de faturas
Você pode usar o controle de faturas para rastrear transações faturadas e não faturadas, e para analisar as transações em relação a cotações para uma exibição ponta a ponta de seus projetos desde o estágio de cotação até a conclusão. Você pode ver quais transações foram cobradas para um projeto específico e quais linhas foram faturadas. Também é possível exibir as transações de forma a poder ajustá-las depois de serem lançadas.

## <a name="invoicing-fixed-price-projects"></a>Faturando projetos de preço fixo
Para faturar um projeto de preço fixo, você deve definir uma agenda de cobrança e concluir o procedimento de faturamento.

### <a name="billing-schedule"></a>Agenda de cobrança

Você pode faturar projetos de preço fixo em uma agenda de cobrança. A agenda de cobrança é definida em termos de uma ou várias etapas para o projeto. Para cada etapa, você pode definir uma data, uma moeda de venda, um preço de venda, e uma atividade específica. 

Por exemplo, é possível configurar a seguinte agenda de cobrança:

-   20% quando o contrato de projeto é assinado
-   30% na primeira entrega
-   15% na segunda entrega
-   35% na entrega final

### <a name="invoicing-procedure"></a>Procedimento de faturamento

Quando os pagamentos em etapa estiverem prontos para serem faturados, use o procedimento de faturamento de valores da conta.

## <a name="vendor-invoicing"></a>Faturamento de fornecedor
Quando você solicitar um item de um fornecedor e atribuir o item a um projeto, a propriedade selecionada para uma linha de ordem de compra para um item determina se o item comprado será faturado para um cliente. Se você configurar as propriedades de linha, elas serão exibidas para o item na linha de ordem de compra (Detalhes da linha &gt; Projeto &gt; Propriedade da linha). Há duas maneiras de alterar a propriedade da linha:

-   Fature o cliente do projeto para o item: Defina a propriedade da linha do item como um valor passível de cobrança na ordem de compra, e fature o cliente usando o método de faturamento de projeto correto.
-   Não fature o cliente do projeto para o item: Não selecione a propriedade de linha **Passível de cobrança** na linha da ordem de compra para o item. Você pode faturar a ordem de compra e não será necessário tomar mais ações.

## <a name="credit-notes"></a>Notas de crédito
Quando um valor em uma fatura do cliente tem um valor negativo, a fatura é classificada como uma nota de crédito. Quando o documento é impresso, ele tem o título "Nota de crédito." 

Ao criar uma nota de crédito para creditar um valor faturado anteriormente, primeiro você deve selecionar o valor faturado para crédito. Em seguida, crie uma nota de crédito seguindo o mesmo procedimento usado para criar uma fatura de cliente comum. Ou seja, é necessário selecionar as transações lançadas anteriormente em uma fatura de cliente e, em seguida, criar e lançar uma proposta de nota de crédito. 

O mesmo documento pode incluir transações selecionadas para crédito, transações de crédito e transações que foram lançadas. O documento é classificado como uma fatura ou nota de crédito, dependendo se o valor total é positivo ou negativo. 

Para creditar um valor faturado, primeiro selecione o valor faturado a ser creditado e, em seguida, crie uma nota de crédito. Crie uma nota de crédito seguindo o mesmo procedimento usado para gerar uma fatura de cliente. 

Você pode criar uma fatura com um valor negativo, que se torna uma fatura classificada como nota de crédito. Para criar e imprimir uma nota de crédito, você deve selecionar as transações lançadas anteriormente para uma fatura de cliente e, em seguida, modificar as transações. Com exceção das entidades legais cujo endereço principal é a Alemanha, o cabeçalho da fatura é "fatura corretiva".




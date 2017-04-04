---
title: Faturamento intercompanhia
description: "Este artigo fornece informações e os exemplos sobre faturamento intercompanhia de projetos no Microsoft Dynamics 365 para as operações."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 8a606f81e6e66390bf0add3deeeb032ab4cbd90b
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-invoicing"></a>Faturamento intercompanhia

Este artigo fornece informações e os exemplos sobre faturamento intercompanhia de projetos no Microsoft Dynamics 365 para as operações.

Sua organização pode ter várias divisões, subsidiárias, e outras entidades legais que transferem produtos e serviços entre si para projetos. A entidade legal que fornece serviço ou produtos são chamados o entity* legal *lending, e a entidade legal que recebe o serviço ou produtos são chamadas o entity* legal *borrowing. 

A ilustração a seguir mostra um cenário típico em que duas entidades legais, SI FR (a entidade legal que toma o empréstimo) e SI EUA (a entidade legal de empréstimo), compartilham recursos para entregar um projeto para o cliente A. Para esse cenário, SI FR é contratada para oferecer o trabalho ao cliente A. 

[exemplo de faturamento intercompanhia do![(]. /media/interco.invoicing-01.jpg)](. /media/interco.invoicing-01.jpg) 

A meta é que o controle de custos, o reconhecimento de receita, impostos, e o preço de transferência intercompanhia para as transações de projeto mais flexível e avançado. Adicionalmente, são fornecidos os seguintes recursos:

-   Crie faturas do cliente em relação a um projeto em uma entidade legal que toma o empréstimo através do uso de tabelas de tempos, despesas, e faturas de fornecedor intercompanhia em uma entidade legal de empréstimo.
-   Suporte para cálculos de impostos e custos indiretos.
-   Adie o reconhecimento de receita em uma entidade legal de empréstimo e quando uma entidade legal que toma o empréstimo deve reconhecer o custo.
-   Acumule a receita do trabalho em andamento (WIP) na entidade legal de empréstimo.
-   Defina preços de transferência que podem ser baseados em diversos modelos de preços. Eis alguns exemplos:
    -   **Quantidade** – A quantia inserida no campo **Preço** é o custo real por quantidade ou unidade.
    -   **Quantia de encargos** – O preço/custo por transação somados à quantia de encargos inserida no campo **Preço**.
    -   **Porcentagem de encargos** – O preço de transferência é o preço/custo por transação multiplicado pela porcentagem de encargos inserida no campo **Preço**.
    -   **Porcentagem do preço de venda** – A porcentagem do preço de venda que é transferida para a entidade legal de empréstimo.
    -   **Valor abaixo do preço de venda** – O valor que a entidade legal que toma o empréstimo retém dos preços de venda antes da transferência para a entidade legal de empréstimo.
    -   **Relação de contribuição** – O número inserido no campo **Preço** é a relação de contribuição, que é expressada como uma porcentagem do preço de venda.

## <a name="example-1-set-up-parameters-for-intercompany-invoicing"></a>Exemplo 1: Configurar parâmetros para faturamento intercompanhia
Neste exemplo, USSI é uma entidade legal de empréstimo e seus recursos estão reportando tempo contra a entidade legal que toma o empréstimo, FRSI, proprietária do contrato com o cliente final. Horas e despesas relatadas pelos funcionários da USSI podem ser incluídos na fatura do projeto gerada pela FRSI. Além disso, há uma terceira fonte de transações que pode se originar da entidade legal de empréstimo (USSI neste exemplo) quando ela fornece serviços de fornecedores compartilhados à subsidiárias (como a FRSI) e, em seguida, passa esses custos para projetos dentro das subsidiárias. Todos os documentos de nota fiscal correspondente e cálculos de imposto são concluídos por dynamics 365 para as operações. 

Para este exemplo, a FRSI deve ser um cliente na entidade legal USSI, e a USSI deve ser um fornecedor na entidade legal FRSI. É possível configurar uma relação intercompanhia entre as duas entidades legais. O procedimento a seguir mostra como definir os parâmetros para que ambas as entidades legais possam participar do faturamento intercompanhia.

1.  Configurar a FRSI como um cliente na entidade legal USSI, e configurar a USSI como um fornecedor na entidade legal FRSI. Existem três pontos de entrada para as etapas que são necessárias para essa tarefa.
    | Etapa | Ponto de entrada                                                                       | descrição   |
    |------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A    | Em USSI, clique ** contas a receber ** &gt; ** clientes ** &gt; ** ** todos os clientes. | Crie um novo registro de cliente para a FRSI, e selecione o grupo de clientes.                                                                                                                                                                                                                           |
    | B    | Em FRSI, clique ** contas a pagar ** &gt; ** fornecedores ** &gt; ** ** todos os fornecedores.        | Crie um novo registro de fornecedor para a USSI, e selecione o grupo de fornecedores.                                                                                                                                                                                                                               |
    | C    | Na FRSI, abra o registro de fornecedor que você acabou de criar.                            | No Painel de ação, na guia **Geral**, no grupo **Configurar**, clique em **Intercompanhia**. Na página **Intercompanhia**, na guia **Relação de comércio**, defina a barra deslizante **Ativo** para **Sim**. No campo **Empresa cliente**, selecione o registro de cliente que você criou na etapa A. |

2.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** de instalação ** &gt; ** parâmetros de contabilidade de gerenciamento de projetos **, e em ** intercompanhia ** a guia. A maneira como você configura os parâmetros depende se você é a entidade legal de empréstimo ou a entidade legal que toma o empréstimo.
    -   Se você for a entidade legal que toma o empréstimo, selecione a categoria de aquisição que deve ser usada para corresponder as faturas de fornecedor, que são geradas automaticamente.
    -   Se você for a entidade legal de empréstimo, para cada entidade que toma o empréstimo, selecione uma categoria de projeto padrão para cada tipo de transação. Categorias de projeto são usadas para a configuração de impostos quando a categoria faturada em transações entre empresas existe somente na entidade legal que toma o empréstimo. É possível escolher acumular receita para transações entre empresas. Esse acúmulo é feito quando as transações são lançadas e, em seguida, é revertido quando a fatura intercompanhia é lançada.

3.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** de instalação ** &gt; ** preços ** &gt; ** ** preço de transferência.
4.  Selecione uma moeda, um tipo de transação e um modelo de preço de transferência. A moeda usada na fatura é a moeda configurada no registro de cliente da entidade legal que toma o empréstimo na entidade legal de empréstimo. A moeda é usada para corresponder entradas na tabela de preços de transferência.
5.  Clique ** contabilidade ** &gt; ** configuração de postagem ** &gt; ** ** contabilidade intercompanhia, e configurar uma relação para USSI e FRSI.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>Exemplo 2: Criar e lançar uma tabela de tempos intercompanhia
A USSI, entidade legal de empréstimo, deve criar e lançar a tabela de tempos para um projeto da FRSI, a entidade legal que toma o empréstimo. Existem dois pontos de entrada para as etapas que são necessárias para essa tarefa.

| Etapa | Ponto de entrada                                                                       | descrição                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | ** Gerenciamento e contabilidade de projeto ** &gt; ** folha de ponto ** &gt; ** as folhas de ponto ** | Crie uma nova tabela de tempo. Na linha da tabela de tempo, no campo **Entidade Legal**, selecione **FRSI**. No campo **ID do projeto**, selecione o projeto na FRSI. Insira o número de horas para cada dia da semana. |
| B    | Página **Tabela de tempos**                                                                | Após a execução do fluxo de trabalho, envie a tabela de tempos, e anote o número do comprovante.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>Exemplo 3: Criar e lançar uma fatura de fornecedor intercompanhia
A USSI, entidade legal de empréstimo, deve criar e lançar a fatura de fornecedor intercompanhia para um projeto da FRSI, a entidade legal que toma o empréstimo. Essa fatura de fornecedor representa o trabalho terceirizado e despesas que foram realizadas pelos fornecedores, pagas pela USSI. Existem dois pontos de entrada para as etapas que são necessárias para essa tarefa.

| Etapa | Ponto de entrada                                                                                      | descrição                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | ** Contas a pagar ** &gt; ** faturas ** &gt; ** faturas de fornecedor abertas ** &gt; ** nova nota fiscal de fornecedor ** | Crie uma nova fatura de fornecedor e insira os serviços que foram adquiridos em nome do projeto do FRSI.                                                                                                                                                                                  |
| B    | A página **Fatura de fornecedor**                                                                      | Insira as linhas que representam os serviços terceirizados em nome de FRSI. Na Guia Rápida **Detalhes da linha**, na guia **Projeto** para a linha da fatura, no campo **Empresa do projeto**, insira **FRSI**. Insira o projeto e as informações correspondentes. Então envie a fatura de fornecedor. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>Exemplo 4: Criar e lançar a fatura intercompanhia
A USSI, entidade legal de empréstimo, deve criar e lançar a fatura intercompanhia. Existem dois pontos de entrada para as etapas que são necessárias para essa tarefa.

| Etapa | Ponto de entrada                                                                                             | descrição                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | ** Gerenciamento e contabilidade de projeto ** &gt; ** fiscais de projeto ** &gt; ** nota fiscal do cliente intercompanhia **  | Clique em **Novo** para abrir a página **Criar fatura intercompanhia**.                                                                                  |
| B    | ** Gerenciamento e contabilidade de projeto ** &gt; ** fiscais de projeto ** &gt; ** faturas de cliente intercompanhias ** | Na página **Criar fatura intercompanhia**, insira a entidade legal, especifique a transação que deve ser incluída e clique em **Pesquisa**. |
| C    | ** Gerenciamento e contabilidade de projeto ** &gt; ** fiscais de projeto ** &gt; ** faturas de cliente intercompanhias ** | Selecione as transações para a fatura, ou clique em **Selecionar tudo** para faturar todas as transações na lista e, em seguida, clique em **OK**.                  |
| D    | A página **Fatura intercompanhia**                                                                       | A proposta de fatura de cliente intercompanhia é exibida.                                                                                             |
| E    | A página **Fatura intercompanhia**                                                                       | Clique em **Enviar**.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>Exemplo 5: Enviar a fatura de fornecedor e faturar do cliente
Quando a entidade legal empréstimo, USSI, lança a fatura de cliente intercompanhia, uma fatura de fornecedor pendente correspondente é criada na entidade legal que toma o empréstimo, FRSI. Assim que essa fatura de fornecedor é lançada, a FRSI também fatura o projeto do cliente levando em conta as horas inseridas pela USSI. Existem três pontos de entrada para as etapas que são necessárias para essa tarefa.

| Etapa | Ponto de entrada                                                                                        | descrição                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A    | ** Contas a pagar ** &gt; ** faturas ** &gt; ** durante ** faturas de fornecedor                            | Examine a fatura para verificar se os valores da tabela de tempos estão incluídos, e então envie a fatura de fornecedor.                  |
| B    | ** Gerenciamento e contabilidade de projeto ** &gt; ** fiscais de projeto ** &gt; ** propostas de nota fiscal de projeto ** | Crie uma nova fatura de projeto para o projeto e verifique se as transações de horas lançadas aparecem.            |
| C    | A página **Fatura de projeto**                                                                       | Selecione a fatura de projeto e, em seguida, clique em **Exibir detalhes** para revisar o custo e o valor de venda. Em seguida, envie a fatura. |





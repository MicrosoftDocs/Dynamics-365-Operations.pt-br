---
title: "Relatórios financeiros"
description: "Este tópico descreve onde acessar o relatório financeiro no Microsoft Dynamics 365 for Finance and Operations, Enterprise edition e como usar os recursos do relatório financeiro. Ele inclui uma descrição de relatórios financeiros padrão que são fornecidos."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e73f2bd29a6d715863f04bdad03fe9c279ebe0b1
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="financial-reporting"></a>Relatórios financeiros

[!include[banner](../includes/banner.md)]


Este tópico descreve onde acessar o relatório financeiro no Microsoft Dynamics 365 for Finance and Operations, Enterprise edition e como usar os recursos do relatório financeiro. Ele inclui uma descrição de relatórios financeiros padrão que são fornecidos.

<a name="accessing-financial-reporting"></a>Avaliando relatórios financeiros
-----------------------------

Você pode encontrar o menu **Relatórios financeiros** nos seguintes locais no Dynamics 365 for Finance and Operations:

-   **Contabilidade** &gt; **Consultas e relatórios**
-   **Orçamento** &gt; **Consultas e relatórios** &gt; **Orçamento básico**
-   **Orçamento** &gt; **Consultas e relatórios** &gt; **Planejamento de orçamento**
-   **Orçamento** &gt; **Consultas e relatórios** &gt; **Controle de orçamento**
-   Consolidações

Para criar e gerar relatórios financeiros para uma entidade legal, você deve configurar as informações a seguir para essa entidade legal:

-   Calendário fiscal
-   Razão
-   Plano de contas
-   Moeda

As funções de relatórios financeiros estão disponíveis para os usuários que têm os privilégios e os direitos apropriados atribuídos a eles com as funções de segurança. As seções a seguir listam os privilégios e direitos, juntamente com as funções associadas.

### <a name="duties"></a>Direitos

| Rótulo do imposto                            | Descrição                                                             | Nome de AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Manter a segurança de relatórios financeiros | Manter a segurança de relatórios financeiros e executar tarefas administrativas. | FinancialReportsSecurityMaintain |
| Manter relatórios financeiros            | Criar e manter relatórios financeiros.                                  | FinancialReportsMaintain         |
| Gerar relatórios financeiros            | Gerar e atualizar relatórios financeiros.                                 | FinancialReportsGenerate         |
| Rever o desempenho financeiro          | Rever e analisar o desempenho financeiro.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilégios

| Rótulo do privilégio                       | Descrição                                                             | Nome de AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Manter a segurança de relatórios financeiros | Manter a segurança de relatórios financeiros e executar tarefas administrativas. | FinancialReportsSecurityMaintain |
| Manter relatórios financeiros            | Criar e manter relatórios financeiros.                                  | FinancialReportsMaintainReports  |
| Gerar relatórios financeiros            | Gerar e atualizar relatórios financeiros.                                 | FinancialReportsGenerateReports  |
| Exibir relatórios financeiros                | Exibir relatórios financeiros.                                                 | FinancialReportsView             |

### <a name="roles"></a>Funções

| Rótulo do privilégio                       | Direitos                                  | Funções                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Manter a segurança de relatórios financeiros | Manter a segurança de relatórios financeiros | Administrador de segurança                                                          |
| Manter relatórios financeiros            | Manter relatórios financeiros            | Gerente de Contabilidade, Supervisor de Contabilidade, Controlador Financeiro, Gerente de Orçamento |
| Gerar relatórios financeiros            | Gerar relatórios financeiros            | CEO, CFO, Contador                                                            |
| Exibir relatórios financeiros                | Rever o desempenho financeiro          | Nenhum atribuído                                                                   |

Depois que um usuário é adicionado ou uma função é alterada, o usuário deve acessar os relatórios financeiros em alguns minutos. **Observação:** A função sysadmin foi adicionada a todas as funções no relatório financeiro.

## <a name="default-reports"></a>Relatórios padrão
Os relatórios financeiros fornecem 22 relatórios financeiros padrão. Cada relatório usa as categorias de conta principal padrão no Finance and Operations. Você pode usar esses relatórios da forma como são ou como um ponto de partida para os relatórios financeiros necessários. Além dos demonstrativos financeiros tradicionais, como o demonstrativo de renda e o balanço, esses relatórios incluem relatórios que mostram os diferentes tipos de relatórios financeiros que você pode criar. Cada relatório na tabela a seguir é vinculado a uma apresentação do Office Mix sobre o relatório.

| Relatório padrão                                                                                         | descrição                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Demonstrativo de Renda de Coluna Única de Rolagem de 12 Meses – Padrão](https://mix.office.com/watch/76kc7bm3wnt1) | Exibir a lucratividade de uma organização para os últimos 12 meses em uma única coluna.                                                                                                                                                                                                                                      |
| [Demonstrativo de Renda de Tendência de 12 Meses – Padrão](https://mix.office.com/watch/12brmfge5p8r)                 | Exibir a lucratividade de uma organização para cada um dos últimos 12 meses. Esses 12 meses podem abranger mais do que um ano fiscal.                                                                                                                                                                                             |
| [Real vs Orçamento – Padrão](https://mix.office.com/watch/fi439lkwr0no)                                | Exibir informações detalhadas de saldo para todas as contas do orçamento original, e comparar o orçamento verificado com os valores reais que têm uma variação.                                                                                                                                                                          |
| [Detalhes da Auditoria – Padrão](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Exibir informações de saldo detalhadas para todas as contas. Este relatório mostra os saldos de débito e crédito na moeda de relatório e na moeda local, juntamente com as informações de transação adicionais, como a ID do usuário, o usuário que modificou os dados por último, a data da última modificação, e a ID do diário. |
| [Lista de Saldo – Padrão](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Exibir informações de saldo detalhadas para todas as contas. Este relatório mostra os saldos de abertura e fechamento, e os saldos de crédito e débito para o período atual e o ano até a data, juntamente com as informações de transação adicionais, como o comprovante.                                                                    |
| [Balanço - Padrão](https://mix.office.com/watch/zkgq0u7visw9)                                   | Exibir a posição financeira da organização para o ano.                                                                                                                                                                                                                                                             |
| [Balanço e Demonstrativo de Renda Lado a Lado - Padrão](https://mix.office.com/watch/zkgq0u7visw9) | Exibir a posição financeira e a lucratividade da organização para o ano lado a lado.                                                                                                                                                                                                                              |
| [Fluxo de Caixa – Padrão](https://mix.office.com/watch/jd3go9pz6390)                                       | Obter uma ideia do dinheiro que está entrando e saindo da organização.                                                                                                                                                                                                                                   |
| [Revisão JE e TB Detalhada – Padrão](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Exibir o saldo de abertura e as informações de atividade para todas as contas.                                                                                                                                                                                                                                                      |
| [Balancete Detalhado - Padrão](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Exibir informações de saldo para todas as contas que possuem saldos de crédito e débito, e a rede desses saldos, juntamente com a data da transação, comprovante, e descrição do diário.                                                                                                                                  |
| [Tendência Trimestral de Três Anos de Despesas – Padrão](https://mix.office.com/watch/gwm4zu7tmtj8)             | Obter uma ideia das despesas dos últimos 12 trimestres dos três anos anteriores.                                                                                                                                                                                                                                   |
| [Revisão JE e TB das Legendas Financeiras – Padrão](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Obter uma visão geral dos saldos e da atividade do ativo, responsabilidade, capital próprio do proprietário, receita, despesa, lucro, ou legendas financeiras de perdas.                                                                                                                                                                           |
| [Demonstrativo de renda – Padrão](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Exibir a lucratividade da organização para o período atual e o ano até o momento.                                                                                                                                                                                                                                   |
| [Lista de Transações do Razão – Padrão](https://mix.office.com/watch/19h9v2rmh48vy)                        | Exibir informações de saldo detalhadas para todas as contas. Este relatório mostra os saldos de crédito e débito, juntamente com as informações de transação adicionais, como a data da transação, número do diário, comprovante, tipo de lançamento, e número de rastreamento.                                                                            |
| [Taxas – Padrão](https://mix.office.com/watch/b08hfc5h92me)                                          | Exibir a solvência, lucratividade, e taxas de eficiência da organização para o ano.                                                                                                                                                                                                                           |
| [Despesas de Rolagem de 12 Meses – Padrão](https://mix.office.com/watch/iywod5qmqhz7)                       | Obter uma ideia das despesas para cada um dos últimos 12 meses. Esses 12 meses podem abranger mais do que um ano fiscal.                                                                                                                                                                                                       |
| [Demonstrativo de Renda do Trimestre de Rolagem – Padrão](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Exibir a lucratividade da organização trimestralmente para o ano passado e também para o ano até o momento.                                                                                                                                                                                                                   |
| [Balanço Lado a Lado – Padrão](https://mix.office.com/watch/zkgq0u7visw9)                      | Exibir a posição financeira da organização para o ano. Este relatório mostra os ativos e o passivo, e o capital próprio de acionistas lado a lado.                                                                                                                                                                                |
| [Resumo do Balancete – Padrão](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Exibir informações sobre saldo para todas as contas que têm saldos de abertura e de fechamento, e saldos de débito e crédito com a diferença líquida.                                                                                                                                                                  |
| [Resumo do Balancete Ano a Ano – Padrão](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Exibir informações sobre saldo para todas as contas que têm saldos de abertura e de fechamento, e saldos de débito e crédito junto com a diferença líquida para o ano atual e o ano passado.                                                                                                                           |
| [Vendas e Descontos Semanais - Padrão](https://mix.office.com/watch/112ng0hy5de0j)                     | Obter uma ideia das vendas e descontos para cada semana em um mês. Esse relatório inclui um total de quatro semanas.                                                                                                                                                                                                              |
| [Fundos de Orçamento Disponíveis - Padrão](https://mix.office.com/watch/15hcpezcbx7tv)                         | Exibir uma comparação detalhada de orçamento revisado, despesas efetivas, reservas de orçamento e dos fundos de orçamento disponíveis para todas as contas                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Abrindo relatórios financeiros
Ao clicar no menu **Relatórios financeiros**, a lista de relatórios financeiros padrão da empresa será exibida. É possível abrir ou modificar um relatório. Para abrir um dos relatórios padrão, selecione o nome do relatório. Na primeira vez que um relatório for aberto, será gerado automaticamente para o mês anterior. Por exemplo, se você abrir um relatório pela primeira vez em agosto de 2016, o relatório é gerado para 31 de julho de 2016. Depois que um relatório for aberto, você pode começar a explorá-la ao aprofundamento de partes específicas de dados e alterar opções de relatório.

## <a name="creating-and-modifying-financial-reports"></a>Criando e modificando relatórios financeiros
Na lista de relatórios financeiros, você pode criar um novo relatório ou modificar um existente relatório. Se você tiver as permissões apropriadas, poderá criar um novo relatório financeiro clicando em **Novo** no painel de Ação. Um programa de designer de relatórios é baixado para seu dispositivo. Depois que o designer de relatórios for iniciado é possível criar o novo relatório. Depois de salvar o novo relatório, ele aparecerá na lista de relatórios financeiros. A lista mostra apenas os relatórios que foram criados para a empresa que você está usando no Finance and Operations. Para obter mais informações sobre o processo de criar e modificar relatórios financeiros no Finance and Operations, consulte estas [postagens de blog](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) do blog do relatório financeiro do Dynamics. **Observação:** O computador no qual você estiver baixando o cliente de designer de relatórios deve ter a versão 4.6.2 do Microsoft .NET Framework instalada. Esta versão do Microsoft .NET Framework pode ser baixada e instalada [aqui](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Se estiver usando o Chrome, instale uma extensão de ClickOnce para baixar o cliente de designer de relatórios. Se estiver executando no modo incógnito, verifique se a extensão de ClickOnce está habilitada para modo incógnito. Você também pode modificar um relatório que aparece na lista de relatórios financeiros. Quando a área em torno do nome do relatório é selecionada, clique em **Editar** no Painel de Ação. O Report Designer é inicializado.

<a name="see-also"></a>Consulte também
--------

[Exibir relatórios financeiros](view-financial-reports.md)

[Blog de Relatório Financeiro do Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)





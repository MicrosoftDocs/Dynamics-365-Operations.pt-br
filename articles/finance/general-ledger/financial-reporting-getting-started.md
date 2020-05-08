---
title: Visão geral dos relatórios financeiros
description: Este tópico descreve onde acessar relatórios financeiros no Microsoft Dynamics 365 Finance e como usar os recursos de relatório financeiro. Ele inclui uma descrição de relatórios financeiros padrão que são fornecidos.
author: aprilolson
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6cd77e22f9c6f90f6aa9934d70a121008e1274dd
ms.sourcegitcommit: 5419f2b8f51cd5de55be66d1389b5b9d7771fd52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2020
ms.locfileid: "3262640"
---
# <a name="financial-reporting-overview"></a>Visão geral de relatórios financeiros

[!include [banner](../includes/banner.md)]

Este tópico descreve onde acessar relatórios financeiros e como usar os recursos de relatório financeiro. Ele também inclui uma descrição de relatórios financeiros padrão fornecidos.

<a name="accessing-financial-reporting"></a>Avaliando relatórios financeiros
-----------------------------

Você pode encontrar o menu **Relatórios financeiros** nos seguintes locais:

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
| Manter a segurança de relatórios financeiros | Manter a segurança de relatórios financeiros e executar tarefas administrativas. | FinancialReportsSecuritySystemMaintain |
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

## <a name="report-deletions-and-expirations"></a>Exclusão e vencimento de relatórios
Os usuários que geram um relatório podem excluir seus próprios relatórios. Os usuários com a obrigação **Manter a segurança de relatórios financeiros** podem excluir os relatórios de outros usuários. 

Na versão 10.0.8, o conceito de datas de vencimento foi introduzido. Um novo recurso necessário será habilitado na página **Todos** no espaço de trabalho gerenciamento de recursos. O recurso **Políticas de retenção de relatórios financeiros** contém as seguintes alterações:
* Os relatórios recém-gerados serão automaticamente marcados como tendo uma data de vencimento de 90 dias a partir do momento em que forem gerados.
* Todos os relatórios existentes antes da instalação do recurso receberão um período de vencimento de 90 dias. A data pode aparecer em branco por um breve período de tempo até que o serviço de relatórios financeiros esteja em execução, um relatório seja gerado e o serviço execute a atualização em relatórios existentes com uma data de vencimento em branco. 
* Os usuários com **Manter a segurança de relatórios financeiros** têm acesso a essa funcionalidade. Todos os usuários na obrigação **Manter relatórios financeiros** que tenham recebido o privilégio **Manter vencimento de relatórios financeiros** também terão a capacidade de modificar o período de vencimento. No momento, há duas opções de retenção disponíveis. 
  * Um vencimento de 90 dias.
  * Uma opção para configurar o relatório para nunca vencer.
  
Opções adicionais serão consideradas em futuras funcionalidades. O vencimento de 90 dias será o padrão, e os usuários com as permissões apropriadas poderão substituir o padrão na página de lista **Relatórios financeiros**.    
  
Quando um vencimento como 90 dias é selecionado, ele concede 90 dias a partir de hoje, o que é um comportamento diferente dos 90 dias a partir da data de geração original configurados durante a geração do relatório. 

## <a name="default-reports"></a>Relatórios padrão
Os relatórios financeiros fornecem 22 relatórios financeiros padrão. Cada relatório usa as categorias de conta principal padrão. Você pode usar esses relatórios da forma como são ou como um ponto de partida para os relatórios financeiros necessários. Além dos demonstrativos financeiros tradicionais, como o demonstrativo de renda e o balanço, esses relatórios incluem relatórios que mostram os diferentes tipos de relatórios financeiros que você pode criar. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Relatório padrão                                                                                         | Descrição                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Demonstrativo de Renda de Coluna Única de Rolagem de 12 Meses – Padrão | Exibir a lucratividade de uma organização para os últimos 12 meses em uma única coluna.                                                                                                                                                                                                                                      |
| Demonstrativo de Renda de Tendência de 12 Meses – Padrão                 | Exibir a lucratividade de uma organização para cada um dos últimos 12 meses. Esses 12 meses podem abranger mais do que um ano fiscal.                                                                                                                                                                                             |
| Real vs Orçamento – Padrão                                | Exibir informações detalhadas de saldo para todas as contas do orçamento original, e comparar o orçamento verificado com os valores reais que têm uma variação.                                                                                                                                                                          |
| Detalhes da Auditoria – Padrão                                  | Exibir informações de saldo detalhadas para todas as contas. Este relatório mostra os saldos de débito e crédito na moeda de relatório e na moeda local, juntamente com as informações de transação adicionais, como a ID do usuário, o usuário que modificou os dados por último, a data da última modificação, e a ID do diário. |
| Lista de Saldo – Padrão                                   | Exibir informações de saldo detalhadas para todas as contas. Este relatório mostra os saldos de abertura e fechamento, e os saldos de crédito e débito para o período atual e o ano até a data, juntamente com as informações de transação adicionais, como o comprovante.                                                                    |
| Balanço - Padrão                                   | Exibir a posição financeira da organização para o ano.                                                                                                                                                                                                                                                             |
| Balanço e Demonstrativo de Renda Lado a Lado - Padrão | Exibir a posição financeira e a lucratividade da organização para o ano lado a lado.                                                                                                                                                                                                                              |
| Fluxo de Caixa – Padrão                                       | Obter uma ideia do dinheiro que está entrando e saindo da organização.                                                                                                                                                                                                                                   |
| Revisão JE e TB Detalhada – Padrão                      | Exibir o saldo de abertura e as informações de atividade para todas as contas.                                                                                                                                                                                                                                                      |
| Balancete Detalhado - Padrão                         | Exibir informações de saldo para todas as contas que possuem saldos de crédito e débito, e a rede desses saldos, juntamente com a data da transação, comprovante, e descrição do diário.                                                                                                                                  |
| Tendência Trimestral de Três Anos de Despesas – Padrão             | Obter uma ideia das despesas dos últimos 12 trimestres dos três anos anteriores.                                                                                                                                                                                                                                   |
| Revisão JE e TB das Legendas Financeiras – Padrão            | Obter uma visão geral dos saldos e da atividade do ativo, responsabilidade, capital próprio do proprietário, receita, despesa, lucro, ou legendas financeiras de perdas.                                                                                                                                                                           |
| Demonstrativo de renda – Padrão                                | Exibir a lucratividade da organização para o período atual e o ano até o momento.                                                                                                                                                                                                                                   |
| Lista de Transações do Razão – Padrão                        | Exibir informações de saldo detalhadas para todas as contas. Este relatório mostra os saldos de crédito e débito, juntamente com as informações de transação adicionais, como a data da transação, número do diário, comprovante, tipo de lançamento, e número de rastreamento.                                                                            |
| Taxas – Padrão                                          | Exibir a solvência, lucratividade, e taxas de eficiência da organização para o ano.                                                                                                                                                                                                                           |
| Despesas de Rolagem de 12 Meses – Padrão                       | Obter uma ideia das despesas para cada um dos últimos 12 meses. Esses 12 meses podem abranger mais do que um ano fiscal.                                                                                                                                                                                                       |
| Demonstrativo de Renda do Trimestre de Rolagem – Padrão               | Exibir a lucratividade da organização trimestralmente para o ano passado e também para o ano até o momento.                                                                                                                                                                                                                   |
| Balanço Lado a Lado – Padrão                      | Exibir a posição financeira da organização para o ano. Este relatório mostra os ativos e o passivo, e o capital próprio de acionistas lado a lado.                                                                                                                                                                                |
| Resumo do Balancete – Padrão                          | Exibir informações sobre saldo para todas as contas que têm saldos de abertura e de fechamento, e saldos de débito e crédito com a diferença líquida.                                                                                                                                                                  |
| Resumo do Balancete Ano a Ano – Padrão           | Exibir informações sobre saldo para todas as contas que têm saldos de abertura e de fechamento, e saldos de débito e crédito junto com a diferença líquida para o ano atual e o ano passado.                                                                                                                           |
| Vendas e Descontos Semanais - Padrão                     | Obter uma ideia das vendas e descontos para cada semana em um mês. Esse relatório inclui um total de quatro semanas.                                                                                                                                                                                                              |
| Fundos de Orçamento Disponíveis - Padrão                         | Exibir uma comparação detalhada de orçamento revisado, despesas efetivas, reservas de orçamento e dos fundos de orçamento disponíveis para todas as contas                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Abrindo relatórios financeiros
Ao clicar no menu **Relatórios financeiros**, a lista de relatórios financeiros padrão da empresa será exibida. É possível abrir ou modificar um relatório. Para abrir um dos relatórios padrão, selecione o nome do relatório. Na primeira vez que um relatório for aberto, será gerado automaticamente para o mês anterior. Por exemplo, se você abrir um relatório pela primeira vez em agosto de 2016, o relatório é gerado para 31 de julho de 2016. Depois que um relatório for aberto, você pode começar a explorá-la ao aprofundamento de partes específicas de dados e alterar opções de relatório.

## <a name="creating-and-modifying-financial-reports"></a>Criando e modificando relatórios financeiros
Na lista de relatórios financeiros, você pode criar um novo relatório ou modificar um existente relatório. Se você tiver as permissões apropriadas, poderá criar um novo relatório financeiro clicando em **Novo** no painel de Ação. Um programa de designer de relatórios é baixado para seu dispositivo. Depois que o designer de relatórios for iniciado é possível criar o novo relatório. Depois de salvar o novo relatório, ele aparecerá na lista de relatórios financeiros. A lista mostra apenas os relatórios que foram criados para a empresa que você está usando no Finance. 

> [!NOTE] 
> O computador no qual você está baixando o cliente do designer de relatórios deve ter a versão 4.6.2 do Microsoft .NET Framework instalada. Esta versão do Microsoft .NET Framework pode ser baixada e instalada do [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53345). Se estiver usando o Chrome, instale uma extensão de ClickOnce para baixar o cliente de designer de relatórios. Se estiver executando no modo incógnito, verifique se a extensão de ClickOnce está habilitada para modo incógnito. Você também pode modificar um relatório que aparece na lista de relatórios financeiros. Quando a área em torno do nome do relatório é selecionada, clique em **Editar** no Painel de Ação. O Report Designer é inicializado.

## <a name="additional-resources"></a>Recursos adicionais
- [Exibir relatórios financeiros](view-financial-reports.md)




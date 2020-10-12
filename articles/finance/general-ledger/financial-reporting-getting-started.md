---
title: Visão geral dos relatórios financeiros
description: Este tópico descreve onde acessar relatórios financeiros no Microsoft Dynamics 365 Finance e como usar os recursos de relatório financeiro.
author: aprilolson
manager: AnnBe
ms.date: 09/22/2020
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
ms.openlocfilehash: a7cc238c573a319073b451063782762c19a80017
ms.sourcegitcommit: 28a771d81322e72d88db63a20ff360de084a6087
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3835101"
---
# <a name="get-started-with-financial-reporting"></a>Introdução ao Financial Reporting 

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
-   Ledger
-   Plano de Contas
-   Moeda

## <a name="granting-security-access-to-financial-reporting"></a>Conceder acesso de segurança ao Financial Reporting
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

Depois que um usuário é adicionado ou uma função é alterada, o usuário deve acessar os relatórios financeiros em alguns minutos. 

> [!NOTE]
> A função sysadmin foi adicionada a todas as funções no Financial Reporting.

## <a name="report-deletions-and-expirations"></a>Exclusão e vencimento de relatórios
Os usuários que geram um relatório podem excluir seus próprios relatórios. Os usuários com a obrigação **Manter a segurança de relatórios financeiros** podem excluir os relatórios de outros usuários. 

Na versão 10.0.8, foi introduzido o conceito de datas de vencimento. Um novo recurso necessário foi habilitado na página **Todos** do espaço de trabalho de gerenciamento de recursos. O recurso **Políticas de retenção de relatórios financeiros** contém as seguintes alterações:
* Os relatórios recém-gerados serão automaticamente marcados como tendo uma data de vencimento de 90 dias a partir do momento em que forem gerados.
* Todos os relatórios existentes antes da instalação do recurso receberão um período de vencimento de 90 dias. A data pode aparecer em branco por um breve período de tempo até que o serviço de relatórios financeiros esteja em execução, um relatório seja gerado e o serviço execute a atualização em relatórios existentes com uma data de vencimento em branco. 
* Os usuários com **Manter a segurança de relatórios financeiros** têm acesso a essa funcionalidade. Todos os usuários na obrigação **Manter relatórios financeiros** que tenham recebido o privilégio **Manter vencimento de relatórios financeiros** também terão a capacidade de modificar o período de vencimento. No momento, há duas opções de retenção disponíveis: 
  * Um vencimento de 90 dias.
  * Uma opção para configurar o relatório para nunca vencer.
  
Quando uma expiração, como 90 dias, é selecionada, ela é aplicada 90 dias a partir de hoje. Esse comportamento é diferente de 90 dias a partir da data da geração original definida quando o relatório foi gerado. 
  
Opções adicionais serão consideradas em futuras funcionalidades. O vencimento de 90 dias será o padrão, e os usuários com as permissões apropriadas poderão substituir o padrão na página de lista **Relatórios financeiros**.    

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
Quando você seleciona o menu **Relatórios financeiros**, é exibida a lista de relatórios financeiros padrão da empresa. É possível abrir ou modificar um relatório. Para abrir um dos relatórios padrão, selecione o nome do relatório. Na primeira vez que um relatório for aberto, será gerado automaticamente para o mês anterior. Por exemplo, se você abrir um relatório pela primeira vez em agosto de 2019, o relatório é gerado para 31 de julho de 2019. Depois que um relatório for aberto, você pode começar a explorá-la ao aprofundamento de partes específicas de dados e alterar opções de relatório.

## <a name="creating-and-modifying-financial-reports"></a>Criando e modificando relatórios financeiros
Na lista de relatórios financeiros, você pode criar um novo relatório ou modificar um existente relatório. Se você tiver as permissões apropriadas, poderá criar um novo relatório financeiro selecionando **Novo** no Painel de Ação. Um programa de designer de relatórios é baixado para seu dispositivo. Depois que o designer de relatórios for iniciado é possível criar o novo relatório. Depois de salvar o novo relatório, ele aparecerá na lista de relatórios financeiros. A lista mostra apenas os relatórios que foram criados para a empresa que você está usando no Dynamics 365 Finance. 

## <a name="reporting-tree-definitions"></a>Definições de árvore de relatórios 
Um dos componentes usados para criar relatórios financeiros é uma definição de árvore de relatórios. Uma relatório de definição de árvore ajuda a definir a estrutura e a hierarquia de sua organização. Você pode criar hierarquias em várias dimensões com base nas relações dimensionais nos dados financeiros. Ele fornece informações no nível de unidade de geração de relatórios e no nível de resumo para todas as unidades na árvore.

Você pode criar um número ilimitado de árvores de relatórios para exibir os dados da organização de várias formas. Cada árvore de relatórios pode conter qualquer combinação de departamentos e unidades de resumo, mas uma definição de relatório só pode ser vinculada a uma árvore de relatórios de cada vez. 


## <a name="troubleshooting-issues-opening-report-designer"></a>Solucionar problemas ao abrir o Designer de Relatórios
Existem alguns problemas comuns que podem causar transtornos quando você abre o Designer de Relatórios. Veja a seguir esses problemas e as etapas para solucioná-los.

Problema 1: o Designer de Relatórios não inicia quando você seleciona **Novo** ou **Editar**.

* No Internet Explorer, selecione **Configurações** e **Opções da Internet**. Selecione a guia **Segurança**, clique em Sites Confiáveis e selecione **Sites**. Em **Adicionar este site à zona**, insira "\*\.dynamics.com" (sem aspas) e selecione **Adicionar**. 
* No Internet Explorer, selecione **Configurações** e **Opções da Internet**. Selecione a guia **Segurança**. Selecione Sites Confiáveis. Na área Nível de segurança desta zona, mude a opção para **Médio-baixo**.
* Desabilite o bloqueador de pop-up no navegador.
* As estações de trabalho devem instalar o Microsoft .NET Framework 4.6.2 ou posterior. Esta versão do Microsoft .NET Framework pode ser baixada e instalada do [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53345).
* Se você usa o navegador Chrome, deve instalar uma extensão ClickOnce para baixar o cliente do Designer de Relatórios. Se estiver executando no modo anônimo, verifique se a extensão ClickOnce está habilitada para esse modo. Se você não conseguir entrar com o Chrome, tente seguir as etapas de configuração descritas em Problema 1 usando o Internet Explorer ou o Micrososft Edge. 

Problema 2: O usuário não recebeu as permissões necessárias para usar o Financial Reporting. 

* Para verificar se o usuário não tem permissão, selecione **Sim** no erro “Não é possível conectar ao servidor do Financial Reporting. Selecione Sim se deseja continuar e especifique outro endereço de servidor.” Depois selecione **Testar Conexão**. Se você não tiver permissão, verá uma mensagem informando "Falha na tentativa de conexão. O usuário não tem as permissões apropriadas para se conectar ao servidor. Entre em contato com o administrador do sistema.”
* As permissões necessárias estão listadas acima, em [Conceder acesso de segurança ao Financial Reporting](#granting-security-access-to-financial-reporting). A segurança no Financial Reporting se baseia nesses privilégios. Você só terá acesso se esses privilégios (ou a outra função de segurança que inclua esses privilégios) estiverem atribuídos a você. 
* A tarefa de integração **Provedor de Usuários da Empresa para Empresas** (que também é responsável por e conhecido como integração do usuário) é executada em um intervalo de 5 minutos. Pode levar até 10 minutos para as alterações de permissão entrarem em vigor no Financial Reporting. 
  Se outro usuário puder abrir o Designer de Relatórios, selecione **Ferramentas** e **Status de Integração**. Verifique se o mapa de integração, "Provedor de Usuários da Empresa para Empresas", foi executado com êxito porque você recebeu permissão para usar o Financial Reporting. 
* Pode ser possível que outro erro tenha impedido que a **Integração de usuário do usuário do Dynamics com o Financial Reporting**. Também é possível que uma redefinição do datamart tenha sido iniciada e ainda não foi concluída ou que outro erro do sistema tenha ocorrido. Tente executar o processo novamente mais tarde. Se o problema persistir, entre em contato com o administrador do sistema.

Problema 3: Você conseguirá passar pela página de entrada no Designer de Relatórios, mas não poderá entrar no Designer de Relatórios. 

* A hora definida no computador local quando você insere as credenciais de logon deve estar dentro de cinco minutos da hora no servidor do Financial Reporting. Se houver uma diferença de mais de cinco minutos, o sistema não permitirá a entrada. 
* Nesse caso, é recomendável habilitar a opção do Windows para definir a hora do PC automaticamente. 

## <a name="additional-resources"></a>Recursos adicionais
- [Exibir relatórios financeiros](view-financial-reports.md)
- [Definições da árvore de relatórios em relatórios financeiros](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)

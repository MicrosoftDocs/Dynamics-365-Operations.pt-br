---
title: Visão geral dos relatórios financeiros
description: Este tópico descreve onde acessar relatórios financeiros no Microsoft Dynamics 365 Finance e como usar os recursos de relatório financeiro.
author: aprilolson
ms.date: 03/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "10444"
- intro-internal
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1db676024f5ec0f254500bd2ceee85ab2150502
ms.sourcegitcommit: 777f9581dccc0f963c6a04c95b85e00e68573db5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8527303"
---
# <a name="get-started-with-financial-reporting"></a>Introdução aos Relatórios financeiros 

[!include [banner](../includes/banner.md)]

Este tópico descreve onde acessar o Financial reporting e como usar as capacidades do relatório financeiro. Ele também inclui uma descrição de relatórios financeiros padrão fornecidos.

## <a name="accessing-financial-reporting"></a>Avaliando relatórios financeiros

Você pode encontrar o menu **Relatórios financeiros** nos seguintes locais:

- **Contabilidade** &gt; **Consultas e relatórios**
- **Orçamento** &gt; **Consultas e relatórios** &gt; **Orçamento básico**
- **Orçamento** &gt; **Consultas e relatórios** &gt; **Planejamento de orçamento**
- **Orçamento** &gt; **Consultas e relatórios** &gt; **Controle de orçamento**
- Consolidações

Para criar e gerar relatórios financeiros para uma entidade legal, você deve configurar as informações a seguir para essa entidade legal:

- Calendário fiscal
- Ledger
- Plano de Contas
- Moeda
- Lançar uma transação em pelo menos uma conta
- MainAccount é listado na coluna **Selecionado** na página **Configuração do Financial Reporting** (**Contabilidade > Configuração do razão > Configuração do Financial Reporting**)

## <a name="granting-security-access-to-financial-reporting"></a>Conceder acesso de segurança ao Financial Reporting

As funções de relatórios financeiros estão disponíveis para os usuários que têm os privilégios e os direitos apropriados atribuídos a eles com as funções de segurança. As seções a seguir listam os privilégios e direitos, juntamente com as funções associadas.

### <a name="duties"></a>Direitos

| Rótulo do imposto                            | descrição                                                             | Nome de AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Manter a segurança de relatórios financeiros | Manter a segurança do Financial reporting e executar tarefas administrativas. | FinancialReportsSecurityMaintain |
| Manter relatórios financeiros            | Criar e manter relatórios financeiros.                                  | FinancialReportsMaintain         |
| Gerar relatórios financeiros            | Gerar e atualizar relatórios financeiros.                                 | FinancialReportsGenerate         |
| Rever o desempenho financeiro          | Rever e analisar o desempenho financeiro.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilégios

| Rótulo do privilégio                       | descrição                                                             | Nome de AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Manter a segurança de relatórios financeiros | Manter a segurança do Financial reporting e executar tarefas administrativas. | FinancialReportsSecuritySystemMaintain |
| Manter relatórios financeiros            | Criar e manter relatórios financeiros.                                  | FinancialReportsMaintainReports  |
| Gerar relatórios financeiros            | Gerar e atualizar relatórios financeiros.                                 | FinancialReportsGenerateReports  |
| Exibir relatórios financeiros                | Exibir relatórios financeiros.                                                 | FinancialReportsView             |

### <a name="roles"></a>Funções

| Rótulo do privilégio                       | Obrigação                                  | Funções                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Manter a segurança de relatórios financeiros | Manter a segurança do Financial reporting | Administrador de segurança                                                          |
| Manter relatórios financeiros            | Manter relatórios financeiros            | Gerente de Contabilidade, Supervisor de Contabilidade, Controlador Financeiro, Gerente de Orçamento |
| Gerar relatórios financeiros            | Gerar relatórios financeiros            | CEO, CFO, Contador                                                            |
| Exibir relatórios financeiros                | Rever o desempenho financeiro          | Nenhum atribuído                                                                   |

Depois que um usuário é adicionado ou que uma função é alterada, o usuário deve poder acessar o Financial Reporting em alguns minutos. 

> [!NOTE]
> A função sysadmin foi adicionada a todas as funções no Financial Reporting.

## <a name="report-deletions-and-expirations"></a>Exclusão e vencimento de relatórios

Os usuários que geram um relatório podem excluir seus próprios relatórios. Os usuários com a obrigação **Manter a segurança de relatórios financeiros** podem excluir os relatórios de outros usuários. 

Na versão 10.0.8, foi introduzido o conceito de datas de vencimento. Um novo recurso necessário foi habilitado na página **Todos** do espaço de trabalho de gerenciamento de recursos. O recurso **Políticas de retenção de relatórios financeiros** contém as seguintes alterações:
* Os relatórios recém-gerados serão automaticamente marcados como tendo uma data de vencimento de 90 dias a partir do momento em que forem gerados.
* Todos os relatórios existentes antes da instalação do recurso receberão um período de vencimento de 90 dias. A data pode aparecer em branco por um breve período de tempo até que o serviço Financial reporting esteja em execução, um relatório seja gerado e o serviço execute a atualização em relatórios existentes com uma data de vencimento em branco. 
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
| [Balancete Detalhado - Padrão](trial-balance-financial-reports.md)| Exibir informações de saldo para todas as contas que possuem saldos de crédito e débito, e a rede desses saldos, juntamente com a data da transação, comprovante, e descrição do diário.                                                                                                                                  |
| Tendência Trimestral de Três Anos de Despesas – Padrão             | Obter uma ideia das despesas dos últimos 12 trimestres dos três anos anteriores.                                                                                                                                                                                                                                   |
| Revisão JE e TB das Legendas Financeiras – Padrão            | Obter uma visão geral dos saldos e da atividade do ativo, responsabilidade, capital próprio do proprietário, receita, despesa, lucro, ou legendas financeiras de perdas.                                                                                                                                                                           |
| [Demonstrativo de renda – Padrão](income-statement-financial-report.md)| Exibir a lucratividade da organização para o período atual e o ano até o momento.                                                                                                                                                                                                                                   |
| Lista de Transações do Razão – Padrão                        | Exibir informações de saldo detalhadas para todas as contas. Este relatório mostra os saldos de crédito e débito, juntamente com as informações de transação adicionais, como a data da transação, número do diário, comprovante, tipo de lançamento, e número de rastreamento.                                                                            |
| Taxas – Padrão                                          | Exibir a solvência, lucratividade, e taxas de eficiência da organização para o ano.                                                                                                                                                                                                                           |
| Despesas de Rolagem de 12 Meses – Padrão                       | Obter uma ideia das despesas para cada um dos últimos 12 meses. Esses 12 meses podem abranger mais do que um ano fiscal.                                                                                                                                                                                                       |
| Demonstrativo de Renda do Trimestre de Rolagem – Padrão               | Exibir a lucratividade da organização trimestralmente para o ano passado e também desde o início do ano.                                                                                                                                                                                                                   |
| Balanço Lado a Lado – Padrão                      | Exibir a posição financeira da organização para o ano. Este relatório mostra os ativos e o passivo, e o capital próprio de acionistas lado a lado.                                                                                                                                                                                |
| [Resumo do Balancete – Padrão](trial-balance-financial-reports.md)| Exibir informações sobre saldo para todas as contas que têm saldos de abertura e de fechamento, e saldos de débito e crédito com a diferença líquida.                                                                                                                                                                  |
| [Resumo do Balancete Ano a Ano – Padrão](trial-balance-financial-reports.md)| Exibir informações sobre saldo para todas as contas que têm saldos de abertura e de fechamento, e saldos de débito e crédito junto com a diferença líquida para o ano atual e o ano passado.                                                                                                                           |
| Vendas e Descontos Semanais - Padrão                     | Obter uma ideia das vendas e descontos para cada semana em um mês. Esse relatório inclui um total de quatro semanas.                                                                                                                                                                                                              |
| Fundos de Orçamento Disponíveis - Padrão                         | Exibir uma comparação detalhada de orçamento revisado, despesas efetivas, reservas de orçamento e dos fundos de orçamento disponíveis para todas as contas                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Abrindo relatórios financeiros

Quando você seleciona o menu **Relatórios financeiros**, é exibida a lista de relatórios financeiros padrão da empresa. É possível abrir ou modificar um relatório. Para abrir um dos relatórios padrão, selecione o nome do relatório. Na primeira vez que um relatório for aberto, será gerado automaticamente para o mês anterior. Por exemplo, se você abrir um relatório pela primeira vez em agosto de 2019, o relatório é gerado para 31 de julho de 2019. Depois que um relatório for aberto, você pode começar a explorá-la ao aprofundamento de partes específicas de dados e alterar opções de relatório.

## <a name="creating-and-modifying-financial-reports"></a>Criando e modificando relatórios financeiros

Na lista de relatórios financeiros, você pode criar um novo relatório ou modificar um existente relatório. Se você tiver as permissões apropriadas, poderá criar um novo relatório financeiro selecionando **Novo** no Painel de Ação. Um programa de designer de relatórios é baixado para seu dispositivo. Depois que o designer de relatórios for iniciado é possível criar o novo relatório. Depois de salvar o novo relatório, ele aparecerá na lista de relatórios financeiros. A lista mostra apenas os relatórios que foram criados para a empresa que você está usando no Dynamics 365 Finance. 

## <a name="reporting-tree-definitions"></a>Definições de árvore de relatórios

Um dos componentes usados para criar relatórios financeiros é uma definição de árvore de relatórios. Uma relatório de definição de árvore ajuda a definir a estrutura e a hierarquia de sua organização. Você pode criar hierarquias em várias dimensões com base nas relações dimensionais nos dados financeiros. Ele fornece informações no nível de unidade de geração de relatórios e no nível de resumo para todas as unidades na árvore.

Você pode criar um número ilimitado de árvores de relatórios para exibir os dados da organização de várias formas. Cada árvore de relatórios pode conter qualquer combinação de departamentos e unidades de resumo, mas uma definição de relatório só pode ser vinculada a uma árvore de relatórios de cada vez. 

## <a name="update-the-financial-reporting-version-through-slipstreaming"></a>Atualizar a versão do Financial reporting com a integração

Os aplicativos de finanças e operações são atualizados todos os meses. No entanto, o Financial reporting não é necessariamente atualizado nessa cadência. Além disso, os clientes têm mais opções sobre ao implementar atualizações para aplicativos de finanças e operações. As atualizações do Financial reporting são instaladas automaticamente. O Financial reporting tem uma versão designada consumida em um ambiente de cliente quando uma atualização de serviço é implementada, quando o tempo de inatividade é iniciado ou quando o ambiente de um cliente está em modo de Manutenção. Esse processo é conhecido como *correção* ou *real*, pois todas as implementações de clientes são definidas como a mesma versão do Financial reporting.

As alterações liberadas em cada versão podem ser encontradas em [Novidades ou alterações no Dynamics 365 Finance](../../finance/get-started/whats-new-home-page.md). As atualizações de plataforma e correção de bugs podem ser encontradas na seção "Recursos Adicionais", na parte inferior da página, para cada liberação.

A versão corrigida selecionada é uma versão revisada e validada do Financial reporting que está pronto para produção. Ele é compatível com qualquer versão anterior ou futura do Dynamics 365 Finance. Por exemplo, o Financial reporting pode estar na compilação de 10.0.19 mais recente enquanto o cliente ainda está na versão do aplicativo 10.0.16.

> [!NOTE]
> A única circunstância em que os clientes podem mudar para uma versão anterior (um cenário de downgrade) ocorre se a Microsoft parar uma distribuição de verdadeira devido a um problema. Assim que uma correção estiver disponível, ela será aplicada automaticamente.

O processo de correção é totalmente automatizado e não requer nenhuma ação do cliente. Três topologias consomem correção, cada um de uma forma ligeiramente diferente:

- **Locais** – as implantações locais não oferecem suporte à correção e ao real.
- **Infraestrutura como serviço (IaaS)** – a lógica de correção é aplicada durante qualquer operação que tenta atualizar o Financial reporting. Inclui atualizações binárias ou transmissões que contêm atualizações binárias.
- **Auto-atendimento** – qualquer operação que exija inatividade do Financial reporting se aplica a lógica de correção:

    - Atualizações binárias ou transmissões que têm atualizações binárias
    - Patch S ou outro tempo de inatividade da infraestrutura
    - Implantações do pacote de AOT

## <a name="troubleshooting-issues-opening-report-designer"></a>Solucionar problemas ao abrir o Designer de Relatórios

Existem alguns problemas comuns que podem causar transtornos quando você abre o Designer de Relatórios. Veja a seguir esses problemas e as etapas para solucioná-los.

Problema 1: o Designer de Relatórios não inicia quando você seleciona **Novo** ou **Editar**.

* No Internet Explorer, selecione **Configurações** e **Opções da Internet**. Selecione a guia **Segurança**, clique em Sites Confiáveis e selecione **Sites**. Em **Adicionar este site à zona**, insira "\*\.dynamics.com" (sem aspas) e selecione **Adicionar**. 
* No Internet Explorer, selecione **Configurações** e **Opções da Internet**. Selecione a guia **Segurança**. Selecione Sites Confiáveis. Na área Nível de segurança desta zona, mude a opção para **Médio-baixo**.
* Desabilite o bloqueador de pop-up no navegador.
* As estações de trabalho devem instalar o Microsoft .NET Framework 4.7.2 ou posterior. Esta versão do Microsoft .NET Framework pode ser baixada e instalada do [Centro de Download da Microsoft](https://dotnet.microsoft.com/download/dotnet-framework/net472).
* Se você estiver usando o navegador Chrome, deverá instalar uma extensão ClickOnce para baixar o cliente do Designer de Relatórios. Se estiver executando no modo incógnito do Chrome, verifique se a extensão de ClickOnce está habilitada para modo incógnito. Para obter mais informações sobre a Extensão ClickOnce do Chrome, consulte [Requisitos de sistema para implantações na nuvem](../../fin-ops-core/fin-ops/get-started/system-requirements.md).
* Se você estiver usando o Microsoft Edge com um navegador Chrome, não será necessário instalar uma extensão ClickOnce para o Edge Chromium. No entanto, você deve habilitar a opção ClickOnce a fim de baixar o cliente do Designer de Relatórios. Se estiver executando no modo anônimo, verifique se a extensão ClickOnce está habilitada para esse modo.

    1. Abra um novo navegador no Microsoft Edge.
    2. Insira **edge://flags** e selecione **Enter**.
    3. Procure a opção de **Suporte do ClickOnce** ou use este link direto: **edge://flags/#edge-click-once**.
    4. Defina a opção de menu suspenso como **Habilitado**.
    5. Selecione **Reiniciar Navegador**.

Problema 2: o usuário não recebeu as permissões necessárias para usar o Financial reporting. 

* Para verificar se o usuário não tem permissão, selecione **Sim** no erro "Não é possível conectar ao servidor do Financial Reporting. Selecione Sim se deseja continuar e especifique outro endereço de servidor." Depois selecione **Testar Conexão**. Se você não tiver permissão, verá uma mensagem informando "Falha na tentativa de conexão. O usuário não tem as permissões apropriadas para se conectar ao servidor. Entre em contato com o administrador do sistema."
* As permissões necessárias estão listadas acima, em [Conceder acesso de segurança ao Financial Reporting](#granting-security-access-to-financial-reporting). No Financial Reporting, a segurança se baseia nesses privilégios. Você só terá acesso se esses privilégios (ou a outra função de segurança que inclua esses privilégios) estiverem atribuídos a você. 
* A tarefa de integração **Provedor de Usuários da Empresa para Empresas** (que também é responsável por e conhecido como integração do usuário) é executada em um intervalo de 5 minutos. Pode levar até 10 minutos para as alterações de permissão entrarem em vigor no Financial reporting. 

    Se outro usuário puder abrir o Designer de Relatórios, selecione **Ferramentas** e **Status de Integração**. Verifique se o mapa de integração, "Provedor de Usuários da Empresa para Empresas", foi executado com êxito porque você recebeu permissão para usar o Financial reporting. 

* Pode ser possível que outro erro tenha impedido que a **Integração de usuário do usuário do Dynamics com o Financial Reporting** termine. Também é possível que uma redefinição do datamart tenha sido iniciada e ainda não foi concluída ou que outro erro do sistema tenha ocorrido. Tente executar o processo novamente mais tarde. Se o problema persistir, entre em contato com o administrador do sistema.

Problema 3: Você conseguirá passar pela página de entrada no **ClickOnce Report Designer**, mas não poderá entrar no Designer de Relatórios. 

* A hora definida no computador local quando você insere as credenciais de logon deve estar dentro de cinco minutos da hora no servidor do Financial reporting. Se houver uma diferença de mais de cinco minutos, o sistema não permitirá a entrada. 
* Se a hora no computador for diferente da hora no servidor do Financial Reporting, recomendamos habilitar a opção do Windows para definir o horário do computador automaticamente. 

## <a name="troubleshoot-report-designer-issues-with-event-viewer"></a>Solucionar problemas do Report Designer com o Visualizador de eventos

Você pode usar o Visualizador de eventos para analisar alguns dos problemas que surgem durante o uso do Financial Reporting. 

### <a name="what-happens-when-you-have-connections-issues-with-financial-reporting"></a>O que acontece quando você tem problemas para se conectar ao Financial Reporting? 

Veja aqui algumas etapas que você pode seguir para tornar a conversa com o suporte da Microsoft mais eficaz e conseguir uma resolução mais rápida. 
 
As etapas a seguir mostram em detalhes o processo de ativar as mensagens do Visualizador de eventos para o Financial Reporting. Os logs gerados pelo Visualizador de eventos ajudarão os engenheiros de suporte a identificar a origem do problema de conexão rapidamente. Envie cópias desses logs junto com o tíquete quando entrar em contato com o suporte.


1. Copie o arquivo RegisterETW.zip para a estação de trabalho do cliente (preferivelmente na área de trabalho) e extraia [RegisterETW.zip](https://dev.azure.com/msdyneng/e6f12261-a46a-4af1-ac0c-e22bc2c5a478/_apis/git/repositories/ff923027-67f0-43fb-b63c-6d6b6423840f/Items?path=%2F.attachments%2FRegisterETW-c1a35291-6aa6-4462-a2bc-4ba117fd5f8e.zip&download=false&resolveLfs=true&%24format=octetStream&api-version=5.0-preview.1&sanitize=true&versionDescriptor.version=wikiMaster).
2. Verifique se o Visualizador de eventos do Windows está fechado.
3. Abra um prompt de comando como Administrador do PowerShell e Acesse o diretório onde está o arquivo RegisterETW.ps1.
4. Execute o seguinte comando: .\RegisterETW.ps1

    Uma saída bem-sucedida no PowerShell será verificada com a mensagem **Script RegisterETW concluído**.

    Abra novamente o Visualizador de eventos e você verá agora estes logs no **Microsoft > Dynamics**:

    * MR-Client
    * MR-DVT
    * MR-Integration
    * MR-Logger
    * MR-Reporting
    * MR_SchedulerTasks
    * MR-Sql
    * MR-TraceManager

5. Reproduza o problema no Report Designer.
6. Exporte os eventos de MR-Logger usando o Visualizador de eventos.

## <a name="troubleshoot-issues-connecting-to-financial-reporting"></a>Solucionar problemas de conexão com o Financial Reporting

Problema: Você recebe o erro "Não é possível conectar ao servidor do Financial Reporting".

* Determine se o problema ocorre nos navegadores da Internet Chrome e Edge.
* Se ocorrer apenas em um navegador, poderá ser um problema do ClickOnce. 
* Quando receber a mensagem de erro de conexão, selecione **Testar** para testar a conexão e ver qual mensagem é exibida. 
* O problema pode ser decorrente do fato de que outro usuário não está tendo acesso ao Financial Reporting. Se um usuário não tiver acesso, receberá uma mensagem informando que ele não tem permissão.
* Se o problema ocorrer em vários navegadores, verifique se o relógio da estação de trabalho está definido como automático.
* Trabalhe com um usuário que tenha direitos de administrador de segurança no Dynamics 365 Finance e direitos de administrador no domínio de rede para se conectar à estação de trabalho e verificar se ele consegue se conectar. Se ele conseguir se conectar, o problema pode estar relacionado às permissões de rede.
* Na estação de trabalho, desabilite o firewall temporariamente. Se desse modo você conseguir se conectar ao Report Designer, o problema estará no firewall. Entre em contato com o departamento de TI da organização para resolver o problema.

## <a name="additional-resources"></a>Recursos adicionais

- [Exibir relatórios financeiros](view-financial-reports.md)
- [Definições da árvore de relatórios em relatórios financeiros](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

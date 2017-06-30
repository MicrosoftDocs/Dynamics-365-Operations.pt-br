---
title: "O que há de novo ou diferente no Dynamics AX 7.0 (fevereiro de 2016)"
description: "Este artigo descreve os recursos novos ou alterados na versão 7.0 do Microsoft Dynamics. Esta versão contém recursos de plataforma e aplicativos e foi lançada em fevereiro de 2016."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 91243
ms.assetid: 515bc6e7-a85d-4995-95c6-6cab6c8aa0f9
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: aba59096bf1ffc9ce6448cb7c0f9bd5d2936d7d7
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="whats-new-or-changed-in-dynamics-ax-70-february-2016"></a>O que há de novo ou diferente no Dynamics AX 7.0 (fevereiro de 2016)

[!include[banner](../includes/banner.md)]


Este artigo descreve os recursos novos ou alterados na versão 7.0 do Microsoft Dynamics. Esta versão contém recursos de plataforma e aplicativos e foi lançada em fevereiro de 2016.

<a name="cost-management"></a>Gerenciamento de custo
---------------

<table>

<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Obtenha uma rápida visão geral do saldo de estoque, do saldo de estoque do trabalho em andamento (WIP), e sobre quais foram as entradas e saídas do estoque durante o ano fiscal selecionado.</td>
<td>Não aplicável</td>
<td>O espaço de trabalho <strong>Administração de custo</strong> contém uma seção na qual o demonstrativo de estoque ou o demonstrativo de estoque do WIP é apresentado para o período fiscal selecionado. O demonstrativo é baseado em um cache de conjunto de dados que, por padrão, é atualizado a cada 24 horas. O cache de conjunto de dados pode ser configurado para que usuários possam atualizá-lo manualmente para relatórios em tempo real. O <strong>Cartão de status da atualização de dados</strong> no espaço de trabalho <strong>Administração de custo</strong> mostra quando o cache foi atualizado pela última vez.</td>
<td>Os controladores de custo estão interessados em saber se o saldo do estoque ou do demonstrativo de estoque do WIP aumenta ou diminui ao longo do tempo. Ao classificar eventos operacionais no demonstrativo, o controlador de custo pode obter uma visão geral do fluxo de estoque. Se o estoque ou o estoque WIP é avaliado por custos padrão, a variação geral registrada também pode ser vista.</td>
</tr>
<tr class="odd">
<td>Use o módulo<strong> Gerenciamento de custo</strong>.</td>
<td>Não aplicável</td>
<td>O gerenciamento de custo é apresentado como uma área de domínio. As informações e configurações relacionadas a custos foram divididas em Gerenciamento de estoque, Controle de produção e Contas a pagar.</td>
<td>Como todas as tarefas relacionadas a gerenciamento de custo estão centralizadas em um módulo, será mais fácil para os controladores de custo manter o sistema.</td>
</tr>
<tr class="even">
<td>Os tipos de lançamento relacionados a contabilidade de estoque e produção foram atualizados.</td>
<td>Os rótulos nos formulários <strong>InventPosting</strong>, <strong>Resource</strong>, <strong>ResourceGroup</strong>, e <strong>ProductionGroup</strong> nem sempre estão alinhados com os rótulos <strong>LedgerPostingType</strong> que de fato são usados. Não é fácil entender a terminologia usada nos rótulos.</td>
<td>Os rótulos foram atualizados para que os rótulos nas páginas <strong>InventPosting</strong>, <strong>Resource</strong>, <strong>ResourceGroup</strong> e <strong>ProductionGroup</strong> correspondam aos rótulos <strong>LedgerPostingType</strong> reais. Todos os rótulos também foram renomeados para que correspondam aos eventos operacionais. Observe que a lógica de lançamento real não foi alterada.</td>
<td>É mais fácil configurar o sistema, já que os novos rótulos estão relacionados aos eventos operacionais que usam esse tipo de lançamento.</td>
</tr>
<tr class="odd">
<td>Importar/exportar o preço de compra, custo, ou preço de venda do Microsoft Excel para ou de uma versão de avaliação de custo.</td>
<td>Você não consegue importar preços ou custos corretamente para uma versão de avaliação de custo, pois o modelo de dados requer uma ID de InventDim.</td>
<td>A introdução das entidades de dados possibilita a implementação de um recurso de exportação/importação. Esse recurso permite aos usuários importar/exportar preços ou custos para uma versão de avaliação de custo.
<ul>
<li>Importe uma lista completa dos preços de compra do próximo ano que é obtida no departamento de compras.</li>
<li>Envie por push os custos ou preços de venda padrão das matrizes a uma ou mais empresas de vendas em uma operação.</li>
</ul></td>
<td>Permite que os controladores de custo economizem uma quantidade significativa de tempo ao manterem o sistema, especialmente ao manterem custos predeterminados para o próximo ano fiscal.</td>
</tr>
<tr class="even">
<td>Obtenha uma rápida visão geral do saldo de estoque e custo unitário médio de um objeto de custo.</td>
<td>O usuário deve abrir o formulário disponível e selecionar as dimensões de estoque que refletem o objeto de custo. Portanto, o usuário deve saber quais dimensões de estoque foram marcadas para o estoque financeiro do produto específico.</td>
<td>Uma nova página <strong>Objeto de custo</strong> é introduzida. Por padrão, essa página mostra todos os objetos de custo que estão relacionados ao produto. A página mostra a quantidade de estoque, o valor e o custo unitário médio atuais por objeto de custo.</td>
<td>Diminui um pouco da complexidade e facilita a tarefa de ser controlador de custo.</td>
</tr>
<tr class="odd">
<td>Use a nova página <strong>Entradas de custo</strong> durante o controle de estoque.</td>
<td>Pode ser complicado realizar o controle de estoque nas transações de estoque registradas e liquidações relacionadas, porque as mesmas transações podem ser físicas ou financeiras.</td>
<td>A página <strong>Entradas de custo</strong> permite que você exiba transações de estoque de uma nova forma.
<ul>
<li>As transações são mostradas em ordem cronológica.</li>
<li>Apenas as transações que contribuem para custos são incluídas.</li>
<li>Não há noção de custos físicos ou financeiros.</li>
<li>Não há noção de quantidade física ou financeira.</li>
<li>Os custos são adicionados gradativamente.</li>
</ul></td>
<td>Permite que os controladores de custo economizem uma quantidade significativa de tempo ao realizarem o controle de estoque no nível de transação.</td>
</tr>
<tr class="even">
<td>Use a nova caixa de diálogo <strong>Demonstrativo do WIP de produção</strong> para visualizar uma exibição resumida dos custos acumulados para um produto específico.</td>
<td>Não aplicável</td>
<td>O demonstrativo do WIP mostra um resumo de saldo de WIP da ordem de produção específica, agrupada em classificações de custo apropriadas. Um gráfico mostra, em ordem cronológica, como os lançamentos operacionais afetaram o saldo do WIP.</td>
<td>Isso pode poupar uma quantia significativa de tempo dos controladores de custo, quando eles precisam saber qual é o saldo atual do WIP em uma ordem de produção específica, ou quanto material foi consumido na ordem.</td>
</tr>
<tr class="odd">
<td>Use o recurso Exibir comparação de custo que foi introduzido nas ordens de produção. O recurso facilita a comparação de custos relacionados a uma ordem de produção.</td>
<td>O usuário pode comparar apenas custos estimados e realizados. A comparação pode ser feita no menor nível.</td>
<td>O recurso de comparação de custos permite que os controladores comparem os seguintes dados:
<ul>
<li>Custo ativo x custo estimado = variação de planejamento</li>
<li>Custo estimado x custo realizado = variação de produção</li>
<li>Variação de planejamento + variação de produção = variação total</li>
</ul>
Esse recurso funciona independentemente dos métodos de avaliação de custo atribuídos ao item do produto. Por padrão, um gráfico mostra a comparação de custos por tipo de grupo de custo. O gráfico permite que os usuários analisem níveis mais detalhados.</td>
<td>Permite que os controladores de custo ou gerentes de produção analisem as origens e causas das variações de produção.</td>
</tr>
</tbody>
</table>

## <a name="developer"></a>Desenvolvedor
|                                                                                                              |                                                                                                                                                                                                    |                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                                                         | **Dynamics AX 2012**                                                                                                                                                                               | **Dynamics AX 7.0**                                                                                                                                                                                                            | **Por que isso é importante?**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Crie soluções baseadas na Web na nuvem que possam ser acessadas em muitos dispositivos.                                 | Não disponível                                                                                                                                                                                      | A versão atual do Dynamics AX baseia-se em um novo cliente baseado na Web e estrutura de cliente.                                                                                                                                    | Você pode fornecer a próxima geração de soluções a seus usuários finais.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Use o Microsoft Visual Studio para desenvolver suas soluções.                                                       | O Microsoft MorphX é o principal ambiente de desenvolvimento, mas uma parte do desenvolvimento pode ser feita no Visual Studio.                                                                                                | O Visual Studio é o único ambiente de desenvolvimento.                                                                                                                                                                             | Mantém conceitos familiares do Dynamics AX 2012, adaptando-os perfeitamente à estrutura e aos paradigmas do Visual Studio. Permite a interoperabilidade padrão com outros projetos e linguagens .NET.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Compile o CIL (Common Intermediate Language) para outros recursos.                                                 | X++ é compilado para p-code.                                                                                                                                                                         | O novo compilador X++ gera CIL para todos os recursos. A CIL é a mesma linguagem intermediária usada por outras linguagens baseadas em .NET.                                                                                   | A CIL é mais rápida, pode referenciar eficientemente as classes nas bibliotecas de link dinâmico (DLLs) gerenciadas e pode ser executada em uma ampla base de ferramentas de utilitários .NET.                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Relatórios e visualizações de BI integrados no cliente do Microsoft Dynamics AX.             | Não disponível                                                                                                                                                                                      | Crie visualizações altamente intuitivas e fluidas.                                                                                                                                                                              | Fornece informações para tomada de decisão baseadas em BI.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Integra-se com o Microsoft Office.                                                                             | Não disponível                                                                                                                                                                                      | Os novos recursos incluem o aplicativo Excel Data Connector, a página **Designer de pastas de trabalho**, Export API e Gerenciamento de documentos.                                                                                                        | É possível criar soluções de produtividade para seus usuários finais.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Automatize a criação, teste e implantação.                                                                            | Parcialmente disponível                                                                                                                                                                                | Implante a Topologia do desenvolvedor usando Desenvolvedor e Criar VM. Configure automaticamente Criar VM para fazer descobertas, criar módulos no Visual Studio Online (VSO) e executar testes. Compilação e referências do módulo C\# e X++ são compatíveis. | Aumenta a produtividade do desenvolvedor reduzindo custos e esforços em testes e validações.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Faça personalizações com sobreposições e extensões.                                                                  | As extensões não estão disponíveis.                                                                                                                                                                       | A versão atual do Dynamics AX apresenta um novo modelo de personalização.                                                                                                                                                              | Você pode personalizar o código-fonte e os metadados dos elementos do modelo que são emitidos pela Microsoft ou por parceiros terceirizados da Microsoft.                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Crie novos controles e elementos de interface de usuário usando X++ e uma estrutura da Web moderna.                                  | Controles personalizados dependem de estruturas externas, como o Microsoft ActiveX e Windows Presentation Foundation (WPF).                                                                                   | É mais fácil criar controles na versão atual. A estrutura X++ pode ser usada em comportamento de aplicativo e lógica comercial, e um cliente baseado em HTML/JavaScript permite visualizações modernas.                         | Seus controles podem ser projetados para ter aparência e comportamento semelhantes aos controles fora-da-caixa (OOB) do Dynamics AX.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Avalie e ajuste o desempenho usando novas ferramentas.                                                            | PerfSDK, Kit de Ferramentas de Expansão de Dados, aplicativo Web Trace Parser e PerfTimer não estão disponíveis.                                                                                                             | PerfSDK, Kit de Ferramentas de Expansão de Dados, aplicativo Web Trace Parser e PerfTimer são novos.                                                                                                                                                  | O SDK (Software Development Kit) permite testar e validar processos de negócios para desempenho em uma execução de teste de usuário único e, se aplicável, de vários usuários. O Kit de Ferramentas de Expansão de Dados permite que você expanda corretamente todos os testes de desempenho que precisam ter dados mestres e dados transacionais corretamente expandidos. O Trace Parser permite validar execuções de teste de desempenho de um único usuário ou de vários usuários. O PerfTimer permite verificar se qualquer consulta ou chamada de método específica está causando problemas de desempenho. Portanto, não é necessário acompanhar e analisar tudo detalhadamente. |
| Exponha uma exibição atualizável usando OData.                                                                        | Não disponível                                                                                                                                                                                      | A versão atual do Dynamics AX apresenta um ponto de extremidade do serviço OData que permite acesso a dados do Dynamics AX de forma consistente em vários clientes.                                                     | Suas soluções podem interagir com os serviços RESTful, compartilhar dados de forma perceptível e permitir uma ampla integração usando a pilha de protocolos HTTP.                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Aproveite o business connector para criar lógica de negócios e oferecer suporte a cenários de integração.         | O conector de negócios está disponível para chamar o código X ++ do código gerenciado. Recomendamos que você use o conector de negócios somente para criar a lógica comercial no C\#, não para cenários de integração. | O business connector não é mais compatível. O requerimento de criação é fornecido pelo fato de que o X++ é compilado no código gerenciado. Portanto, o interop será mais fácil. Os cenários de integração são atendidos por meio de OData.       | Você não pode usar o business connector daqui para a frente.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Escolha a escala (ou seja, o número de casas decimais) em campos de banco de dados reais e tipos de dados estendidos (EDTs). | A escala 16 é a padrão e não pode ser alterada pelo desenvolvedor.                                                                                                                               | Agora EDTs e campos têm uma propriedade de escala que pode ser aplicada ao campo e EDT individuais. O padrão é definido como 6, não 16.                                                                                                | O desempenho com tabelas NCCI (suporte de memória no SQL) é mais rápido por ordens de magnitude quando uma escala menor é usada. Altere a escala conforme sua necessidade de uso dos campos individuais.                                                                                                                                                                                                                                                                                                                                                                                                               |
## <a name="financial-management"></a>Gerenciamento financeiro
<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Exporte as estruturas de conta para o Microsoft Excel.</td>
<td>Não disponível</td>
<td>Agora é possível selecionar uma estrutura de conta e exportá-la para o Excel.</td>
<td>Muitos clientes solicitaram a capacidade de exportar estruturas de conta para o Excel para tornar a filtragem mais fácil.</td>
</tr>
<tr class="odd">
<td>Exiba razões e estruturas de regras avançados que estão associados a uma estrutura de conta em uma única página.</td>
<td> O usuário deve explorar diversos formulários para visualizar o livro razão e a estrutura de conta usados. </td>
<td>Os Quadros de Fatos foram adicionados à página da estrutura de conta.</td>
<td>É mais fácil acessar informações importantes quando as estruturas de conta estão definidas e editadas.</td>
</tr>
<tr class="even">
<td>Exiba os razões associados a um gráfico de contas em uma única página.</td>
<td>O usuário deve explorar cada empresa e abrir o formulário de contabilidade para ver o gráfico de contabilidade atribuído ao razão.</td>
<td>FactBoxes foram adicionadas à página **Plano de contas**.</td>
<td> É mais fácil acessar informações importantes quando um plano de contas está definido e atribuído.</td>
</tr>
<tr class="odd">
<td>Exiba ajustes de planilhas e transações de fechamento em colunas separadas na página de listagem **Balancete**. </td>
<td>O usuário vê ambos os tipos de transações em uma única coluna.</td>
<td>Um parâmetro adicional foi incluído na página de listagem **Balancete**.</td>
<td>Permite análises de dados mais concisas e também é necessário para relatório de regulamentação em alguns países/regiões. </td>
</tr>
<tr class="even">
<td>Utilize a nova página **Diário geral global**.</td>
<td>Não disponível </td>
<td>Nova página **Diário geral global** para inserir diários gerais. Os privilégios para essa página são adicionados à função **Contador**.</td>
<td>Torna possível para um contador de serviço compartilhado inserir diários gerais entre as empresas sem a necessidade de deixar o formulário ou alternar o contexto da empresa.</td>
</tr> 
<tr class="odd">
<td>Use a nova página **Navegador fonte de contabilidade**.</td>
<td>Disponível no Dynamics AX 2012 R3 CU10.</td>
<td>Nova página **Navegador fonte de contabilidade** e ações para navegar nela a partir da página de listagem **Balancete** e da página **Transações de comprovante**.</td>
<td>Torna possível visualizar as informações mais detalhadas sobre a fonte para um balancete ou uma entrada contábil na contabilidade, ou para análise ad-hoc.</td>
</tr>
<tr class="even">
<td>Adicione níveis de lançamento adicionais.</td>
<td>Adicionar níveis de lançamento adicionais foi uma experiência de desenvolvedor.</td>
<td>Dez níveis de lançamento estão disponíveis agora.</td>
<td>A maioria dos clientes adiciona níveis de lançamento adicionais.</td>
</tr>
<tr class="odd">
<td>Utilize a opção Comprovante relacionado.</td>
<td>Não disponível</td>
<td>A opção de Comprovante relacionado está disponível para que os usuários visualizem o comprovante na empresa de compensação ao lançar transações entre empresas. A partir dos comprovantes relacionados, os usuários podem clicar nos detalhes e acessar rapidamente o comprovante da empresa de compensação.</td>
<td>Ao lançar transações entre empresas, os usuários não tinham visibilidade ou rastreamento do comprovante lançado na empresa de compensação.</td>
</tr>
<tr class="even">
<td>Fechamento em massa de períodos financeiros</td>
<td>Não disponível</td>
<td>Os usuários são capazes de atualizar o acesso ao módulo e alterar o status do período para várias empresas ao mesmo tempo.</td>
<td>Antes do recurso, os usuários tinham que alterar a empresa em que estavam conectados, navegar até o formulário de calendário do razão e atualizar manualmente o acesso ao módulo e o status do período.</td>
</tr>
<tr class="odd">
<td>Tenha taxas de câmbio alimentadas pela Oanda.</td>
<td>Configurar o provedor de taxa de câmbio para importar taxas da Oanda foi uma experiência de desenvolvedor. </td>
<td>Se os usuários possuem uma chave para o Oanda eles podem inseri-lá ao configurar o provedor de taxa de câmbio.</td>
<td>Os usuários podem tirar proveito da funcionalidade fora-da-caixa ao ter as taxas de câmbio alimentadas pela Oanda importadas de maneira programada.</td>
</tr>
<tr class="even">
<td>Filtre relatórios financeiros (Relator de Gerenciamento) com base nas dimensões, atributos, datas e cenários. </td>
<td> Toda a filtragem dos relatórios do Management Reporter é gerenciada por meio do design do relatório. Por exemplo, se um usuário que possui privilégios de exibição deseja visualizar um relatório para uma data diferente, um designer de relatórios deve realizar a modificação. </td>
<td>As opções de relatório foram adicionadas, de modo que diferentes filtros podem ser aplicados quando um usuário está visualizando um relatório. Um novo relatório é gerado na base dos filtros.</td>
<td>Usuários de relatórios financeiros podem aplicar diferentes filtros para dimensões, datas, atributos e cenários sem a necessidade de atualizações para designs de relatório.</td>
</tr>
<tr class="odd">
<td>Exiba relatórios financeiros (Relator de Gerenciamento) dentro do cliente do Microsoft Dynamics AX.</td>
<td>Um cliente web à parte foi usado para exibir os relatórios do Management Reporter.</td>
<td>Todos os relatórios financeiros podem ser acessados no cliente do Dynamics AX. O usuário seleciona um relatório que será exibido no cliente.</td>
<td>Agora você pode exibir relatórios financeiros sem a necessidade de acesso a um cliente/aplicativo diferente.</td>
</tr>
<tr class="even">
<td>Imprima relatórios financeiros (Relator de Gerenciamento) a partir do cliente do Microsoft Dynamics AX.</td>
<td>Imprimir um relatório utilizaria as opções de impressão do navegador para impressões e imprimiria apenas o que o usuário visualiza na tela. </td>
<td>O usuário pode escolher o nível de detalhamento e a configuração de página para um relatório utilizando a opção Imprimir do relatório financeiro no cliente do Dynamics AX.</td>
<td>Os relatórios impressos são gerados de acordo com a expectativa do usuário, ao invés de imprimir uma página da web.</td>
</tr><tr class="odd">
<td>Analise os dados financeiros utilizando o pacote de conteúdo “Monitorar desempenho financeiro” para conteúdo Power BI.</td>
<td>Não disponível</td>
<td>Em PowerBI.com, selecione **Obter Dados**, e depois selecione o pacote de conteúdo **Dynamics AX – Desempenho financeiro**. Insira a URL para seu ponto de extremidade do Dynamics AX para ver seus dados refletidos no painel.</td>
<td>Com três ou quatro cliques, as empresas podem implantar um painel Power BI que contém dados financeiros importantes. O conteúdo pode ser personalizado pela organização.</td>
</tr>
<tr class="even">
<td>Rastreie processos de fechamento de período financeiro.</td>
<td>Não disponível </td>
<td>Os modelos e agendas de fechamento podem ser criados por meio da configuração Fechamento do período financeiro. Use o espaço de trabalho **Fechamento do período financeiro** para acompanhar o progresso das agendas de fechamento em diversas empresas.</td>
<td>Esse espaço de trabalho elimina sistemas manuais para definir, agendar e comunicar atividades de fechamento. Portanto, o número de dias para fechamento é reduzido.</td>
</tr>
<tr class="odd">
<td>Monitore o orçamento versus valores reais, e crie previsões do razão utilizando o espaço de trabalho **Orçamentos e previsões do razão** e formulários de consulta adicionais.</td>
<td>Não disponível</td>
<td> O espaço de trabalho pode ser acessado por meio do painel Dynamics AX. Inclui diversos links para diversas novas páginas de consulta: **Resumo de Valores reais vs. orçamento**, **Resumo estatístico do controle de orçamento**, **Entradas no registrador do orçamento**, e **Planos de orçamento**.</td>
<td>As novas páginas de consulta permitem acesso a informações de orçamento. O espaço de trabalho combina todas as tarefas de manutenção e monitoramento do orçamento em um único lugar de fácil utilização para os gerentes de orçamento e contabilidade.</td>
</tr>
<tr class="even">
<td>Crie layouts para planos e previsões de orçamento.</td>
<td>O documento **Plano de orçamento** é exibido como uma lista de linhas que possuem datas efetivas e quantias para combinação de dimensões financeiras. O usuário precisa criar e usar modelos do Excel para exibir dados de plano de orçamento em uma Tabela Dinâmica.</td>
<td>Um número ilimitado de layouts está disponível para planos e previsões de orçamento. Você pode combinar dimensões financeiras selecionadas, colunas definidas por usuários e outros atributos de linha (como comentários, projetos e ativos) no layout. Os usuários podem alternar o layout do documento de plano de orçamento imediatamente e editar dados usando um layout selecionado. A configuração do planejamento de orçamento é simplificada por meio da eliminação das restrições de cenário e uso de layouts para definir quais dados podem ser exibidos e editados em cada etapa do documento de plano de orçamento.</td>
<td>Fornece a flexibilidade para criar e editar os planos de orçamento usando tanto o Excel quanto o cliente do Dynamics AX. Modelos para pastas de trabalho do Excel podem ser gerados por meio da configuração de layout do plano de orçamento.</td>
</tr>
<tr class="odd">
<td>Imprima o relatório **Transações de Fatura de Fornecedor** utilizando informação do relatório **Lista Detalhada de Datas de Vencimento**, que inclui os dias de atraso. </td>
<td>Você deve imprimir dois relatórios diferentes: **Lista Detalhada de Datas de Vencimento** e **Transações de Fatura de Fornecedor**.</td>
<td>As informações nos dois relatórios foram consolidadas no relatório **Transações de Fatura de Fornecedor**. O relatório **Lista Detalhada de Datas de Vencimento** tornou-se obsoleto. </td>
<td>Elimina a necessidade de imprimir dois relatórios separados mas relacionados.</td>
</tr>
<tr class="even">
<td>Gere relatórios de regulamentação diretamente em formato PDF.</td>
<td>Você deve primeiro gerar um relatório de regulamentação em um formato e depois exportá-lo para o formato PDF.</td>
<td>O formato PDF é o padrão para relatórios de regulamentação.</td>
<td>Proporciona uma experiência de exibição unificada tanto no monitor do computador quanto na cópia de papel impressa.</td>
</tr>
<tr class="odd">
<td>Execute o processo de liquidação de imposto como um processo em lote. </td>
<td>Não disponível</td>
<td>Na página **Período de liquidação do imposto**, é possível especificar que o processo de liquidação deve ser executado no modo de lotes.</td>
<td>No caso de períodos com muitas transações de imposto, o processo de liquidação pode ser muito demorado e talvez seja melhor executá-lo em segundo plano como um processo em lote.</td>
</tr>
</tbody>
</table>





## <a name="foundation"></a>Fundação
<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Acesse o cliente a qualquer momento, em qualquer lugar. </td>
<td>O cliente de desktop do AX 2012 fornece um conjunto completo de formulários, mas só pode ser executado em um computador com Microsoft Windows e precisa de instalação. O Terminal Server é frequentemente utilizado com o cliente da área de trabalho para habilitar o acesso em uma ampla área de rede (WAN). O cliente web do portal empresarial fornece um conjunto reduzido de formulários.</td>
<td>Os dois clientes do AX 2012 foram substituídos por um único cliente web baseado em padrões que fornece o conjunto completo de funcionalidade do cliente de área de trabalho juntamente com o alcance do cliente do portal empresarial.</td>
<td>Evita que esforços de desenvolvimento sejam divididos entre duas plataformas de interface do usuário. Usando interfaces da Web padrão, elimina a necessidade de Terminal Server.</td>
</tr>
<tr class="odd">
<td>Seja produtivo usando o novo gravador de tarefas.</td>
<td>O gravador de tarefas do AX 2012 requer acesso direto a um computador do Servidor de Objetos de Aplicativo (Application Object Server, AOS) e privilégios elevados e não fornece opções de edição.</td>
<td>O novo gravador de tarefas pode ser usado diretamente do cliente web. O acesso ao gravador de tarefas não exige privilégios administrativos. As etapas gravadas podem ser vistas ao vivo enquanto você grava, novas opções de edição foram introduzidas e o gravador de tarefas é compatível com mais cenários, além dos cenários de modelador de processo de negócios (Business process modeler, BPM).</td>
<td>O novo gravador de tarefas fornece uma experiência simplificada e habilita novos recursos no Dynamics AX. Alguns desses novos recursos já estão disponíveis e haverá mais deles no futuro.</td>
</tr>
<tr class="even">
<td>Ajuda os usuários a compreender melhor seu trabalho futuro com espaços de trabalho.</td>
<td>Os centros de funções fornecem uma visão geral das informações que se aplicam à função de trabalho de um usuário da empresa ou da organização.</td>
<td>Espaços de trabalho são um novo conceito no Dynamics AX que devem substituir centros de funções como a principal maneira de navegar para tarefas e páginas específicas Eles fornecem uma visão geral em uma página sobre uma atividade empresarial e ajudam usuários a entender o status atual, a carga de trabalho futura e o desempenho do processo ou usuário. Espaços de trabalho são mais granulares que os centros de funções do AX 2012, e um usuário pode ter acesso a diversos espaços de trabalho.</td>
<td>Espaços de trabalho foram criados para aumentar a produtividade do usuário. Os desenvolvedores precisarão criar um espaço de trabalho para cada "atividade" significativa apoiada no produto. Um centro de funções herdado do AX 2012 normalmente será substituído por vários espaços de trabalho na versão atual do Dynamics AX.</td>
</tr>
<tr class="odd">
<td>Tornar os formulários sensíveis à área de exibição do navegador ou tamanho do dispositivo.</td>
<td>No AX 2012, o conteúdo de formulário estava rigidamente estabelecido usando colunas, e a altura/largura geral da forma era amplamente determinada com base nos controles do formulário.</td>
<td>Com a mudança para a web no Dynamics AX mais recente, as dimensões do formulário agora são baseadas no tamanho da janela do navegador ou dispositivo. Os parâmetros de layout e controles foram modificados ou adicionados para responder melhor às alterações no tamanho da área de exibição.</td>
<td>O conteúdo do formulário precisa ser mais sensível para otimizar o uso da altura/largura disponível no navegador ou dispositivo. Alcançar a capacidade de resposta pode exigir alterações no modo como um formulário é modelado.</td>
</tr>
<tr class="even">
<td>Utilize padrões para obter uma experiência aprimorada de desenvolvimento de formulário.</td>
<td>Modelos de formulário estavam disponíveis como ponto de partida para o desenvolvimento de formulário no AX 2012 com base em um estilo de formulário. O Verificador de Estilo de Formulário, um incremento opcional, forneceu informações sobre como um formulário se desviou de seu modelo correspondente.</td>
<td>Na versão atual do Dynamics AX, foram introduzidos padrões de formulário. Padrões de formulário representam uma combinação de modelos de formulário e o Verificador de Estilo de Formulário se integrou fortemente à experiência de desenvolvimento. Padrões foram definidos no nível de formulário (como o AX 2012) com subpadrões adicionais agora disponíveis nos níveis de página de guia e grupo.</td>
<td>Os formulários que estão de acordo com padrões possuem muitos benefícios, incluindo uma interface de usuário mais consistente, uma experiência de desenvolvimento mais simples, caminho de upgrade de formulário mais fácil e aumento da confiança na capacidade de resposta do layout de formulário.</td>
</tr>
</tbody>
</table>

## <a name="help"></a>Ajuda
<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Acesse a Ajuda de procedimentos guiados (guias de tarefas) e tópicos conceituais clicando em **Ajuda**.</td>
<td>O sistema de ajuda do AX 2012 indica os tópicos de HTML que estão armazenados em um servidor web local. Clientes e parceiros podem criar sua própria ajuda.</td>
<td>O sistema de ajuda na versão atual do Dynamics AX mostra os guias de tarefas que estão armazenados no BPM do Microsoft Dynamics Lifecycle Services (LCS). O sistema de ajuda também mostra tópicos do site de documentos da Microsoft. Para obter mais informações, consulte [Ajuda do Dynamics AX - Introdução](help-overview.md) e [Novos guias de tarefa disponíveis (fevereiro de 2016)](new-task-guides-available-february-2016.md).</td>
<td>Guias de tarefa fornecem uma experiência controlada, guiada, interativa que servirá de norte durante as etapas de uma tarefa ou processo comercial. Você pode baixar e personalizar os guias de tarefas que a Microsoft fornece. O tópico fornece uma maneira mais rápida e mais flexível para criar, entregar e atualizar a documentação do produto. Portanto, ajuda a garantir que você tenha acesso às informações técnicas mais recentes.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gerenciamento de capital humano
<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Transfira habilidades e certificados para participantes da classe ao término do curso.</td>
<td>Trata-se de um processo manual.</td>
<td>Quando um curso é concluído, é disponibilizada uma nova opção para atualizar os registros de um participante com os novos certificados e habilidades.</td>
<td>Fornece uma nova e eficiente forma de atualizar os registros dos funcionários.</td>
</tr>
<tr class="odd">
<td>Verifique rapidamente o emprego.</td>
<td>Trata-se de um processo manual.</td>
<td>Seu departamento de RH pode verificar rapidamente os empregos usando um espaço de trabalho ou a página do funcionário.</td>
<td>Seu departamento de RH não tem mais acesso a várias páginas para verificar data de início, gerente, meses no cargo e dados de remuneração.</td>
</tr>
<tr class="even">
<td>Permita que os funcionários vejam, atualizem e excluam informações no sistema.</td>
<td>Disponível, mas com exibição e recursos de atualização limitados.</td>
<td>Este recurso está habilitado e permite que os funcionários e prestadores de serviço vejam uma ampla variedade de dados pessoais. Como opção, um fluxo de trabalho pode ser usado quando informações são criadas, atualizadas e excluídas.</td>
<td>Permite que os funcionários tenham o controle de suas informações, como atualizar endereço ou dados de contato, candidatar-se a um trabalho ou atualizar uma imagem. Quando um fluxo de trabalho é habilitado, as informações podem ser analisadas por um aprovador ou automaticamente aprovadas, com base em seus processos de negócios.</td>
</tr>
<tr class="odd">
<td>Deixe que os gerentes vejam ou editem as informações dos funcionários.</td>
<td>Disponível, mas com exibição e recursos de atualização limitados.</td>
<td>Dependendo das definições de configuração e segurança, os gerentes podem ver ou editar as informações dos funcionários.</td>
<td>Permite que os gerentes acessem os dados do funcionário para que eles possam tomar melhores decisões sobre recursos, desempenho e desenvolvimento do funcionário.</td>
</tr>
<tr class="even">
<td>Usufrua da funcionalidade de autoatendimento de gerente.</td>
<td>Não disponível</td>
<td>Os gerentes podem agora enviar solicitações para novas contratações (funcionários e prestadores de serviços), transferências e término (final do contrato de emprego). Os gerentes também podem solicitar uma nova posição, estender a duração de posições ou solicitar alterações de posição.</td>
<td>Esses cenários estavam expostos anteriormente apenas para Recursos Humanos. Habilitar esses cenários oferece ferramentas poderosas para gerentes de uma organização. Fluxos de trabalho opcionais podem ser habilitados para fornecer o nível correto de revisão e aprovações.</td>
</tr>
<tr class="odd">
<td>Acesse os resultados de processamento de remuneração.</td>
<td>Os resultados só estarão disponíveis no momento do processamento.</td>
<td>Agora os resultados de processamento de remuneração podem ser acessados a qualquer momento após a execução do processo.</td>
<td>Proporciona uma excelente auditoria do processo e do resultado do processo. Fornece uma abrangente exibição dos dados antes de os registros do funcionário serem atualizados.</td>
</tr>
<tr class="even">
<td>Acesse os resultados de processamento de benefício.</td>
<td>Os resultados só estarão disponíveis no momento do processamento.</td>
<td>Agora os resultados de benefício de remuneração podem ser acessados a qualquer momento após a execução do processo.</td>
<td>Fornece uma abrangente exibição dos dados que são atualizados por inscrição em benefícios e alterações de custo.</td>
</tr>
<tr class="odd">
<td>Veja alterações de linha do tempo de “data de efetivação”.</td>
<td>Não disponível</td>
<td>Esta ferramenta de comparação está disponível para funcionários, posições e trabalhos. Fornece uma abrangente visualização das alterações de uma versão de um registro para outra.</td>
<td>Permite que você economize tempo ao verificar alterações em registros de funcionários, posições e trabalhos ao longo do tempo. Permite que você compare rapidamente versões de um registro, ou todos os registros, ao longo do tempo.</td>
</tr>
<tr class="even">
<td>Veja funcionários por companhia.</td>
<td>Trata-se de um processo manual que é realizado por meio de filtragem.</td>
<td>Listas de funcionários e prestadores de serviço são automaticamente filtradas pela companhia na qual você fez logon.</td>
<td>Fornece uma visualização filtrada dos funcionários que estão empregados na companhia na qual o logon foi feito. Para uma exibição não filtrada de todos os funcionários e prestadores de serviço, a lista de trabalhadores ainda está disponível. Na versão atual do Dynamics AX, o sistema não muda a companhia com base no funcionário selecionado na lista.</td>
</tr>
<tr class="odd">
<td>Atualize a lista de participantes do curso.</td>
<td>Não disponível</td>
<td>Os participantes do curso podem ser removidos da lista de participantes.</td>
<td>Oferece uma forma prática de atualizar os participantes do curso cadastrados por engano.</td>
</tr>
<tr class="even">
<td>Gerencie eventos de remuneração em um grupo.</td>
<td>Não disponível</td>
<td>Este recurso simplifica o processamento de alterações de remuneração para funcionários.</td>
<td>Fornece um processo fácil e simplificado de atualização de registros de funcionários por meio de espaço de trabalho de remuneração e páginas relacionadas.</td>
</tr>
</tbody>
</table>

## <a name="inventory-management"></a>Gerenciamento de estoque
Não foram adicionados novos recursos.

## <a name="localization"></a>Localização
<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Configure e gere documentos eletrônicos para atender às exigências legais de vários países/regiões.</td>
<td>Documentos eletrônicos são de difícil codificação em X++ ou como XSLTs (Extensible Stylesheet Language Transformations). Qualquer ajuste de formato exige esforços de desenvolvimento. Acesso a dados e formatação não são isolados. Um desenvolvimento de formato ajustado requer um novo pacote de hotfix do Microsoft Dynamics AX que substitua a formato existente. As modificações personalizadas de cada formato devem ser transferidas para o código-fonte de um novo pacote de hotfix do Microsoft Dynamics AX.</td>
<td>O Relatório Eletrônico (RE) é uma nova ferramenta para configurar e gerar documentos eletrônicos que têm como alvo um usuário empresarial ao invés de um desenvolvedor. O RE permite que você configure modelos de dados que são de domínio específico e independente da base de dados do Microsoft Dynamics AX como fontes de dados para formatos de documento. Um usuário comercial pode configurar os formatos, com base nesses modelos de dados específicos do domínio (por exemplo, para pagamentos, relatórios Intrastat ou relatórios de imposto). O usuário configura os formatos usando ferramentas visuais simples que são semelhantes ao Excel. O RE é atualmente compatível com a geração de documentos eletrônicos nos formatos texto, XML e Excel. Esses documentos podem ser gerados simultaneamente e comprimidos em arquivos ZIP. Modelos e formatos de dados são compatíveis com controle de versão. Versões de formato podem ter períodos vigentes. Cada modelo de dados ou versão de formato é armazenado em uma configuração separada e distribuído a parceiros e clientes por meio de LCS. Parceiros e clientes podem personalizar modelos e formatos de dados da Microsoft ou criar os seus próprios. O RE salva as alterações nas configurações de parceiros e clientes como deltas nas configurações da Microsoft, o que simplifica as atualizações para novas versões de configurações da Microsoft. Ao utilizar LCS, os parceiros também podem compartilhar seus modelos de dados e suas configurações de formato com outros parceiros e clientes, que podem personalizá-las e compartilhá-las. A personalização e fácil atualização de delta recebem suporte em toda a cadeia de personalização.</td>
<td>O RE simplifica a criação, manutenção e atualização de formatos de documentos eletrônicos visando atender as exigências legais em diversos países/regiões. O RE torna o processo de criação ou alteração de formatos de documentos eletrônicos mais rápido e fácil. Essas alterações podem ser feitas por usuários comerciais em vez de desenvolvedores. O RE torna mais rápido e fácil para parceiros e clientes atualizarem suas personalizações de formato para novas versões de formatos que são lançadas pela Microsoft ou outros parceiros. O RE oferece uma maneira comum (por meio do LCS) para que a Microsoft e os parceiros distribuam configurações de documento eletrônico para outros parceiros e clientes. O RE também facilita para que parceiros e clientes personalizem, atualizem e distribuam formatos de documento eletrônico de acordo com suas necessidades comerciais específicas.</td>
</tr>
<tr class="odd">
<td>(MEX) Gere relatórios de regulamentação de imposto sobre valor agregado (IVA) mexicano.</td>
<td>Você deve gerar relatórios **IVA sobre Compras e Vendas** utilizando a funcionalidade de IVA não realizado, para que usuários possam identificar transações que pertençam às sessões realizadas e não realizadas com base no status.</td>
<td>Os relatórios **IVA sobre Compras e Vendas** foram modificados e agora consideram o recurso de imposto condicional apenas utilizando períodos específicos de liquidação para a definição de códigos de imposto sobre vendas não realizadas e realizadas.</td>
<td>Alterações na configuração de códigos de imposto são necessárias antes que os usuários possam gerar esses relatórios corretamente. Um recurso de imposto condicional é necessário, e o usuário deve configurar períodos de liquidação separados, não realizados e realizados, para identificar as transações nas áreas da seção relacionada.</td>
</tr>
<tr class="even">
<td>(JPN) Gerencie o documento de declaração de depreciação acelerada do ativo fixo japonês.</td>
<td>Não disponível</td>
<td>Informações de declaração importantes são armazenadas centralmente em um único documento para melhor manutenção.</td>
<td>A conformidade e o fácil gerenciamento do documento ajudam a reduzir problemas durante auditorias ou outras revisões.</td>
</tr>
<tr class="odd">
<td>(JPN) Verifique os caracteres JBA na conta bancária.</td>
<td>Não disponível</td>
<td>Você pode verificar se os campos de nome kana contêm apenas caracteres que são permitidos pelo formato bancário JBA.</td>
<td>Ajuda a reduzir as interrupções aos usuários durante a criação de arquivos de pagamento por causa de caracteres inválidos.</td>
</tr>
<tr class="even">
<td>(JPN) Recupere a diferença mínima do ativo fixo japonês no fim do ano fiscal.</td>
<td>Não disponível</td>
<td>Na página **Parâmetros de ativo fixo**, é possível optar por recuperar ao fim do período fiscal ou ano fiscal.</td>
<td>Fornece mais flexibilidade para equiparar práticas locais.</td>
</tr>
<tr class="odd">
<td>(JPN) Gere a série de 16 tabelas anexas da declaração do imposto sobre a produção da pessoa coletiva japonesa em um valor resumido por tipo principal de ativo fixo.</td>
<td>Não disponível</td>
<td>Nos modelos de valor de um ativo fixo, você pode optar por resumir por tipo principal. Por padrão, essa funcionalidade é usada para ativos fixos recém-criados.</td>
<td>Para grandes companhias com centenas de ativos fixos, os relatórios resumidos reduzem consideravelmente o tamanho do relatório que é gerado.</td>
</tr>
<tr class="even">
<td>(JPN) Comece alocando a reserva de depreciação especial do próximo ano fiscal para ativos fixos japoneses.</td>
<td>Não disponível</td>
<td>Nos modelos de valor de um ativo fixo com um perfil de depreciação extraordinária adequado, você pode optar por iniciar a alocação do próximo período fiscal ou próximo ano fiscal.</td>
<td>Fornece mais flexibilidade para equiparar práticas locais.</td>
</tr>
<tr class="odd">
<td>(JPN) Gere um relatório de imposto de consumo japonês que inclua as alíquotas de imposto revisadas.</td>
<td>O relatório de imposto de consumo está disponível para uma alíquota de imposto de 5%.</td>
<td>O relatório de imposto de consumo contém uma seção para a alíquota de imposto revisada (por exemplo, 8%).</td>
<td>O layout foi anunciado recentemente pelo governo.</td>
</tr>
<tr class="even">
<td>(UE) Configurar as definições de arredondamento para a lista de vendas da EU.</td>
<td>As definições de arredondamento para os relatórios de lista de vendas da EU em vários países/regiões são codificados em X++ ou em Extensible Stylesheet Language Transformations (XSLTs).</td>
<td>As definições de arredondamento são adicionadas aos parâmetros de Transação estrangeira. Você pode configurar a precisão de arredondamento, método de arredondamento, precisão da saída e o comportamento para valores menores que a precisão do arredondamento.</td>
<td>Isso unifica e simplifica a configuração dos relatórios de lista de vendas da EU. O ajuste das definições de arredondamento não exigem mais esforços de desenvolvimento.</td>
</tr>
<tr class="odd">
<td>(UE) Configurar regras de aplicabilidade de encargo revertido.</td>
<td>As regras de aplicabilidade de encargos revertidos são codificadas para o cenário de encargo revertido nacional. O limite de aplicabilidade pode ser definido por grupo de itens. A funcionalidade está disponível apenas para a Grã Bretanha.</td>
<td>Você pode configurar regras de aplicabilidade de encargo revertido por tipo de documento (ordem de compra/venda, fatura de fornecedor, fatura de texto livre, etc.) e um grupo de encargos revertidos que combina itens, grupos de itens e categorias de compra/venda. As regras de aplicabilidade possuem data de vigência. Também é possível marcar códigos individuais de imposto sobre vendas em grupos de impostos sobre vendas conforme aplicável para encargos revertidos. O relatório de nota fiscal de venda é ajustado para representar detalhes do encargo revertido aplicado. A funcionalidade está disponível para todos os países/regiões europeias.</td>
<td>Essa alteração unifica a configuração das regras de aplicabilidade de encargos revertidos e oferece suporte à adoção das regulamentações nacionais de encargo revertido por países/regiões europeias.</td>
</tr>
<tr class="even">
<td>(DE) Gerar o arquivo de auditoria alemão - GDPdUGoBD</td>
<td>Os usuários podem configurar a definição de tabelas que contêm os dados financeiros para que sejam exportados em um formato aceito por autoridades e auditores alemães.</td>
<td>O recurso foi implementado como uma configuração de relatório eletrônico. A funcionalidade está disponível para a Alemanha e a Áustria.</td>
<td>Essa alteração dá ao usuário muito mais possibilidades na formatação de dados, transformações, e também oferece todos os benefícios de gerenciamento do ciclo de vida da configuração de relatório eletrônico, como fácil troca de configuração, controle de versão, etc.</td>
</tr>
<tr class="odd">
<td>(FR) Lista de saldos com relatório de contas total do grupo.</td>
<td>Lista de saldos com relatório de contas total do grupo é implementada como relatório SSRS (LedgerAccountSum\_FR).</td>
<td>Lista de saldos com relatório de contas total do grupo é implementada como relatório do Relator de Gerenciamento disponível na biblioteca de Ativos LCS localizada na pasta de relatórios financeiros.</td>
<td>Isso permite aos usuários obter todos os benefícios e liberdade de personalização ao utilizar relatórios financeiros no Relator de Gerenciamento.</td>
</tr>
<tr class="even">
<td>(EU) Aviso de pagamento, Nota de participação e Relatórios de controle para pagamentos.</td>
<td>Todos os relatórios são implementados e relatórios do SSRS.</td>
<td>Esses relatórios foram implementados como modelos de Open XML para serem usados no Microsoft Excel.</td>
<td>As configurações de pagamento eletrônico contém definições e modelos de formato de arquivo de pagamento. Isso permite aos usuários obter todos os benefícios e liberdade de personalização do relatório ao utilizar Relatórios eletrônicos.</td>
</tr>
<tr class="odd">
<td>(UE) Configurar as definições de arredondamento para Intrastat.</td>
<td>As definições de arredondamento para os relatórios Intrastat em vários países/regiões são codificados em X++ ou em Extensible Stylesheet Language Transformations (XSLTs).</td>
<td>As definições de arredondamento são adicionadas aos parâmetros de transação estrangeira. Você pode configurar a precisão de arredondamento, método de arredondamento, precisão da saída e o comportamento para valores menores que a precisão do arredondamento.</td>
<td>Isso unifica e simplifica a configuração dos relatórios Intrastat. O ajuste das definições de arredondamento não exigem mais esforços de desenvolvimento.</td>
</tr>
<tr class="even">
<td>(EU) Definir códigos de mercadoria Intrastat em hierarquias de categoria.</td>
<td>Códigos de mercadoria Intrastat é uma lista separada. Embora exista uma hierarquia de categoria do tipo de Código de mercadoria, esses códigos de mercadoria poderiam ser padronizados nas categorias Varejo HQent e vendas.</td>
<td>A lista separada de códigos de mercadoria Intrastat é mesclada à hierarquia de produto do tipo Código de mercadoria.</td>
<td>Isso unifica a abordagem para atribuir códigos de mercadoria à produtos lançados e categorias em documentos de compra e venda.</td>
</tr>
<tr class="odd">
<td>(UE) Relatar a quantidade em unidades adicionais para Intrastat utilizando a definição de conversão de unidade.</td>
<td>O código de mercadoria Intrastat possui um campo de texto para identificar as unidades adicionais, e o cartão Produto possui um campo para identificar a quantidade de unidades adicionais em quilogramas.</td>
<td>Unidades adicionais para o código de mercadoria Intrastat são escolhidas da lista de Unidades. A quantidade de unidades adicionais é calculada por meio de configurações de conversão de unidade.</td>
<td>Isso unifica a abordagem de recálculo de unidades de transação para unidades adicionais.</td>
</tr>
<tr class="even">
<td>(UE) Atribuir método de transporte padrão ao modo de entrega.</td>
<td>Não disponível</td>
<td>Um campo para método de transporte padrão é adicionado ao Modo de entrega.</td>
<td>Isso simplifica a preparação do relatório Intrastat.</td>
</tr>
<tr class="odd">
<td>(UE) Marcar produto lançado que não deverá ser informado no Intrastat.</td>
<td>Não disponível</td>
<td>Uma opção para excluir o item do relatório Intrastat é adicionada ao produto lançado.</td>
<td>Isso simplifica a preparação do relatório Intrastat.</td>
</tr>
</tbody>
</table>

## <a name="manufacturing"></a>Fabricação
|                                                                                                                                                      |                                                                                                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                       |
|------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                                                                                                 | **Dynamics AX 2012**                                                                                                             | **Dynamics AX 7.0**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | **Por que isso é importante?**                                                                                                                                                                                                                                            |
| Realize uma verificação da disponibilidade de material para ordens de produção em uma página separada que é aberta no espaço de trabalho **Gerenciamento de chão de fábrica**. | Não disponível                                                                                                                    | O supervisor de produção pode verificar se os materiais para as ordens de produção programadas estarão disponíveis na data requerida. No espaço de trabalho, o supervisor de produção pode ver quantas ordens de produção estão no estado programado e com liberação pendente. Com base no plano mestre dinâmico, as informações sobre a disponibilidade de material são atualizadas se as exigências de material forem atendidas conforme o estoque disponível para ordens reais ou ordens planejadas. Com base nas informações sobre disponibilidade de material, o supervisor pode liberar as ordens na página **Disponibilidade de material**.                                                                                                                                                                                                                                                                                                                        | Permite que os supervisores de produção tomem decisões apropriadas sobre a alocação de materiais para ordens quando as ordens de produção estiverem sendo liberadas para o chão de fábrica.                                                                                                       |
| Inicie e relate o progresso em trabalhos de produção utilizando a nova página **Dispositivo de cartão de trabalho**.                                                              | O formulário **Registro de trabalho** se destina principalmente a grandes telas de terminal, e a interface de usuário costuma ser acessada por cliques do mouse. | Embora a nova página Dispositivo de cartão de trabalho seja projetada para simplicidade, também é projetada para ser sensível ao toque. A página adéqua-se a dispositivos móveis, como tablets e celulares. O trabalhador de chão de fábrica vai encontrar menos sobrecarga de informações e mais facilidade de uso intuitivo. O trabalhador pode realizar tarefas tradicionais, como iniciar, finalizar e relatar o progresso em um trabalho. Além de realizar o trabalho real ou fazer logoff e marcar o cartão ao sair, o trabalhador pode exibir anexos, parar para o almoço e fazer outras atividades. Trabalhos são enfileirados em uma sequência planejada, mas também podem ser separados pelo trabalhador. A página é voltada principalmente a operações de fabricação distintas, nas quais os materiais são preparados para produção. Para cenários que estão relacionados a relatórios de coprodutos e subprodutos, e separação de materiais por dimensões de rastreamento, use a página **Registro de trabalho**. | Apresentando uma interface de usuário alternativa que é sensível ao toque e pode ser acessada de todos os tipos de dispositivos, como telas de terminal e dispositivos móveis, este recurso ajudará a reduzir os custos de implementação para uma distribuição tradicional de registros de chão de fábrica. |

## <a name="master-planning-and-forecasting"></a>Planejamento e previsão mestre
|                                                                                                                            |                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                         |
|----------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                                                                       | **Dynamics AX 2012**                                                                                                                                                                                                                                                                          | **Dynamics AX 7.0**                                                                                                                                                                                                                                                                                                                                               | **Por que isso é importante?**                                                                                                                              |
| Alerte o usuário se uma ordem de venda ou ordem de produção não está pronta para entrega na data programada.                         | Os avisos criados pelo planejamento mestre são chamados de *mensagens de futuros*. *Futuros* são um contrato entre duas partes para comprar ou vender um ativo por um preço que é acordado no momento atual (o *preço de futuros*), embora a entrega e o pagamento ocorram em um momento no futuro (a *data de entrega)*. | *Mensagens de futuros* e *datas de futuros* foram renomeados como *atrasos calculados* e *datas atrasadas, *respectivamente.                                                                                                                                                                                                                                                   | A terminologia usada no AX 2012 era imprecisa e levava a traduções incorretas.                                                               |
| Compreenda rapidamente o status de uma execução de planejamento mestre, ordens planejadas urgentes e ordens planejadas que provocam atrasos. | As informações estão disponíveis, mas distribuídas em vários formulários.                                                                                                                                                                                                                       | O espaço de trabalho **Planejamento mestre** oferece informações rápidas sobre quando a última execução do planejamento mestre foi concluída, se houve algum erro, quais são as ordens planejadas urgentes e quais ordens planejadas provocam atrasos.                                                                                                                                   | Você se beneficia da visão geral fornecida pelo espaço de trabalho. As informações relevantes são reunidas para orientar o planejamento mestre e ajudar a melhorar a produtividade. |
| Use o Excel para atualizar previsões de demanda.                                                                                      | Não disponível                                                                                                                                                                                                                                                                                 | Você pode aproveitar a perfeita integração com o Excel ao inserir previsões de demanda, fazer atualizações e excluir previsões de demanda.                                                                                                                                                                                                                             | Ajuda a aumentar a eficiência e produtividade.                                                                                                          |
| Estime a demanda futura e crie previsões de demanda, com base no histórico de dados de transação.                                  | No Microsoft Dynamics AX 2012 R3, os modelos de previsão no Microsoft SQL Server Analysis Service são usados para criar previsões de demanda.                                                                                                                                                | Estime demandas futuras usando a capacidade e extensibilidade de um serviço de nuvem do Aprendizado de Máquina do Microsoft Azure. É fácil usar e estender os modelos de previsão no Aprendizado de Máquina para atender às necessidades do cliente. O serviço seleciona um modelo que combine melhor e fornece os indicadores de desempenho chave (KPIs) que podem ser usados para calcular a precisão da previsão. | Gere mais previsões acuradas usando as técnicas do Aprendizado de Máquina.                                                                              |
| Otimize a data e quantidade da ordem, com base em uma síntese visual das ações relacionadas da execução de planejamento mestre.          | A visão geral do gráfico de ações está disponível, mas mostra todas as ações relacionadas. Quando as ações forem aplicadas, elas desaparecerão imediatamente da exibição.                                                                                                                                             | O gráfico de ações fornece uma visão geral melhor. Inclui opções que permitem mostrar apenas as ações aplicadas e as diretamente relacionadas. Quando as ações forem aplicadas, elas aparecerão esmaecidas, mas ainda serão exibidas. Portanto, a visão geral é mantida. Mais informações são adicionadas ao gráfico de ações para exibir os dados em uma página.                               | Você pode se beneficiar da melhora de produtividade, porque você focará apenas as ações relevantes.                                                              |

## <a name="procurement-and-sourcing"></a>Compras
|                                                                                                                                                         |                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                                                                                                    | **Dynamics AX 2012** | **Dynamics AX 7.0**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | **Por que isso é importante?**                                                                                                                                                                                                               |
| Use o espaço de trabalho **Preparação da ordem de compra** para obter informações rápidas sobre o status das ordens de compra que estão sendo preparadas.                      | Sem suporte        | O espaço de trabalho **Preparação da ordem de compra** oferece uma visão geral das ordens do momento em que são criadas como um rascunho e rastreadas, passando pelos estados de aprovação de fluxo de trabalho, até a confirmação.                                                                                                                                                                                                                                                                                                                      | O departamento de compras não precisa mais procurar informações em várias páginas, pois agora ele se beneficia da visão geral que o espaço de trabalho fornece.                                                                                         |
| Use o espaço de trabalho **Recebimento e acompanhamento da ordem de compra** para obter informações rápidas sobre ordens de compra com recebimento pendente, para auxiliar no acompanhamento. | Sem suporte        | O espaço de trabalho **Recebimento e acompanhamento da ordem de compra** oferece uma visão geral das ordens de compra confirmadas com recebimento ou envio pendente. O espaço de trabalho inclui listas de recebimentos pós-vencimento e recebimentos pendentes para ajudar com revisão e acompanhamento proativos pelo fornecedor. O espaço de trabalho também lista ordens de compra cujo registro de entrada ocorreu no depósito, para ajudar a garantir que o recebimento será lançado. As devoluções de ordens de compra que ainda não foram emitidas também estão disponíveis para análise. | O departamento de compras aproveita a visão geral que o espaço de trabalho fornece. As informações relevantes são reunidas para orientar o acompanhamento e ajudar a melhorar a produtividade.                                                                |
| Envie as ordens de compra para confirmação a um portal de fornecedor hospedado no cliente do Dynamics AX. Deixe que o fornecedor confirme ou rejeite.                            | Sem suporte        | A interface do portal do fornecedor permite que fornecedores recebam ordens de compra para serem confirmadas ou rejeitadas. Também permite que o fornecedor tenha uma visão geral de todas as ordens de compra confirmadas para uma conta. O agente de compras pode enviar uma ordem de compra solicitando a confirmação do fornecedor. O fornecedor precisa ser um usuário registrado do Microsoft Azure Active Directory (Azure AD) no Dynamics AX, uma pessoa de contato para o fornecedor, e possuir uma função de segurança exclusiva.                                                     | O departamento de compras beneficia-se da redução da papelada e rastreamento manual de respostas em ordens de compra, uma vez que entram diretamente no sistema. Ter uma só fonte de verdade reduz os mal-entendidos entre cliente e fornecedor. |

## <a name="projects"></a>Projetos
|                                        |                                                                                         |                                                                                                                                              |                                                          |
|----------------------------------------|-----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------|
| **O que você pode fazer?**                   | **Dynamics AX 2012**                                                                    | **Dynamics AX 7.0**                                                                                                                          | **Por que isso é importante?**                               |
| Reserve trabalhadores como recursos em projetos. | Assim como os recursos, os trabalhadores são reservados em projetos em associação aos recursos. | A tabela de centro de trabalho, na qual recursos para fabricação e produção estão armazenados, agora pode ser usada para reservar trabalhadores como recursos em um projeto. | Ao reservar projetos, você só precisar reservar os recursos. |

## <a name="retail-sales-marketing-and-customer-service"></a>Vendas de varejo, marketing e atendimento ao cliente
### <a name="retail-hq"></a>Matriz de varejo

O Microsoft Azure-hosted Retail HQ oferece gerenciamento centralizado e visibilidade completa de todos os aspectos das operações comerciais através de um cliente web.

<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Realize operações de merchandising.</td>
<td>Usuários devem acessar vários formulários para gerenciar estes dados:
<ul>
<li>Gerenciamento de categoria</li>
<li>Gerenciamento de produtos</li>
<li>Atributos de produto do canal</li>
<li>Sortimentos</li>
<li>Gerenciamento de catálogo</li>
<li>kits</li>
<li>Preços &amp; descontos</li>
</ul></td>
<td>O espaço de trabalho <strong>Gerenciamento de categorias e produtos</strong> habilita a seguinte funcionalidade:
<ul>
<li>Gerenciamento de classificação.</li>
<li>Acompanhamento do ciclo de vida de classificação.</li>
<li>Gerenciamento de produtos lançados.</li>
</ul>
O <strong>espaço de trabalho Gerenciamento de preços e descontos</strong> habilita as seguintes funcionalidades:
<ul>
<li>Gerenciamento de preços e descontos para um canal e categoria específicos.</li>
<li>Gerenciamento de regra de preço de categoria.</li>
<li>Prioridades de preços e descontos, que permite atribuir prioridades a grupos de preços e descontos, para que você possa controlar a ordem na qual eles são aplicados.</li>
<li>Gerenciamento de descontos de afiliação e catálogo.</li>
</ul>
O espaço de trabalho <strong>Gerenciamento de catálogo</strong> habilita as seguintes funcionalidades:
<ul>
<li>Resumo de catálogos ativos.</li>
<li>Acompanhamento do ciclo de vida do catálogo em um único local.</li>
</ul></td>
<td><ul>
<li>Espaços de trabalho melhoram a eficiência e a produtividade dos trabalhadores permitindo que eles gerenciem centralmente suas tarefas e ações relacionadas à função de merchandizing.</li>
<li>O recurso de prioridade de preços e descontos garante aos clientes mais controle sobre como preços e descontos são usados. O recurso também habilita novos cenários nos quais preços de armazenamento mais elevados superam os preços padrão.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Gerencie as implantações e operações de canal de varejo.</td>
<td>O usuário deve acessar vários formulários para executar as seguintes tarefas:
<ul>
<li>Crie e configure canais e entidades relacionadas.</li>
<li>Gerencie atividades de armazenamento diário.</li>
<li>Processe transações de varejo no Microsoft Dynamics AX, gere declarações de varejo e atualize o estoque e as finanças do Microsoft Dynamics AX.</li>
</ul>
 </td>
<td>O espaço de trabalho <strong>Desenvolvimento de canal</strong> permite realizar as seguintes tarefas:
<ul>
<li>Crie canais e entidades relacionadas.</li>
<li>Acompanhe o progresso de configuração de lojas de varejo.</li>
<li>Adote as medidas necessárias para concluir a tarefa ou forneça as informações para concluir a tarefa.</li>
<li>Acompanhe o status dos dispositivos. Depois, valide e baixe diretamente a instalação do programa Retail Modern POS (MPOS) na lojas.</li>
<li>Acesse todas as páginas relacionadas.</li>
</ul>O espaço de trabalho 
<strong>Gerenciamento de loja de varejo</strong> permite realizar as seguintes tarefas:
<ul>
<li>Gerencie os trabalhadores e as permissões de ponto de venda (PDV) dos trabalhadores.</li>
<li>Acompanhe o status do turno de uma determinada loja ou determinado grupo de lojas.</li>
<li>Valide e baixe diretamente a instalação do programa MPOS na lojas.</li>
<li>Imprima relatórios e acesse páginas relacionadas.</li>
</ul>O espaço de trabalho 
<strong>Finanças da loja de varejo</strong> permite realizar as seguintes tarefas:
<ul>
<li>Crie, calcule e lance demonstrativos de um determinado canal.</li>
<li>Agende trabalhos em lotes para atualizar estoque e calcular e lançar demonstrativos.</li>
<li>Acompanhe demonstrativos abertos.</li>
<li>Acompanhe o status do turno de uma determinada loja ou determinado grupo de lojas.</li>
<li>Imprima relatórios e acesse rapidamente todas as páginas relacionadas.</li>
</ul></td>
<td>Espaços de trabalho melhoram a eficiência e a produtividade dos trabalhadores permitindo que eles gerenciem centralmente a maior parte de suas tarefas e ações que estão relacionadas a implantação de canal, gerenciamento de armazenamento e finanças.</td>
</tr>
<tr class="even">
<td>Gerencie operações de TI de varejo.</td>
<td>O usuário deve acessar vários formulários.</td>
<td>O espaço de trabalho <strong>TI de varejo</strong> habilita consultas do Commerce Data Exchange em um único lugar para um determinado canal, para que você possa realizar as seguintes tarefas:
<ul>
<li>Sessões de download.</li>
<li>Sessões de upload.</li>
<li>Acompanhe sessões com falha e reinicie-as ou execute-as outra vez.</li>
<li>Exiba ou execute trabalhos futuros.</li>
</ul></td>
<td>Espaços de trabalho melhoram a eficiência e a produtividade dos trabalhadores permitindo que eles gerenciem centralmente suas tarefas e ações relacionadas a operações de TI do varejo.</td>
</tr>
<tr class="odd">
<td>Importar/exportar dados usando entidades de dados.</td>
<td>O AX 2012 é compatível com a migração imediata do Microsoft Dynamics Retail Management System (RMS) por meio da estrutura de Importação/Exportação de Dados.</td>
<td>Entidades de dados de varejo foram expandidas para suportar todos os dados mestres e de referência relacionados a varejo. Também há suporte avançado para entidades de dados em toda a solução do Dynamics AX.</td>
<td>Entidades de dados permitem que clientes realizem importação e exportação de dados orientadas por metadados. Entidades do OData também permitem que clientes integrem o Dynamics AX com programas de terceiros.</td>
</tr>
<tr class="even">
<td>Realize análises inteligentes usando relatórios de BI do Dynamics Microsoft AX e cliente de PDV.</td>
<td>Mais de 25 relatórios de back office e cinco relatórios de canal estão disponíveis.</td>
<td>Mais de 30 relatórios de apoio e 10 relatórios de canal estão disponíveis.</td>
<td>Esses relatórios permitem que clientes tenham mais BI para prever tendências, obter informações e operar com máximo desempenho e de forma contínua.</td>
</tr>
<tr class="odd">
<td>Analise dados de vendas de canais de varejo usando o conteúdo “Monitorar o Desempenho dos Canais de Varejo” para Power BI.</td>
<td>Não disponível</td>
<td>Em PowerBI.com, selecione <strong>Obter dados</strong> e depois selecione o pacote de conteúdo <strong>Dynamics AX – Desempenho dos canais de venda</strong>. Insira a URL para seu ponto de extremidade do Dynamics AX para ver seus dados refletidos no painel.</td>
<td>Com três ou quatro cliques, as empresas podem implantar um painel Power BI que contém dados financeiros importantes. O conteúdo pode ser personalizado pela organização. Além disso, usuários podem incorporar blocos do painel Power BI nos espaços de trabalho personalizados do Dynamics AX, para que possam ver as informações analíticas rapidamente.</td>
</tr>
<tr class="even">
<td>Configure as permissões do cliente.</td>
<td>Não disponível</td>
<td>Os clientes podem decidir se as operações de PDV podem ser disponibilizadas aos clientes. O Servidor de Varejo usa permissões para chamadas de interface de programação de aplicativo (API).</td>
<td>Fornece a capacidade de configurar as permissões no nível do cliente.</td>
</tr>
<tr class="odd">
<td>Gerencie e valide configurações de entidade.</td>
<td>Não disponível</td>
<td>O recurso gerenciador e validador de configurações habilita a seguinte funcionalidade:
<ul>
<li>Upload de dados de configuração em massa</li>
<li>Validação de entidade comercial</li>
</ul></td>
<td>Permite inicializar a configuração e validar o status e a integridade da configuração dos vários elementos de configuração.</td>
</tr>
</tbody>
</table>

### <a name="retail-hardware-station"></a>Estação de Hardware do Retail

|                                                                                                  |                                                                         |                                                                                                                                                                                                                                                                                                                                                               |                                                                                                                                   |
|--------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                                             | **Dynamics AX 2012**                                                    | **Dynamics AX 7.0**                                                                                                                                                                                                                                                                                                                                           | **Por que isso é importante?**                                                                                                        |
| Habilite dispositivos de PDV para se conectar a periféricos, como impressoras, caixas registradoras ou dispositivos de pagamento. | O perfil de hardware do MPOS é usado para especificar os dispositivos que são usados. | Um perfil de hardware adicionado é compatível com hardwares mais diversificados de uma estação para a outra. O perfil de uma nova estação de hardware é compatível com uma ID de terminal exclusiva para cada estação de hardware quando as transações de transferência eletrônica de fundos (TEF) são processadas. O suporte a TEF foi mesclado em uma estação de hardware para reduzir a participação do MPOS no processo de pagamento de TEF. | Proporciona mais flexibilidade para implementações. Também proporciona segurança avançada e exposição reduzida para dados de cartão de crédito. |

### <a name="retail-server-and-data-management"></a>Gerenciamento de Servidor de Varejo e dados

Com o gerenciamento de Servidor de Varejo e dados, clientes e empresas podem criar uma experiência de compra de canal omni em canais online, na loja e de call center.

<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Conecte-se a um banco de dados de tempo de execução (commerce runtime, CRT) que armazene dados comerciais do canal usando serviços de CRT.</td>
<td>Há compatibilidade com o OData V3.</td>
<td>Há compatibilidade com o OData V4.</td>
<td>Ajuda a manter o cliente atualizado em relação aos padrões de OData. Também cria uma sólida experiência de canal omni integrando vendas em canais na loja, móveis e online.</td>
</tr>
<tr class="odd">
<td>Dê suporte a serviços de varejo como um conjunto hospedável de serviços.</td>
<td>A API de comércio eletrônico não é compatível por meio do Servidor de Varejo.</td>
<td>Agora a API de comércio eletrônico está disponível por meio do Servidor de Varejo para dar suporte a cenários online.</td>
<td>Fornece serviços de comércio eletrônico hospedados e escalonáveis que podem ser usados com lojas online de terceiros.</td>
</tr>
<tr class="even">
<td>Mova os dados entre o back office e os canais do Microsoft Dynamics AX usando o Commerce Data Exchange.</td>
<td>O Commerce Data Exchange é um sistema que transfere dados entre o Microsoft Dynamics AX e os canais de varejo, como lojas online ou lojas físicas. Para obter mais informações, acesse <a href="https://technet.microsoft.com/en-us/library/dn741440.aspx">Commerce Data Exchange [AX 2012]</a>.</td>
<td>Há uma paridade funcional com o Microsoft Dynamics AX 2012 CU8. No entanto, observe os seguintes detalhes:
<ul>
<li>O Commerce Data Exchange foi reprojetado para a nuvem.</li>
<li>O serviço Async usa acesso de banco de dados direto para o banco de dados do canal.</li>
<li>Commerce Data Exchange: serviço em tempo real é hospedado como um serviço personalizado do Microsoft Dynamics AX.</li>
<li>O MPOS gerencia a sincronização entre banco de dados offline e o Servidor de Varejo.</li>
</ul></td>
<td>O Commerce Data Exchange foi reprojetado para a plataforma de nuvem. Continua a gerenciar a transferência de dados entre o Microsoft Dynamics AX e os canais de varejo, como lojas online ou lojas físicas.</td>
</tr>
<tr class="odd">
<td>Forneça suporte a plug and play, pagamento de canal cruzado semi-integrado usando o SDK de pagamento.</td>
<td>O AX 2012 fornece a seguinte funcionalidade:
<ul>
<li>Suporte para todos os canais: PDV, comércio eletrônico e call center.</li>
<li>Suporte para cartão presente e cartão não presente.</li>
<li>Página para aprovação de pagamento.</li>
<li>Suporte periférico para LS5300 e MX925 como código de amostra no Varejo SDK.</li>
</ul></td>
<td>A versão atual do Dynamics AX é compatível com todos os recursos de cartão de crédito/débito e quatro novos aprimoramentos do Microsoft Dynamics AX for Retail 2012.</td>
<td>Permite que o cliente processe transações de cartão de crédito/débito para pagamentos.</td>
</tr>
<tr class="even">
<td>Ativar os dispositivos usando uma conta da Microsoft (Microsoft Azure Active Directory (Azure AD)).</td>
<td>Não disponível</td>
<td>A seguinte funcionalidade é fornecida:
<ul>
<li>Segurança avançada pela ativação para a nuvem com base no Azure AD.</li>
<li>Segurança avançada para gerenciamento de token.</li>
<li>Confiabilidade, solução de problemas e mensagens de erro durante a ativação aprimoradas</li>
<li>Tarefas de administração de TI simplificadas que estão relacionadas à ativação.</li>
<li>Modelo de ameaças revisado e problemas de segurança corrigidos.</li>
</ul></td>
<td>Proporciona os seguintes benefícios:
<ul>
<li>A segurança é aprimorada por meio do Azure AD e token/ID do dispositivo (chamadas RS que usam um token, armazenamento de aplicativos de usuário específico).</li>
<li>Impede o uso remoto não autorizado do MPOS (dispositivo de bloco)</li>
<li>Rastreia dispositivos MPOS para fins de conformidade de PCI.</li>
<li>Mapeia dispositivos físicos com uma entidade comercial (registro) usando um token de dispositivo.</li>
<li>Inicializa configurações para funcionalidades simples do MPOS (sequências numéricas e perfis de hardware) como o ponto de contato do MPOS.</li>
<li>Reporta informações de dispositivos da matriz.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Gerencie conteúdo de mídias avançadas para criação e serviço por meio da galeria de mídia.</td>
<td>Não disponível</td>
<td><ul>
<li>Suporte para upload, exibição, gerenciamento e exclusão de imagens da Galeria de Mídia para imagens hospedadas tanto externamente quanto por varejo.</li>
<li>Suporte para upload e exibição de imagens nas páginas de entidade (<strong>Produtos</strong>, <strong>Catálogos</strong>, e assim por diante) vinculando uma imagem da galeria e realizando upload de uma imagem da área de trabalho.</li>
<li>Otimize as imagens para miniaturas, tamanhos personalizados e originais.</li>
<li>Vincule entidades em massa usando um modelo e trabalhos em segundo plano para associação em massa.</li>
<li>A integração do Microsoft Excel substitui a limitação de grupos de atributos de convenções de nomenclatura e caminhos predefinidos.</li>
<li>Suporte para imagens offline e imagens seguras para o conteúdo de informações de identificação pessoal (PII), como imagens de funcionários e clientes hospedados pelo varejo.</li>
</ul></td>
<td><ul>
<li>Trata os pontos críticos em torno das imagens hospedadas externamente, para evitar alternação de locais e, em vez disso, realizar o gerenciamento em um único lugar.</li>
<li>Oferece um gerenciamento de conteúdo eficiente por meio da Galeria de Mídia para imagens carregadas e hospedadas externamente, bem como fornece filtragem que ajuda a localizar imagens.</li>
<li>Permite que você crie facilmente associações em massa entre imagens hospedadas externamente e entidades, como produtos e catálogos.</li>
<li>Fornece suporte a armazenamento de imagens hospedado por varejo e integração do Excel para fácil atualização.</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="rich-clientele-experience"></a>Rica experiência de clientes

O varejo oferece experiências móveis imersivas em qualquer lugar, a qualquer momento e em qualquer dispositivo. A funcionalidade possibilita melhores experiências de compra e armazenamento em todos os canais.

<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Pesquise, procure, consulte ou examine produtos, adicione-os a um carrinho, aceite pagamento e faça check out usando uma experiência de usuário intuitiva, sensível ao toque, rica e imersiva no MPOS.</td>
<td>O AX 2012 habilita os seguintes recursos:
<ul>
<li>Realiza vendas, devoluções e anulações.</li>
<li>Crie, modifique e separe ordens de clientes.</li>
<li>Realize operações de turno e sacadoras.</li>
<li>Separe e receba ordens e realize contagens de estoque.</li>
<li>Exiba relatórios na loja.</li>
</ul></td>
<td>É fornecida paridade funcional com AX 2012 MPOS. Inclui a seguinte funcionalidade:
<ul>
<li>Pesquisa de cliente em lojas/canais.</li>
<li>A capacidade de criar ordens de cliente sem acessar o Serviço em Tempo Real.</li>
<li>Aprimoramento de fluxos de trabalho, status e mensagens de erro de ativação de dispositivos.</li>
<li>Melhorias de extensibilidade, como acionadores antes e depois e suporte de atividade para aprimorar a personalização.</li>
</ul></td>
<td>A equipe de vendas pode processar as transações de vendas e ordens de cliente e realizar operações diárias e gerenciamento de estoque, usando dispositivos móveis em qualquer lugar da loja.</td>
</tr>
<tr class="odd">
<td>Inicie o PDV como um aplicativo da Web por meio de um PDV em nuvem.</td>
<td>Não disponível</td>
<td>É fornecida paridade funcional com MPOS. Inclui a seguinte funcionalidade:
<ul>
<li>Ativação do dispositivo usando AAD</li>
<li>Design de layout responsivo</li>
<li>Suporte para os navegadores Edge, Internet Explorer e Chrome.</li>
</ul></td>
<td>Fornece um aplicativo da Web de PDV que apresenta funcionalidade compatível com o MPOS e que pode ser usado em plataformas e navegadores sem custo de implantação.</td>
</tr>
<tr class="even">
<td>Integração com sistemas de gerenciamento de conteúdo para criar um site de comércio eletrônico de canal omni.</td>
<td>Há compatibilidade com o Microsoft SharePoint e lojas de terceiros.</td>
<td>É fornecida uma plataforma de comércio eletrônico compatível com lojas de terceiros. A plataforma inclui os seguintes recursos:
<ul>
<li>Uma rica API de cliente.</li>
<li>Integração de autenticação a qualquer provedor de ID aberto de terceiros.</li>
<li>Integração de pagamento.</li>
</ul></td>
<td>Agora os clientes têm a flexibilidade de usar o sistema de gerenciamento de conteúdo de sua escolha.</td>
</tr>
<tr class="odd">
<td>Selecione clientes via catálogos de correspondência e simplifique as operações por meio de uma rápida entrada de ordem, vendas com apoio e atendimento usando call center.</td>
<td><ul>
<li>Canal de call center</li>
<li>Catálogos de correspondência</li>
<li>Rápida entrada de ordem e venda com apoio</li>
<li>Aprimoramento de cumprimento de ordem</li>
<li>Atendimento ao cliente</li>
<li>Preços e promoções/descontos integrados</li>
</ul></td>
<td>A paridade de recursos com a solução de call center do AX 2012 está disponível, com exceção das substituições de preço.</td>
<td>O call centers são um tipo de canal de varejo que permite aos trabalhadores assumir ordens de cliente por telefone e criar ordens de venda.</td>
</tr>
</tbody>
</table>

### <a name="commerce-essentials"></a>Fundamentos comerciais

Uma opção de configuração com foco em varejo e comércio ajuda a simplificar implantações específicas de varejo.

|                                               |                                                                                                             |                                                                                                                                                                               |                                                                                                                                                         |
|-----------------------------------------------|-------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                          | **Dynamics AX 2012**                                                                                        | **Dynamics AX 7.0**                                                                                                                                                           | **Por que isso é importante?**                                                                                                                              |
| Use o painel Fundamentos de comércio.        | Uma página da área com links para itens de menu está disponível.                                                         | O painel Fundamentos de comércio fornece links para tarefas frequentes, incluindo links para espaços de trabalho, controle da Web do Power BI, favoritos, páginas recentes e itens de trabalho atuais. | O painel aprimorado capacita os trabalhadores tornando-os mais eficientes e fornecendo um ponto de partida flexível para qualquer tarefa específica de varejo.             |
| Use as entidades de dados para acessar as alterações da conta.  | As alterações da conta são exportadas para uma pasta no sistema de arquivos.                                                | As alterações da conta são acessíveis por meio das entidades de dados.                                                                                                                         | Este recurso fornece maior flexibilidade ao movimentar dados entre sistemas distintos. Este recurso também pode ser aperfeiçoado por meio de aplicativos de OData. |
| Use PDV e MPDV em nuvem.                       | Somente o Enterprise POS (EPOS) é compatível de imediato.                                                     | MPOS e PDV em nuvem substituem o cliente (EPOS). O canal de comércio eletrônico também foi adicionado aos Fundamentos de comércio por padrão.                                                     | Este recurso habilita o suporte a canais imediatos maiores com clientes de ponto de venda de rápido implantação.                                                  |
| Implementa e mantém arquitetura de dois níveis. | A estrutura de importação/exportação de dados fornece a capacidade de movimentar dados entre o AX 2012 e sistemas de terceiros. | Entidades de dados criadas para aprimorar o suporte a arquitetura de dois níveis.                                                                                                           | Entidades de dados e aplicativos de OData fornecem camada de abstração para produzir cenários de dois níveis mais fáceis de serem implantados e mantidos.                          |
| Simplifique formulários.                               | Códigos personalizados são necessários para simplificar a interface de usuário.                                                                 | As extensões de formulário e menu fornecem simplificação padronizada da interface do usuário.                                                                                                              | Com este recurso, é mais fácil e rápido ajustar formulários com base nas necessidades do varejista.                                                             |

### <a name="pos-task-recorder"></a>Gravador de tarefas do PDV

<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Crie e compartilhe guias de tarefas e documentos para MPOS.</td>
<td>Não disponível</td>
<td>O gravador de tarefas do MPOS é compatível com os seguintes recursos:
<ul>
<li>Crie gravações de tarefas para várias tarefas que são realizadas no MPOS.</li>
<li>Gere um documento que inclui etapas e capturas de tela, associando-as a um nó no modelo de processo comercial.</li>
</ul></td>
<td>Parceiros e fornecedores de softwares independentes (ISVs) podem personalizar o MPOS e fornecer documentos de suporte para treinar seus usuários.</td>
</tr>
</tbody>
</table>

### <a name="extensibility"></a>Extensibilidade

<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Forneça suporte a componentes de varejo extensíveis e de fácil implantação em matrizes, call centers, comércio eletrônico e PDVs.</td>
<td>O componentes podem ser estendidos com o SDK de varejo. Nenhum recurso de embalagem e implantação é compatível.</td>
<td>Ganchos de extensibilidade são aperfeiçoados nos vários componentes para melhorar o isolamento e a capacidade de serviço do código de suporte. Estes são alguns dos recursos incluídos:
<ul>
<li>Fluxo de trabalho, atividade e operação.</li>
<li>Acionadores anteriores e posteriores que permitem estender facilmente um fluxo de trabalho.</li>
<li>Acionadores de aplicativo e operações.</li>
</ul>
Além disso, há uma estrutura disponível que permite que você construa e agrupe esses componentes usando o MSBuild, e depois implante diretamente sua personalização por meio do Microsoft Dynamics Lifecycle Services (LCS).</td>
<td>Os varejistas possuem exigências muito específicas, com base em verticais e geografias de operação. Fornecendo uma plataforma de fácil extensão, podemos habilitar o uso em verticais e mercados. Como o varejo também tem uma arquitetura muito distribuída, a capacidade de implantar diretamente melhora, de forma considerável, a produtividade.</td>
</tr>
</tbody>
</table>

### <a name="lifecycle-management"></a>Gerenciamento de ciclo de vida

O Lifecycle Services (LCS) fornece um conjunto de serviços que os clientes e parceiros podem usar para gerenciar o ciclo de vida de um sistema, de inscrição a operações diárias.

<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Gerencie o programa por meio dos serviços de implantação de nuvem.</td>
<td>Não disponível</td>
<td>As seguintes topologias podem ser implantadas na nuvem:
<ul>
<li>Topologia do teste de 1 caixa do varejo.</li>
<li>Topologia de alta disponibilidade de múltiplas caixas do varejo.</li>
<li>Topologia do desenvolvedor com o SDK do varejo.</li>
</ul>
Há um aprimoramento da instalação do componente do cliente de baixo contato por meio de instalação de autoatendimento:
<ul>
<li>PDV Moderno do Varejo.</li>
<li>Estação de Hardware do Varejo.</li>
<li>Suporte para o upload e distribuição de pacotes personalizados por meio da instalação de autoatendimento.</li>
</ul></td>
<td>Os serviços de implantação de nuvem proporcionam os seguintes benefícios:
<ul>
<li>Redução significativa do esforço e da complexidade de implantação para componentes da Matriz de Varejo.</li>
<li>Implantação nativa à nuvem pública do Microsoft Azure.</li>
<li>Instalação de autoatendimento aprimorada de componentes na loja para tornar a configuração mais fácil e intuitiva</li>
</ul></td>
</tr>
<tr class="odd">
<td>Monitore a saúde do sistema e faça um diagnóstico dos erros e problemas</td>
<td>Esta funcionalidade requer <a href="http://www.microsoft.com/en-us/download/details.aspx?id=42636">System Center 2012 Management Pack for Microsoft Dynamics AX 2012 R3 CU8 Retail</a>.</td>
<td>O monitoramento e diagnóstico de componentes de varejo agora é disponibilizado por meio do painel <strong>Informações operacionais</strong> no LCS.</td>
<td>O painel <strong>Informações operacionais</strong> é um portal de monitoramento baseado em nuvem que substitui a necessidade de instalar a infraestrutura do System Center Operations Manager (SCOM)</td>
</tr>
<tr class="even">
<td>Crie, configure, baixe e instale dispositivos e estação de hardware de varejo usando o autoatendimento.</td>
<td>Usando o empacotador de instalação e o Portal Empresarial, um usuário pode realizar uma instalação automática e a configuração de todos os componentes que são necessários em um computador específico, com base em uma topologia definida.</td>
<td>Como só há dois pacotes de instalação, um para o cliente do MPOS e o outro para o componente da estação de hardware de varejo, o autoatendimento reduziu a quantidade de trabalho que é necessária em cada nível para instalar esses componentes de cliente.</td>
<td>O autoatendimento tem como objetivo minimizar exigências e permitir que o usuário faça a instalação com mais facilidade.</td>
</tr>
</tbody>
</table>

## <a name="sales"></a>Venda
<table>






<tbody>
<tr class="odd">
<td><strong>O que você pode fazer?</strong></td>
<td><strong>Dynamics AX 2012</strong></td>
<td><strong>Dynamics AX 7.0</strong></td>
<td><strong>Por que isso é importante?</strong></td>
</tr>
<tr class="even">
<td>Obtenha uma rápida visualização de alternativas de entrega ao prometer ordens aos clientes.</td>
<td>Quando há restrições de disponibilidade de produtos e a data de entrega solicitada do cliente para um ou mais produtos na ordem não pode ser atendida, a tarefa de promessa de ordem torna-se um desafio. Para encontrar alternativas que possam compensar os problemas de disponibilidade e tempo de remessa de modo que a data solicitada do cliente possa ser atendida ou para oferecer uma solução de entrega que ele possa aceitar ou na qual ele possa confiar, o processador de ordem talvez precise abrir vários formulários, cada um dos quais oferecendo apenas um subconjunto das informações necessárias. Mais especificamente, um formulário mostra a quantidade disponível em sites, outro formulário mostra a quantidade disponível no ambiente intercompanhia, um terceiro formulário permite que os usuário calculem as datas mais antigas disponíveis para um site/variante de cada vez e o quarto formulário mostra ordens de fornecedor. Por esse motivo, os usuários não se sentem seguros de que consideraram todas as opções relevantes em vez de apenas escolherem uma solução imediata mas abaixo do ideal. Os usuários também não consideram isso eficaz, já que há várias interrupções durante o fluxo de promessa de ordens à medida que eles abrem e fecham diversas páginas e combinam as informações e opções.</td>
<td>Com base nos algoritmos existentes para o cálculo de data de entrega, a página <strong>Alternativas de entrega </strong>oferece uma nova experiência de usuário para a promessa de ordem:
<ul>
<li>Consolida as informações relevantes de vários formulários em um espaço.</li>
<li>Oferece pacotes de entrega alternativos “já feitos”, como um modo de combinação de site/depósito/variante/transporte, com base nos critérios de entrega mais rápida (data disponível mais antiga) que o usuário pode selecionar.</li>
<li>Permite que o usuário selecione opções da interface de simulação e as transfira para a linha de ordem de venda.</li>
</ul></td>
<td>Companhias que pretendem fornecer serviço ao cliente elevado comprometendo-se com uma estratégia de otimização de estoque devem ser capazes de prometer ordens de forma confiável e competitiva. Afinal, a própria empresa do cliente exige que os produtos estejam disponíveis a tempo. A página de tarefas <strong>Alternativas de entrega</strong> faz com que a tarefa de promessa de ordem seja mais rápida, fácil e sistemática identificando e recomendando as melhores datas de entrega de ordem alternativas em um espaço interativo.</td>
</tr>
</tbody>
</table>

## <a name="service-management"></a>Gerenciamento de serviços
Não foram adicionados novos recursos.

## <a name="transportation-management"></a>Gerenciamento de transporte
Não foram adicionados novos recursos.

## <a name="travel-and-expense"></a>Viagem e despesas
Não foram adicionados novos recursos.

## <a name="warehouse-management"></a>Gerenciamento de depósito
|                                                                       |                                                                                                                                                                                                              |                                                                                                                                                               |                                                                                                                                                                                      |
|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                  | **Dynamics AX 2012**                                                                                                                                                                                         | **Dynamics AX 7.0**                                                                                                                                           | **Por que isso é importante?**                                                                                                                                                           |
| Baixe, instale e configure o portal de Dispositivos Móveis de Depósito. | Você pode baixar, instalar e configurar o portal durante o processo de instalação do Microsoft Dynamics AX, por meio de uma instalação padrão. É desenvolvido para implantação e configuração automáticas e locais. | Você pode baixar um instalador autônomo por meio do item de menu no gerenciamento de depósito. É desenvolvido para implantação e configuração automáticas e locais. | Ao configurar a funcionalidade de dispositivo móvel, você deve instalar e configurar o Portal de Dispositivos Móveis de Depósito localmente e obter uma conexão com o Dynamics AX na nuvem. |



<a name="see-also"></a>Consulte também
--------

[Novidades e alterações](whats-new-changed.md)

[Novas guias de tarefas disponíveis (fevereiro de 2016)](new-task-guides-available-february-2016.md)





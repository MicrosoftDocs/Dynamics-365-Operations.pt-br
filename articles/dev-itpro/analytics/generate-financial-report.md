---
title: Gerar relatórios financeiros
description: Este tópico fornece informações sobre gerar um relatório financeiro.
author: aprilolson
manager: AnnBe
ms.date: 09/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 70fa1298c3af43f62b8fa0b833fa817f17858c47
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "340881"
---
# <a name="generate-financial-reports"></a>Gerar relatórios financeiros

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre gerar um relatório financeiro.

Para gerar um relatório, abra a definição de relatório e clique no botão Gerar na barra de ferramentas. A janela Status da Fila de Relatórios será aberta e indicará a localização do relatório na fila. Por padrão, o relatório gerado será aberto no Visualizador da Web.

As seguintes opções estão disponíveis para geração de relatórios:

- Configurar um plano para gerar automaticamente um relatório ou um grupo de relatórios
- Verificar se há contas ou dados ausentes em um relatório, e validar a precisão de um relatório

Quando você gera um relatório, as opções especificadas nas guias Definição de relatório são usadas.

## <a name="generate-a-financial-report"></a>Gerar um relatório financeiro

Para gerar um relatório financeiro com o Microsoft Dynamics 365 for Finance and Operations, vá para **Contabilidade** \> **Consultas e relatórios** \> **Relatórios financeiros**.

- Selecione um relatório para gerar e clique em **Gerar**.
- Preencha o campo **Data do relatório** e clique em **OK**.

Depois que o relatório for gerado, ele estará disponível para exibição na seção **Relatórios**.

Você pode selecionar **Exibir** ou **Excluir** o relatório.

Para gerar um relatório usando o **Designer de relatórios**, abra a definição de relatório e, em seguida, clique no botão Gerar na barra de ferramentas. A janela Status da Fila de Relatórios será aberta e indicará a localização do relatório na fila. Por padrão, o relatório gerado será aberto no Visualizador da Web.

## <a name="schedule-report-generation"></a>Programar geração de relatórios
Várias empresas têm um conjunto de relatórios principais que são executados nos intervalos programados para alinhas com processos de negócios. Você pode programar a geração de um relatório como diária, semanal, mensal ou anual. Isso pode ser um relatório exclusivo ou um grupo de relatórios que inclui várias empresas. Você deve inserir suas credenciais para cada uma das empresas especificadas, como essas em uma definição de hierarquia organizacional. Se as credenciais não forem válidas, o relatório exibirá apenas as informações que você tem permissão para acessar, como a empresa em que está registrado no momento. As informações de saída são lidas primeiro do grupo de relatórios e, depois, de relatórios individuais.

Quando agendamentos de relatório são criados e salvos, eles são exibidos no painel de navegação em Agendamentos de Relatório. Você pode criar pastas para organizar seus relatórios. Se um único relatório em um plano não é for executado, todos os relatórios que continuarão em execução.

> [!IMPORTANT]
> Para criar, modificar e excluir agendas de relatórios, você deve ter a função de criador ou administrador. Quando um relatório é executado, as credenciais do usuário que criou o plano são usadas para gerar o relatório.

### <a name="create-a-report-schedule"></a>Criar um agendamento de relatório

1. No Designer de Relatórios, no menu Arquivo, clique em Novo e selecione Agendamento de relatório. A caixa de diálogo Novo Agendamento de Relatório é aberta.
2. Em Configurações, selecione um relatório individual ou um grupo de relatórios para agendar. Somente os relatórios ou grupos de relatórios para seleção de empresa ou de bloco de construção na qual você fez o logon estão disponíveis.
3. Selecione a caixa de seleção Ativa para ativar a agenda de relatório. Somente o criador de relatório ou um administrador pode ativar ou desativar uma agenda do relatório.
4. Clique no botão Permissões para inserir as credenciais da empresa. Por padrão, as informações de logon é usada para a empresa que você fez logon. Se outras empresas estiverem incluídas, como em definições da hierarquia organizacional, Usar credenciais separadas, e insira as credenciais de outra empresa incluída na agenda do relatório. Você pode selecionar Autenticação do Windows ou digite um nome de usuário e uma senha para cada empresa. Marque a caixa de seleção Salvar credenciais para salvar as credenciais dessas empresas. Depois, clique em OK para fechar a caixa de diálogo.
5. Em Frequência, no campo Início de recorrência, selecione a data em que o agendamento é iniciado. Por padrão, a data do sistema atual do computador do cliente é selecionada.
6. No campo de Executar relatório em, selecione a hora em que o relatório deve executado. Se você inserir uma hora que se seja antes da hora do sistema atual, o relatório será executado na próxima data programada.
7. Na área Padrão de recorrência, especifique a frequência de execução do relatório. Por padrão, Diariamente é selecionado com um valor de Intervalo (dias) de 1. Outras opções incluem Semanalmente, Mensalmente e Anualmente.
8. Na área Intervalo de recorrência, selecione quando o relatório deve parar de ser gerado.

    - Nenhuma data final – A agenda do relatório é executada de maneira indefinida.
    - Definir número de ocorrências – A agenda de relatório é executada para o número específico de vezes e é desativada.
    - Finalizado até – A agenda de relatório é finalizada na data especificada.

9. Clique em Salvar na barra de ferramentas. Na caixa de diálogo Salvar Como, insira um nome exclusivo e uma descrição para o agendamento de relatório.

Para copiar um agendamento de relatório, você deve ter a função de designer ou administrador. Mesmo que um administrador mude o agendamento de relatório, o relatório manterá as credenciais do usuário que criou o relatório.

### <a name="copy-a-report-schedule"></a>Copiar um agendamento de relatório

1. No Designer do Relatórios, clique em Agendamentos de Relatório no painel de navegação, e abra um agendamento de relatório a ser copiado.
2. No menu Arquivo, clique em Salvar como e digite um novo nome e descrição para o plano na caixa de diálogo Salvar como. Clique em OK e o novo plano é exibido no painel de navegação.
3. Na nova agenda, modifique os campos e as informações conforme necessário. Clique em Salvar na barra de ferramentas ou em Salvar no menu Arquivo.

Para excluir um agendamento de relatório, você deve ser proprietário do agendamento de relatório ou ter uma função administrador.

### <a name="delete-a-report-schedule"></a>Excluir um agendamento de relatório

1. No Designer de Relatórios, clique em Agendamentos de Relatórios no painel de navegação.
2. Selecione a agenda de relatório a ser excluída e clique em Excluir ou pressione a tecla Delete.
3. Na caixa de diálogo de verificação de exclusão, clique em Sim para excluir permanentemente a agenda do relatório. Se você não tiver permissão para excluir o agendamento, será exibida uma mensagem e o relatório não será excluído.

### <a name="credentials-and-report-schedules"></a>Credenciais e agendas de relatório

Se você não inserir credenciais necessárias para todas as empresas incluídas nos relatórios, receberá a seguinte mensagem ao salvar o agendamento de relatório: “Você deve inserir suas credenciais para as empresas contidas neste agendamento de relatório. Selecione o botão de Permissões para inserir suas credenciais”.

Por exemplo, Phyllis entra na empresa A usando seu logon e senha. Ela cria uma agenda para um relatório que usa uma definição de árvore de relatório para coletar dados de várias empresas. Quando essa agenda do relatório é salva, é solicitado que Phyllis insira credenciais para outras empresas que são especificadas na definição de hierarquia organizacional. Quando suas credenciais expiram, os relatórios afetados no agendamento de relatório não são gerados até que as credenciais sejam atualizadas. Uma mensagem é exibida na fila de relatórios para indicar que as permissões devem ser atualizadas. O agendamento de relatório falha quando um destes cenários ocorre (porque eles exigem credenciais):

- Uma nova empresa foi adicionada a uma árvore de relatório para um relatório individual.
- Um relatório em um grupo de relatórios foi alterado.
- Um novo relatório para uma empresa adicional foi adicionado a um grupo de relatórios.

Para continuar, clique no botão Permissões na caixa de diálogo Agendamento de Relatórios. Em seguida, insira as credenciais apropriadas.

## <a name="missing-account-analysis-feature"></a>Recurso de análise de conta ausente
Você pode procurar contas financeiras e dimensões que possam estar ausentes em todas as definições de linha, definições de árvore de relatório e definições de relatório em um grupo de blocos de construção. Isso é útil quando você cria ou atualiza várias contas ou blocos de construção em um curto período de tempo, e você deseja verificar se todas as novas informações foram incluídas nos relatórios.

As contas ausentes são determinadas usando os valores inferiores e superiores da definição de linha ou a definição de árvore de relatório. Ele exibe uma lista de contas que não estão na definição de linha ou na definição da árvore de relatório, mas que constam nos dados financeiros. Se uma conta ausente for maior ou menor do que os valores na definição de linha, essa conta não está incluída na lista de contas ausentes.

> [!TIP]
> Para fins de validação, esse processo deve ser executado antes de gerar os relatórios mensais e ao criar novos blocos de construção.

Relatórios com intervalos de valores têm menor probabilidade de ter contas ausentes. Quando possível, use intervalos no bloco de construção para incluir as contas novas quando elas forem criadas. Se qualquer definição de relatório estiver definida como empresa @ANY, você pode fazer logon em uma empresa específica e executar uma análise de conta ausente para essa empresa.

> [!NOTE]
> Se uma nova empresa for adicionada, adicione a nova empresa às árvores de relatório em todos os relatórios existentes; senão, a empresa não será incluída na análise de conta ausente.

### <a name="run-missing-account-analysis"></a>Executar a análise de conta ausente

1. No Designer de Relatórios, clique em Ferramentas e em Análise de Conta Ausente.
2. No campo Filtro de empresa, selecione a empresa pela qual filtrar os resultados, ou selecione Tudo (sem filtro) para exibir os resultados de todas as empresas disponíveis.
3. No campo Filtro de dimensão, selecione a dimensão pela qual filtrar os resultados, ou selecione Tudo (sem filtro) para exibir todas as informações de dimensão de todas as dimensões disponíveis.
4. No campo Agrupar por, selecione uma opção para classificar os resultados. É possível classificar os resultados de acordo com o bloco de construção que é afetado, ou classificar os resultados por conjuntos de dimensões e de valor.
5. Revisar os resultados exibidos. Ao selecionar um item no painel superior, o painel inferior exibe as informações adicionais sobre a exceção. Isso inclui os relatórios, as dimensões, e os valores relacionados.
6. Para abrir o item afetado, clique no ícone associado que é exibido no painel da lista, ou clique com o botão direito do mouse no item e selecione Abrir. Para selecionar vários itens, mantenha pressionada a tecla Ctrl enquanto seleciona os itens no painel inferior.
7. Se algum valor, bloco de construção ou relatório for retornado que não deva ser incluído na análise, clique com o botão direito do mouse no item e selecione Excluir. Ou marque a caixa de seleção Excluir ao lado do item para removê-lo da lista. Os itens excluídos não são incluídos quando a lista é atualizada. Para selecionar vários itens, mantenha pressionada a tecla CTRL enquanto seleciona os itens no painel inferior. Para exibir todos os itens, incluindo os resultados que você selecionou anteriormente para serem excluídos da análise, marque a caixa de seleção Mostrar os blocos de construção e os valores excluídos e, em seguida, clique em Atualizar.
8. Clique em Atualizar para atualizar as exceções que você resolveu. Clique em Sim para executar uma atualização completa de todos os resultados, ou clique em Não para executar uma atualização parcial dos itens resolvidos.

    > [!NOTE]
    > O formulário é atualizado automaticamente quando aberto, a menos que ele tenha sido aberto nos últimos 15 minutos.

9. Quando os problemas forem resolvidos, clique em OK para fechar a caixa de diálogo.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Atalhos de teclado para a análise de conta ausente
Quando você executa uma análise de conta ausente, os atalhos de teclado a seguir estão disponíveis.

| Para                           | Use este atalho de teclado |
|--------------------------------------|----------------------------|
| Filtrar por empresa                    | Alt+C                      |
| Filtrar por dimensão                  | Alt+D                      |
| Selecione o campo Agrupar por            | Alt+G                      |
| Mostrar os blocos e os valores excluídos      | Alt+S                      |
| Atualizar os resultados                      | Alt+R                      |
| Excluir o bloco de construção selecionado  | Alt+X                      |
| Excluir a definição de linha selecionada  | Ctrl+B                     |
| Excluir o valor de dimensão selecionado | Ctrl+D                     |
| Abrir a definição de relatório selecionada  | Ctrl+R                     |
| Abrir a definição de linha selecionada     | Ctrl+O                     |


## <a name="additional-resources"></a>Recursos adicionais

[Relatórios financeiros](financial-reporting-intro.md)

[Interface do Report Designer](report-designer-interface.md)

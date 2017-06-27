---
title: "Gerar um relatório financeiro"
description: "Este tópico fornece informações sobre gerar um relatório financeiro."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9b0d8fd9f5ae9d99f299cc71d7caef021ad3fb9d
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="generate-a-financial-report"></a>Gerar um relatório financeiro

[!include[banner](../includes/banner.md)]


Este tópico fornece informações sobre gerar um relatório financeiro. 

Para gerar um relatório, abra a definição de relatório e clique no botão Gerar na barra de ferramentas. A janela Status da Fila de Relatórios será aberta e indicará a localização do relatório na fila. Por padrão, o relatório gerado será aberto no Visualizador Web.
| ![Observação](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Observação")**Observação**        |
|------------------------------------------------------------------------------------------------|
| Você pode gerar relatórios somente para pastas e locais em que você tem permissão de acesso. |

A tabela a seguir explica as opções disponíveis para gerar relatórios.

| Opção                                                                                | Para obter mais informações |
|---------------------------------------------------------------------------------------|----------------------|
| Configurar um plano para gerar automaticamente um relatório ou um grupo de relatórios              |                      |
| Verificar se há contas ou dados ausentes em um relatório, e validar a precisão de um relatório |                      |

Quando você gera um relatório, as opções especificadas nas guias Definição de relatório são usadas. A guia Saída e Distribuição permite especificar um local da biblioteca do relatório, que é uma maneira fácil de compartilhar o relatório.

## <a name="schedule-report-generation"></a>Agendar a geração de relatórios
Várias empresas têm um conjunto principal de relatórios que são executados em intervalos programados para alinhar com seus processos comerciais. Você pode programar a geração de um relatório como diária, semanal, mensal ou anual. Pode ser um único relatório ou um grupo de relatórios que inclui várias empresas. Você deve inserir suas credenciais para cada empresa especificada, como as da definição de uma árvore de relatório. Se as credenciais não forem válidas, o relatório exibirá apenas as informações que você tem permissão para acessar, como a empresa em que está registrado no momento. As informações de saída são lidas primeiro do grupo de relatórios e, depois, de relatórios individuais.

Quando agendamentos de relatório são criados e salvos, eles são exibidos no painel de navegação em Agendamentos de Relatório. Você pode criar pastas para organizar os relatórios. Se um único relatório em um plano não for executado, todos os demais relatórios continuarão em execução.
| ![Importante](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Importante")**Importante**                                                                                                           |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Para criar, modificar e excluir agendamentos de relatório, você deve ter a função de designer ou administrador. Quando um relatório é executado, as credenciais do usuário que criou o plano são usadas para gerar o relatório. |

### <a name="create-a-report-schedule"></a>Criar um agendamento de relatório

1.  No Designer de Relatórios, no menu Arquivo, clique em Novo e selecione Agendamento de relatório. A caixa de diálogo Novo Agendamento de Relatório é aberta.
2.  Em Configurações, selecione um relatório individual ou um grupo de relatórios para agendar. Só estão disponíveis os relatórios ou grupos de relatórios para seleção da empresa ou do bloco de construção no qual você está conectado no momento.
3.  Marque a caixa de seleção Ativo para ativar o agendamento do relatório. Somente o criador do relatório ou um administrador pode ativar ou desativar um agendamento de relatório.
4.  Clique no botão Permissões para inserir as credenciais da empresa. Por padrão, as informações de logon são usadas para a empresa em que você está conectado. Se outras empresas estão incluídas, como em definições de árvore de relatório, selecione Usar credenciais separadas e insira as credenciais para qualquer outra empresa incluída no planejamento de relatório. Você pode selecionar Autenticação do Windows ou digitar um nome de usuário e senha para cada empresa. Marque a caixa de seleção Salvar credenciais para salvar as credenciais dessas empresas. Depois, clique em OK para fechar a caixa de diálogo.
5.  Em Frequência, no campo Início de recorrência, selecione a data em que o agendamento é iniciado. Por padrão, a data atual do sistema do computador cliente está selecionada.
6.  No campo Executar relatório em, selecione a hora em que o relatório deve ser executado. Se você inserir uma hora que anterior à hora do sistema atual, o relatório será executado na próxima data agendada.
7.  Na área Padrão de recorrência, especifique a frequência de execução do relatório. Por padrão, Diariamente é selecionado com um valor de Intervalo (dias) de 1. Outras opções incluem Semanalmente, Mensalmente e Anualmente.
8.  Na área Intervalo de recorrência, selecione quando o relatório deve parar de ser gerado.
    -   Nenhuma data final – O agendamento de relatório é executado indefinidamente.
    -   Definir número de ocorrências – O agendamento de relatório é executado no número especificado de vezes, e depois é desativado.
    -   Terminar em – O agendamento de relatório termina na data especificada.

9.  Clique em Salvar na barra de ferramentas. Na caixa de diálogo Salvar Como, insira um nome exclusivo e uma descrição para o agendamento de relatório.

Para copiar um agendamento de relatório, você deve ter a função de designer ou administrador. Mesmo que um administrador mude o agendamento de relatório, o relatório manterá as credenciais do usuário que criou o relatório.
### <a name="copy-a-report-schedule"></a>Copiar um agendamento de relatório

1.  No Designer do Relatórios, clique em Agendamentos de Relatório no painel de navegação, e abra um agendamento de relatório a ser copiado.
2.  No menu Arquivo, clique em Salvar Como, e insira um novo nome e descrição da agenda na caixa de diálogo Salvar Como. Clique em OK, e a nova agenda será exibida no painel de navegação.
3.  Na nova agenda, modifique os campos e as informações conforme necessário. Clique em Salvar na barra de ferramentas ou em Salvar no menu Arquivo.

Para excluir um agendamento de relatório, você deve ser proprietário do agendamento de relatório ou ter uma função administrador.
### <a name="delete-a-report-schedule"></a>Excluir um agendamento de relatório

1.  No Designer de Relatórios, clique em Agendamentos de Relatórios no painel de navegação.
2.  Selecione o agendamento de relatório a ser excluído. Clique em Excluir ou pressione a tecla Excluir.
3.  Na caixa de diálogo de verificação de exclusão, clique em Sim para excluir permanentemente o agendamento de relatório. Se você não tiver permissão para excluir o agendamento, será exibida uma mensagem e o relatório não será excluído.

### <a name="credentials-and-report-schedules"></a>Credenciais e agendamentos de relatório

Se você não inserir credenciais necessárias para todas as empresas incluídas nos relatórios, receberá a seguinte mensagem ao salvar o agendamento de relatório: “Você deve inserir suas credenciais para as empresas contidas neste agendamento de relatório. Selecione o botão Permissões para inserir suas credenciais.”

Por exemplo, a Phyllis faz logon na empresa A usando seu logon e senha. Ela cria uma agenda para um relatório que usa uma definição de árvore de relatório para coletar dados de várias empresas. Quando esse agendamento de relatório é salvo, a Phyllis é solicitada a inserir as credenciais das outras empresas que são especificadas na definição da árvore de relatório. Quando suas credenciais expiram, os relatórios afetados no agendamento de relatório não são gerados até que as credenciais sejam atualizadas. Uma mensagem é exibida na fila de relatórios para indicar que as permissões devem ser atualizadas. O agendamento de relatório falha quando um destes cenários ocorre (porque eles exigem credenciais):
-   Uma nova empresa foi adicionada a uma árvore de relatório para um relatório individual.
-   Um relatório foi modificado em um grupo de relatórios.
-   Um novo relatório de uma empresa extra foi adicionado a um grupo de relatórios.

Para continuar, clique no botão Permissões na caixa de diálogo Agendamento de Relatórios. Em seguida, insira as credenciais apropriadas.

## <a name="missing-account-analysis-feature"></a>Recurso de análise de conta ausente
Você pode procurar contas financeiras e dimensões que possam estar ausentes em todas as definições de linha, definições de árvore de relatório e definições de relatório em um grupo de blocos de construção. Isso é útil quando você cria ou atualiza várias contas ou blocos de construção em um curto período de tempo, e você deseja verificar se todas as novas informações foram incluídas nos relatórios.

As contas ausentes são determinadas usando os valores inferiores e superiores da definição de linha ou a definição de árvore de relatório. Ele exibe uma lista de contas que não estão na definição de linha ou na definição da árvore de relatório, mas que constam nos dados financeiros. Se uma conta ausente for maior ou menor do que os valores na definição de linha, essa conta não será incluída na lista de contas ausentes.
| ![Dica](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Dica")**Dica**                                             |
|----------------------------------------------------------------------------------------------------------------------------------|
| Para fins de validação, esse processo deve ser executado antes de você gerar relatórios mensais e quando você criar novos blocos de construção. |

Relatórios com intervalos de valores têm menor probabilidade de ter contas ausentes. Quando possível, use intervalos no bloco de construção para incluir novas contas ao criá-las. Se qualquer definição de relatório for definida como @ANY, você poderá fazer logon em uma empresa específica e executar uma análise de conta ausente para essa empresa.
| ![Observação](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Observação")**Observação**                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se uma nova empresa for adicionada, adicione a nova empresa às árvores de relatório em todos os relatórios existentes; senão, a empresa não será incluída na análise de conta ausente. |

### <a name="run-missing-account-analysis"></a>Executar a análise de conta ausente

1.  No Designer de Relatórios, clique em Ferramentas e em Análise de Conta Ausente.
2.  No campo Filtro da empresa, selecione uma empresa para filtrar os resultados, ou selecione Todas (sem filtro) para exibir os resultados de todas as empresas disponíveis.
3.  No campo Filtro de dimensão, selecione uma dimensão para filtrar os resultados, ou selecione Todas (sem filtro) para exibir todas as informações de dimensão de todas as dimensões disponíveis.
4.  No campo Agrupar por, selecione uma opção para classificar os resultados. Você pode classificar resultados de acordo com o bloco de construção afetado, ou pode classificar resultados por dimensão e conjuntos de valores.
5.  Analisar os resultados exibidos. Quando você seleciona um item no painel superior, o painel inferior exibe informações adicionais sobre a exceção. Isso inclui dimensões, valores e relatórios relacionados.
6.  Para abrir o item afetado, clique no ícone associado que é exibido no painel da lista, ou clique com o botão direito do mouse no item e selecione Abrir. Para selecionar vários itens, mantenha pressionada a tecla Ctrl enquanto seleciona os itens no painel inferior.
7.  Se algum valor, bloco de construção ou relatório for retornado que não deva ser incluído na análise, clique com o botão direito do mouse no item e selecione Excluir. Ou marque a caixa de seleção Excluir ao lado do item para removê-lo da lista. Os itens excluídos não são incluídos quando a lista é atualizada. Para selecionar vários itens, mantenha pressionada a tecla Ctrl enquanto seleciona os itens no painel inferior. Para exibir todos os itens, incluindo resultados antes selecionados para excluir da análise, marque a caixa de seleção Mostrar blocos de construção e valores excluídos. Depois, clique em Atualizar.
8.  Clique em Atualizar para atualizar exceções que você tratou. Clique em Sim para executar uma atualização completa de todos os resultados. Ou clique em Não para executar uma atualização parcial de itens tratados.
    | ![Observação](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Observação")**Observação**                    |
    |------------------------------------------------------------------------------------------------------------|
    | O formulário é atualizado automaticamente quando é aberto, a menos que ele tenha sido aberto nos últimos 15 minutos. |

9.  Quando os problemas forem resolvidos, clique em OK para fechar a caixa de diálogo.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Atalhos de teclado para a análise de conta ausente
Quando você executa uma análise de conta ausente, os atalhos de teclado a seguir estão disponíveis.

| Para                           | Use este atalho de teclado |
|--------------------------------------|----------------------------|
| Filtrar por empresa                    | Alt+C                      |
| Filtrar por dimensão                  | Alt+D                      |
| Selecionar o campo Agrupar por            | Alt+G                      |
| Mostrar blocos e valores excluídos      | Alt+S                      |
| Atualizar resultados                      | Alt+R                      |
| Excluir o bloco de construção selecionado  | Alt+X                      |
| Excluir a definição de linha selecionada  | Ctrl+B                     |
| Excluir o valor de dimensão selecionado | Ctrl+D                     |
| Abrir a definição de relatório selecionada  | Ctrl+R                     |
| Abrir a definição de linha selecionada     | Ctrl+O                     |

 
<a name="see-also"></a>Consulte também
--------

[Relatórios financeiros](financial-reporting-intro.md)

[Interface do Designer de Relatórios](report-designer-interface.md)




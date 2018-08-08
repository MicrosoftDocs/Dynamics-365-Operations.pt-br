---
title: "Modelos de planejamento de orçamento para Excel"
description: "Este tópico descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento."
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 156688b705337331e083ebc19fded57b028acb67
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-templates-for-excel"></a>Modelos de planejamento de orçamento para Excel

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento.

Este tópico mostra como criar modelos do Excel que serão usados com planos de orçamento por meio do conjunto de dados de demonstração padrão e do logon de usuário Administrador. Para obter mais informações sobre planejamento de orçamento, consulte [Visão geral do planejamento de orçamento.](budget-planning-overview-configuration.md) Você também pode acompanhar o tutorial [Planejamento de orçamento 101](budget-plan.md) para aprender princípios básicos de configuração e uso de módulos.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Gerar uma planilha usando o layout de documento de plano de orçamento

Documentos de plano de orçamento podem ser exibidos e editados com um ou vários layouts. Cada layout pode ter um modelo de documento de plano de orçamento associado para exibir e editar os dados do plano de orçamento em uma planilha do Excel. Neste tópico, um modelo de documento de plano de orçamento será gerado por meio de uma configuração de layout existente. 

1. Abra a **Lista de planos de orçamento** (**Orçamento** &gt; **Planos de orçamento**). 
2. Clique em **Novo** para criar um novo documento de plano de orçamento. 

   [![Lista de planos de orçamento](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Use a opção de linha **Adicionar** para adicionar linhas. Clique em **Layouts** para exibir a configuração de layout do documento de plano de orçamento. 

   [![Adição de planos de orçamento](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Você pode revisar a configuração do layout e ajustá-la quando necessário. 
1. Vá para **Modelo** &gt; **Gerar** para criar um arquivo do Excel para esse layout. 
2. Após a criação do modelo, vá para **Modelo** &gt; **Exibir** para abrir ou revisar o modelo de documento de plano de orçamento. É possível salvar o arquivo do Excel na sua unidade local. 

[![Salvar como](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> O layout de documento do plano do orçamento não pode ser editado depois que um modelo do Excel é associado a ele. Para alterar o layout, exclua o arquivo do modelo do Excel associado e gere-o novamente. Isso é necessário para manter os campos no layout e na planilha sincronizados. 

O modelo do Excel conterá todos os elementos do layout do documento de plano de orçamento, no qual a coluna **Disponível em planilha** é definida como Verdadeira. Não é possível sobrepor elementos no modelo do Excel. Por exemplo, se o layout contiver as colunas Solicitação Q1, Solicitação Q2, Solicitação Q3 e Solicitação Q4 e uma coluna com o total de solicitações representando a soma de todas as 4 colunas trimestrais, apenas as colunas trimestrais ou a coluna com o total estarão disponíveis para serem usadas no modelo do Excel. O arquivo do Excel pode atualizar a sobreposição de colunas durante a atualização, já que os dados na tabela poderiam ficar desatualizados e se tornar imprecisos.

[![Exemplo](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> Para evitar possíveis problemas com a exibição e edição de dados de plano de orçamento usando o Excel, o mesmo usuário deve estar conectado tanto ao Microsoft Dynamics 365 for Finance and Operations quanto ao Microsoft Dynamics Office Add-in Data Connector.

## <a name="add-a-header-to-budget-plan-document-template"></a>Adicionar um cabeçalho ao modelo de documento de plano de orçamento
Para adicionar informações de cabeçalho, selecione a linha superior no arquivo do Excel e insira linhas vazias. Clique em **Design** no **Conector de Dados** para adicionar campos de cabeçalho ao arquivo do Excel.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

Na guia **Design**, clique nos campos **Adicionar** e, em seguida, selecione **BudgetPlanHeader** como a fonte de dados da entidade.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

Aponte o cursor para o local desejado no arquivo do Excel. Clique em **Adicionar etiqueta** para adicionar a etiqueta do campo ao local selecionado. Selecione **Adicionar Valor** para adicionar o campo de valor ao local selecionado. Clique em **Concluído** para fechar o designer.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Adicionar uma coluna calculada à tabela do modelo de documento de plano de orçamento
--------------------------------------------------------------

Em seguida, colunas calculadas serão adicionadas ao modelo de documento de plano de orçamento gerado. Uma coluna **Total de Solicitações**, que resume as colunas Solicitação Q1: Solicitação Q4, e uma coluna **Ajuste**, que recalcula a coluna **Total de Solicitações** por um fator predefinido.

Clique em **Design** no **Conector de Dados** para adicionar colunas à tabela. Clique em **Editar** ao lado da fonte de dados **BudgetPlanWorksheet** para iniciar a adição das colunas.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

O grupo de campos selecionado exibe a coluna que está disponível no modelo. Clique em **Fórmula** para adicionar uma nova coluna. Nomeie a nova coluna e depois cole a fórmula no campo **Fórmula**. Clique em **Atualizar** para inserir a coluna.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Para definir a fórmula, crie a fórmula na planilha e depois copie-a na janela **Design**. Uma tabela vinculada do Finance and Operations geralmente será nomeada como "AXTable1". Por exemplo, para resumir as colunas Solicitação Q1 : Solicitação Q4 na planilha, a fórmula = AxTable1\[Solicitação Q1\]+AxTable1\[Solicitação Q2\]+AxTable1\[Solicitação Q3\]+AxTable1\[Solicitação Q4\].

Repita essas etapas para inserir a coluna **Ajuste**. Use a fórmula = AxTable1\[Total da solicitações\]\*$I$1 para essa coluna. Isso usará o valor na célula I1 e multiplicará os valores na coluna **Total de solicitações** para calcular os valores de ajuste.

Salve e feche o arquivo do Excel. Retorne ao Finance and Operations e, em **Layouts**, clique em **Modelo &gt; Carregar** para carregar o modelo do Excel salvo que será usado no plano de orçamento. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Feche o controle deslizante **Layouts**. No documento **Plano de orçamento**, clique em **Planilha** para exibir e editar o documento no Excel. Observe que o modelo do Excel ajustado foi usado para criar essa planilha de plano de orçamento e as colunas calculadas são atualizadas por meio de fórmulas que foram definidas nas etapas anteriores. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Dicas e truques para criar modelos de plano de orçamento
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Posso adicionar e usar fontes de dados adicionais em um modelo de plano de orçamento?

Sim, você pode usar o menu **Design** para adicionar mais entidades às mesmas ou a outras planilhas no modelo do Excel. Por exemplo, você pode adicionar as fontes de dados **BudgetPlanProposedProject** para criar e manter uma lista de projetos propostos ao trabalhar com dados de plano de orçamento no Excel. Observe que a inclusão de alto volume de fontes de dados pode ter impacto sobre o desempenho da pasta de trabalho do Excel. 

Você pode usar a opção **Filtro** no **Conector de Dados** para adicionar os filtros desejados a fontes de dados adicionais.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Posso ocultar a opção Design no Conector de Dados para outros usuários?

Sim, abra as opções **Conector de Dados** para ocultar a opção **Design** de outros usuários.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Expanda as **Opções de conector de dados** e desmarque a caixa de seleção **Habilitar design**. Isso ocultará a opção **Design** do **Conector de Dados**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Posso impedir que usuários fechem acidentalmente o Conector de Dados ao trabalhar com dados?

Recomendamos o bloqueio do modelo para impedir que usuários o fechem. Para ativar o bloqueio, clique no **Conector de Dados**, no canto superior direito no qual aparece uma seta. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Clique na seta para obter um menu adicional. Selecione **Bloqueio**.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Posso usar outros recursos do Excel, como formatação de células, formatação condicional e gráficos com meus modelos de plano de orçamento?

Sim, a maior parte dos recursos padrão do Excel funcionará nos modelos de plano de orçamento. Recomendamos o uso da codificação por cor para que os usuários diferenciem entre colunas somente leitura e editáveis. A formatação condicional pode ser usada para destacar áreas problemáticas do orçamento. Os totais de coluna podem facilmente ser apresentados por meio de fórmulas padrão do Excel acima da tabela.

Você também pode criar e usar tabelas e gráficos dinâmicos para mais agrupamentos e visualizações de dados de orçamento. Na guia **Dados**, no grupo **Conexões**, clique em **Atualizar Tudo** e depois clique em **Propriedades da Conexão**. Clique na guia **Uso**. Em **Atualizar**, marque a caixa de seleção **Atualizar dados ao abrir o arquivo**. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)





---
title: Modelos de plano de orçamento para Excel
description: Este artigo descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: kfend
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8996ad5d03327b9273be7860a3905dc25efa7e90
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070654"
---
# <a name="budget-planning-templates-for-excel"></a>Modelos de plano de orçamento para Excel

[!include [banner](../includes/banner.md)]

Este artigo descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento.

Este artigo mostra como criar modelos do Excel que serão usados com planos de orçamento por meio do conjunto de dados de demonstração padrão e do logon de usuário Administrador. Para obter mais informações sobre planejamento de orçamento, consulte [Visão geral do planejamento de orçamento.](budget-planning-overview-configuration.md). Você também pode acompanhar o tutorial [Planejamento de orçamento](budget-plan.md) para aprender os princípios básicos de configuração e uso de módulos.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Gerar uma planilha usando o layout de documento de plano de orçamento

Documentos de plano de orçamento podem ser exibidos e editados com um ou vários layouts. Cada layout pode ter um modelo de documento de plano de orçamento associado para exibir e editar os dados do plano de orçamento em uma planilha do Excel. Neste artigo, um modelo de documento de plano de orçamento será gerado por meio de uma configuração de layout existente. 

1. Abra a **Lista de planos de orçamento** (**Orçamento** &gt; **Planos de orçamento**). 
2. Clique em **Novo** para criar um novo documento de plano de orçamento. 

   [![Lista de planos de orçamento.](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Use a opção de linha **Adicionar** para adicionar linhas. Clique em **Layouts** para exibir a configuração de layout do documento de plano de orçamento. 

   [![Adição de planos de orçamento.](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Você pode revisar a configuração do layout e ajustá-la quando necessário. 
1. Acesse **Modelo** &gt; **Gerar** para criar um arquivo do Excel para esse layout. 
2. Após a criação do modelo, Acesse **Modelo** &gt; **Exibir** para abrir ou revisar o modelo de documento de plano de orçamento. É possível salvar o arquivo do Excel na sua unidade local. 

[![Salvar como.](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> O layout de documento do plano do orçamento não pode ser editado depois que um modelo do Excel é associado a ele. Para alterar o layout, exclua o arquivo do modelo do Excel associado e gere-o novamente. Isso é necessário para manter os campos no layout e na planilha sincronizados. 

O modelo do Excel conterá todos os elementos do layout do documento de plano de orçamento, no qual a coluna **Disponível em planilha** é definida como Verdadeira. Não é possível sobrepor elementos no modelo do Excel. Por exemplo, se o layout contiver as colunas Solicitação Q1, Solicitação Q2, Solicitação Q3 e Solicitação Q4 e uma coluna com o total de solicitações representando a soma de todas as 4 colunas trimestrais, apenas as colunas trimestrais ou a coluna com o total estarão disponíveis para serem usadas no modelo do Excel. O arquivo do Excel pode atualizar a sobreposição de colunas durante a atualização, já que os dados na tabela poderiam ficar desatualizados e se tornar imprecisos.

> [!NOTE] 
> Para evitar possíveis problemas com a exibição e a edição de dados de plano de orçamento usando o Excel, o mesmo usuário deve estar conectado ao Microsoft Dynamics 365 Finance e ao Conector de Dados do Suplemento do Office do Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Adicionar um cabeçalho ao modelo de documento de plano de orçamento
Para adicionar informações de cabeçalho, selecione a linha superior no arquivo do Excel e insira linhas vazias. Clique em **Design** no **Conector de Dados** para adicionar campos de cabeçalho ao arquivo do Excel.

Na guia **Design**, clique nos campos **Adicionar** e, em seguida, selecione **BudgetPlanHeader** como a fonte de dados da entidade.

Aponte o cursor para o local desejado no arquivo do Excel. Clique em **Adicionar etiqueta** para adicionar a etiqueta do campo ao local selecionado. Selecione **Adicionar Valor** para adicionar o campo de valor ao local selecionado. Clique em **Concluído** para fechar o designer.

## <a name="select-add-valuemediabpt7png"></a>[![Selecione Adicionar Valor.](./media/bpt7.png)](./media/bpt7.png)

## <a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Adicionar uma coluna calculada à tabela do modelo de documento de plano de orçamento

Em seguida, colunas calculadas serão adicionadas ao modelo de documento de plano de orçamento gerado. Uma coluna **Total de Solicitações**, que resume as colunas Solicitação Q1: Solicitação Q4, e uma coluna **Ajuste**, que recalcula a coluna **Total de Solicitações** por um fator predefinido.

Clique em **Design** no **Conector de Dados** para adicionar colunas à tabela. Clique em **Editar** ao lado da fonte de dados **BudgetPlanWorksheet** para iniciar a adição das colunas.

[![Comece a adicionar colunas.](./media/bpt8-1024x301.png)](./media/bpt8.png) 

O grupo de campos selecionado exibe a coluna que está disponível no modelo. Clique em **Fórmula** para adicionar uma nova coluna. Nomeie a nova coluna e depois cole a fórmula no campo **Fórmula**. Clique em **Atualizar** para inserir a coluna.

[![Adicione e insira a coluna.](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Para definir a fórmula, crie a fórmula na planilha e depois copie-a na janela **Design**. Uma tabela limitada de finanças e operações geralmente será nomeada como "AXTable1". Por exemplo, para resumir as colunas Solicitação Q1 : Solicitação Q4 na planilha, a fórmula = AxTable1\[Solicitação Q1\]+AxTable1\[Solicitação Q2\]+AxTable1\[Solicitação Q3\]+AxTable1\[Solicitação Q4\].

Repita essas etapas para inserir a coluna **Ajuste**. Use a fórmula = AxTable1\[Total da solicitações\]\*$I$1 para essa coluna. Isso usará o valor na célula I1 e multiplicará os valores na coluna **Total de solicitações** para calcular os valores de ajuste.

Salve e feche o arquivo do Excel. Em **Layouts**, clique em **Modelo &gt; Carregar** para carregar o modelo do Excel salvo que será usado no plano de orçamento. 

[![Carregue o modelo do Excel.](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Feche o controle deslizante **Layouts**. No documento **Plano de orçamento**, clique em **Planilha** para exibir e editar o documento no Excel. Observe que o modelo do Excel ajustado foi usado para criar essa planilha de plano de orçamento e as colunas calculadas são atualizadas por meio de fórmulas que foram definidas nas etapas anteriores. 

[![Exiba e edite o documento no Excel.](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Dicas e truques para criar modelos de plano de orçamento
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Posso adicionar e usar fontes de dados adicionais em um modelo de plano de orçamento?

Sim, você pode usar o menu **Design** para adicionar mais entidades às mesmas ou a outras planilhas no modelo do Excel. Por exemplo, você pode adicionar as fontes de dados **BudgetPlanProposedProject** para criar e manter uma lista de projetos propostos ao trabalhar com dados de plano de orçamento no Excel. Observe que a inclusão de alto volume de fontes de dados pode ter impacto sobre o desempenho da pasta de trabalho do Excel. 

Você pode usar a opção **Filtro** no **Conector de Dados** para adicionar os filtros desejados a fontes de dados adicionais.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Posso ocultar a opção Design no Conector de Dados para outros usuários?

Sim, abra as opções **Conector de Dados** para ocultar a opção **Design** de outros usuários.

[![Abra as opções Conector de Dados.](./media/bpt13-1024x565.png)](./media/bpt13.png)

Expanda as **Opções de conector de dados** e desmarque a caixa de seleção **Habilitar design**. Isso ocultará a opção **Design** do **Conector de Dados**.

[![Oculte a opção Design do Conector de Dados.](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Posso impedir que usuários fechem acidentalmente o Conector de Dados ao trabalhar com dados?

Recomendamos o bloqueio do modelo para impedir que usuários o fechem. Para ativar o bloqueio, clique no **Conector de Dados**, no canto superior direito no qual aparece uma seta. 

[![Ative o bloqueio.](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Clique na seta para obter um menu adicional. Selecione **Bloqueio**.

### <a name="select-lockmediabpt16png"></a>[![Selecione Bloqueio.](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Posso usar outros recursos do Excel, como formatação de células, formatação condicional e gráficos com meus modelos de plano de orçamento?

Sim, a maior parte dos recursos padrão do Excel funcionará nos modelos de plano de orçamento. Recomendamos o uso da codificação por cor para que os usuários diferenciem entre colunas somente leitura e editáveis. A formatação condicional pode ser usada para destacar áreas problemáticas do orçamento. Os totais de coluna podem facilmente ser apresentados por meio de fórmulas padrão do Excel acima da tabela.

Você também pode criar e usar tabelas e gráficos dinâmicos para mais agrupamentos e visualizações de dados de orçamento. Na guia **Dados**, no grupo **Conexões**, clique em **Atualizar Tudo** e depois clique em **Propriedades da Conexão**. Clique na guia **Uso**. Em **Atualizar**, marque a caixa de seleção **Atualizar dados ao abrir o arquivo**. 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]


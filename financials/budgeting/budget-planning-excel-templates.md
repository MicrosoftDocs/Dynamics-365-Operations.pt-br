---
title: "Modelos de previsão de orçamento para O Excel"
description: "Este tópico descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 0e2eb6e7c130f03edbf60a185d397d94b5d61d7d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-templates-for-excel"></a>Modelos de previsão de orçamento para O Excel

Este tópico descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento.

Esse tópico mostra como criar modelos Excel que serão usados com planos de orçamento usando o conjunto de dados de demonstração padrão e o logon do usuário admin. Para obter mais informações sobre planejamento de orçamento, consulte visão geral [de planejamento de orçamento (budget-planning-overview-configuration.md].) Você também pode controlar orçamento que planeja [101] o tutorial () budget-plan.md para aprender princípios de configuração e o uso do módulo básico.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Gerar uma planilha com o layout de documento de plano de orçamento
Os documentos de plano de orçamento podem ser exibidos e editadas com um ou vários layouts. Cada layout pode ter um modelo de documento associada de plano de orçamento para exibir e editar os dados do plano de orçamento em uma planilha do excel. Neste tópico, um modelo de documento de plano de orçamento será gerado usando uma configuração existente do layout. Abra ** planos de orçamento listam ** (** para orçar **&gt; ** planos de orçamento **). ** ** Clique em novo para criar um novo documento de plano de orçamento. [![(bpt1]. /media/bpt11-1024x552.png)](. /media/bpt11.png) 

** Usam adicionam ** a opção de linha adicionar linhas. ** Layouts ** clique para exibir o layout de documento de plano de orçamento. 
[![(bpt2]. /media/bpt2-1024x274.png)](. /media/bpt2.png) 

Examine a configuração do layout e ajustá-la quando necessário. Ir ** modelo ** &gt; ** geram ** para criar um arquivo excel para esse layout. Depois que o modelo é gerado, vai ** modelo ** &gt; ** exibição ** para abrir ou revisar o modelo de documento de plano de orçamento. Você pode salvar o arquivo excel a sua unidade local. [![(bpt3]. /media/bpt3-1024x545.png)](. /media/bpt3.png) 

> [!NOTE] 
> O layout de documento do plano do orçamento não pode ser editado depois que um modelo De O excel associado a ele. Para alterar o layout, exclua o arquivo de modelo associado Excel e regenere-o. Isso é necessário atualizar os campos em layout e sincronizados na planilha. 

O modelo De O excel conterá todos os elementos do layout de documento de plano de orçamento, onde ** disponível na planilha ** a coluna é definida para retificar. Sobrepor elementos não são permitidos no modelo De O excel. Por exemplo, se o layout contém colunas do Q1, do Q2, solicitação de Q3, e a solicitação Q4, e uma coluna total do que representa a soma de todas as colunas 4 trimestrais, somente colunas ou trimestrais a coluna total disponíveis para ser usado no modelo De O excel. O arquivo excel pode atualizar não se sobrepuserem colunas durante atualização como os dados na tabela podem ficar expirados imprecisos e.

[![(bpt4]. /media/bpt4-1024x615.png)](. /media/bpt4.png)

> [!NOTE] 
> Para evitar problemas potenciais a exibição de dados e de plano de orçamento usando Excel editar, o mesmo usuário deve ser registrado em dynamics 365 para operações e o COM de dados manuais suplementam da Microsoft Dynamics Office.

## <a name="add-a-header-to-budget-plan-document-template"></a>Adicionar um cabeçalho no modelo de documento de plano de orçamento
Para adicionar informações de cabeçalho, selecione a linha superior em linhas vazios do arquivo e de inserção Excel. Clique ** Design ** em ** connector dados ** para adicionar campos de cabeçalho no arquivo excel.

[![(bpt5]. /media/bpt5-1024x615.png)](. /media/bpt5.png) 

** Design ** na guia, ** ** clique em adicionar ** ** campos, e BudgetPlanHeader ** ** como a fonte de dados da entidade.

[![(bpt6]. /media/bpt6-1024x615.png)](. /media/bpt6.png)

Apontam o cursor a localização desejada no arquivo excel. ** O clique em adicionar para adicioná-lo rótulo ** rótulo do campo para o local selecionado. Selecione adicionar ** o valor ** para adicionar o valor do campo para o local selecionado. Clique ** feito ** fechar o designer.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![(bpt7]. /media/bpt7.png)](. /media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Adicionar uma coluna calculada a tabela do documento de plano de orçamento
--------------------------------------------------------------

Em seguida, colunas calculadas será gerado adicionado ao modelo de documento de plano de orçamento. ** A solicitação ** coluna total, que é o Q1: Às colunas, e Q4 ** ajuste ** uma coluna que, recalcule ** o total ** a coluna por um fatora predefinido.

Clique ** Design ** em ** connector dados ** para adicionar colunas à tabela. Clique ** edição ** próximas ** BudgetPlanWorksheet ** dados de origem para começar a adicionar colunas.

[![(bpt8]. /media/bpt8-1024x301.png)](. /media/bpt8.png) 

O grupo selecionado de campos exibe as colunas disponíveis no modelo. Clique ** fórmula ** para adicionar uma nova coluna. Nomear a nova coluna e colar na fórmula ** ** fórmula no campo. Clique ** atualização ** para inserir coluna.

[![(bpt12]. /media/bpt12-1024x565.png)](. /media/bpt12.png)

> [!NOTE] 
> A fórmula para definir, criar a fórmula na planilha, e em copiar-la ** Design ** a janela. Uma dynamics 365 para tabela associada operações geralmente será chamada “AXTable1”. Por exemplo, para resumir Q1 a solicitação: Às colunas Q4 na planilha, a fórmula Q4 = o\]do Q3\]+AxTable1\[do Q2\]+AxTable1\[do Q1\]+AxTable1\[de AxTable1\[.

Repita essas etapas para inserir ** ajuste ** a coluna. Use a fórmula a solicitação =\]\*$I$1 total de AxTable1\[para essa coluna. Isso até o valor na célula I1 e multiplicará ** os valores totais a solicitação ** coluna para calcular valores de ajuste.

Salve e feche o arquivo excel. Retorne o dynamics 365 para operações, e dentro ** layouts **, clique ** carregamento &gt; de modelo ** para carregar o modelo a O Excel a serem usado para o plano de orçamento. 

[![(bpt10]. /media/bpt10-1024x352.png)](. /media/bpt10.png) 

** De layouts ** o controle deslizante. ** Plano de orçamento ** o documento, clique ** planilha ** para exibir e editar o documento Excel. Observe que o modelo foi ajustado Excel usado para criar a planilha do plano do orçamento e as colunas calculadas são atualizadas usando fórmulas definidas em etapas anteriores. 

[![(bpt11]. /media/bpt111-1024x431.png)](. /media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Derrubam e enganam criar modelos de orçamento do plano
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Eu pode adicionar e usar fontes de dados adicional para um modelo de plano de orçamento?

Sim, você pode usar ** Design ** o menu para adicionar entidades adicionais para o mesmo ou outras planilhas no modelo De O excel. Por exemplo, você pode adicionar BudgetPlanProposedProject ** ** a fonte de dados para criar o mesmo tempo e manter uma lista de projetos propostos ao trabalhar com dados do plano do Excel. Observe que inclua fontes de dados de volume alto pode afetar o desempenho de pasta trabalho do Excel. 

Você pode usar ** filtro ** a opção em ** connector de dados adiciona ** filtros desejados fontes de dados adicional.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Eu pode ocultar a opção de Design de dados no business connector para outros usuários?

Sim ** connector, ele dados ** opções ocultar ** Design ** a opção de outros usuários.

[![(bpt13]. /media/bpt13-1024x565.png)](. /media/bpt13.png)

** Expandem opções connector de dados e desmarque ** ** habilitam o design ** a caixa de seleção. Isso ocultará ** Design ** a opção de ** connector ** de dados.

[![(bpt14]. /media/bpt14-1024x592.png)](. /media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Eu pode impedir que os usuários acidentalmente fechem o COM de dados ao trabalhar com dados?

Recomendamos bloquear o modelo para prevenir os usuários do fechem. Para ativar o bloqueio, clique ** connector ** de dados, no canto superior direito de uma seta será exibido. 

[![(bpt15]. /media/bpt15-1024x285.png)](. /media/bpt15.png) 

Clique na seta para um menu adicional. Selecione bloquear ** **.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![(bpt16]. /media/bpt16-1024x614.png)](. /media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Eu pode usar outros recursos do Excel, a formatação da célula, cores, a formatação condicional, e gráficos com meus modelos de plano de orçamento?

Sim, a maioria recursos padrões Excel funcionará em modelos de plano de orçamento. Recomenda-se usar o código de cor dos usuários distingam entre colunas somente leitura e editável. Formatação condicional pode ser usado para realçar áreas do orçamento. problemáticas Os totais de coluna facilmente ser apresentados usando fórmulas padrões Excel acima da tabela.

Você também pode criar e usar tabelas dinâmicas para gráficos e agrupamentos adicionais visualizações de dados e de orçamento. ** Em dados ** guia, ** conexões ** em grupo, clique em atualizar todos ** **, e clique em propriedades ** ** de conexão. Clicar ** uso ** a guia. Sob ** ** atualização, selecione ** atualizar dados quando abrir o arquivo ** a caixa de seleção. 

[![(bpt17]. /media/bpt17-1024x614.png)](. /media/bpt17.png)



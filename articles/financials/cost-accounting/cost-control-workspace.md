---
title: "Espaço de trabalho de controle de custos"
description: "Este tópico fornece informações sobre o espaço de trabalho de controle de custos. Este espaço de trabalho é um ponto central onde os gerentes responsáveis por controlar um objeto de custo ou um conjunto de objetos de custo dentro de uma dimensão ou nas dimensões podem acessar relatórios."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspaceConfiguration, CAMCostControlWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 07787b67a84e8229cb3ce0a4434a39af3bd5a4e0
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="cost-control-overview"></a>Visão geral de controle de custos 

[!include[banner](../includes/banner.md)]

O espaço de trabalho **Controle de custos** é um ponto central onde os gerentes responsáveis por controlar um objeto de custo ou um conjunto de objetos de custo dentro de uma dimensão ou nas dimensões podem acessar relatórios. Os relatórios no espaço de trabalho são gerenciados totalmente por contadores custo, de forma que o layout e os dados que são usados para relatórios possam ser consistentes na organização inteira.

## <a name="cost-control-workspace-configuration"></a>Configuração de espaço de trabalho de controle de custo

Os contadores de custo podem definir quantas configurações de relatório eles precisarem para composição de dados ou layout desejado. Uma configuração de relatório consiste em seis seções, cada uma contribui para a seleção de composição ou layout de dados de destino.

Para configurar um espaço de trabalho de controle de custo, clique em **Contabilização de custos** \> **Configuração** \> **Configuração do espaço de trabalho de controle de custo**.

### <a name="general"></a>Geral

Na Guia Rápida **Geral**, você pode criar um layout de relatório exclusivo. O nome do relatório será um identificador exclusivo que os usuários poderão reconhecer no espaço de trabalho **Controle de custos**. Você também pode especificar se o relatório deve compartilhado ou mantido interno para os contadores de custo.

| Campo       | descrição |
|-------------|-------------|
| Nome        | Digite um nome exclusivo para o layout. |
| descrição | Insira uma descrição detalhada. |
| Publicado   | Se você definir este campo como **Sim**, um usuário que é atribuído a uma das seguintes funções visualizará o relatório no espaço de trabalho **Controle de custos** :<ul><li>Gerenciador de contabilização de custos</li><li>Contador de custos</li><li>Contador de custos</li><li>Controlador do objeto de custo</li></ul>Se você definir este campo como **Não**, somente os usuários que são atribuídos a uma das seguintes funções visualizarão o relatório no espaço de trabalho **Controle de custos** :<ul><li>Gerenciador de contabilização de custos</li><li>Contador de custos</li><li>Contador de custos</li></ul> |

### <a name="data-filtering"></a>Filtragem de dados

Na Guia Rápida **Filtragem de dados**, você define a base de dados do relatório. Os usuários deste relatório verão os valores no relatório depois que os dados de origem forem processados.

| Campo                                                             | descrição |
|-------------------------------------------------------------------|-------------|
| Razão de contabilização de custos                                            | A **Razão da contabilização de custos** na qual o relatório está baseado. O valor é obtido do campo **Unidade de controle de custos**. |
| Unidade de controle de custo                                                 | O valor que você selecionar determinará o razão de contabilização de custos e os objetos de custos no qual este relatório está baseado. |
| Hierarquia da dimensão estatística, hierarquia da dimensão do elemento de custo | Um registro de configuração do espaço trabalho **Controle de custos** pode relatar valores monetários ou não monetários, mas não no mesmo layout. Selecione um valor no campo **Hierarquia da dimensão de elemento de custo** para relatar valores monetários. Selecione um valor no campo **Hierarquia da dimensão estatística** para relatar valores não monetários. O registro da hierarquia da dimensão selecionada determina a estrutura de relatório e os níveis agregação.<blockquote>[!NOTE]<br>Para exibir os valores monetários e não monetários lado-a-lado, você pode exportar dados para o Microsoft Excel para o pacote de conteúdo do Microsoft Power BI.</blockquote> |
| Hierarquia da dimensão de objeto de custo                                   | Selecione a hierarquia de dimensões da dimensão do objeto de custo que se ajusta ao objetivo do relatório que você está definindo. |
| Versão original do orçamento                                           | Selecione a ID da versão de orçamento que atua como o orçamento original no contexto deste relatório. |
| Versão revisada do orçamento                                            | Selecione a ID da versão de orçamento que atua como o orçamento revisado no contexto deste relatório. |

### <a name="assign-calculation-records"></a>Atribuir registros de cálculo

O cálculo de custos indiretos executa várias etapas de cálculo nos dados de origem, como classificação de comportamento de custo, distribuição de custo e alocação de custos. Vários cálculos de custos indiretos podem ser feitos para o mesmo período fiscal, no caso de dados de origem ausentes serem descobertos ou as regras tiverem que ser atualizadas. Cada cálculo de custos indiretos é salvo com uma ID exclusiva. O contador de custo pode selecionar uma ID de cálculo de custo indireto específico. Os usuários do relatório, como gerentes verão, os resultados de cálculos de custos indiretos no espaço de trabalho **Controle de custos**.

| Campo                  | descrição |
|------------------------|-------------|
| Período do calendário fiscal | Selecione o período do calendário fiscal para o qual atribuir uma ID de cálculo de custos indiretos.<blockquote>[!NOTE]<br>Os períodos fiscais listados no campo do calendário fiscal associados ao motivo da contabilização de custo.</blockquote> |
| Versão real         | Selecione a ID de cálculo de custo indireto apropriada. |
| Versão de orçamento         | Selecione a ID de cálculo de custo indireto apropriada. |
| Versão do orçamento revisado | Selecione a ID de cálculo de custo indireto apropriada. |

### <a name="fiscal-periods-per-column"></a>Períodos fiscais por coluna

Na Guia Rápida **Períodos fiscais por coluna**, o contador de custo decide qual período fiscal deve ser mostrado no layout do relatório.

Os valores nas colunas selecionadas serão multiplicados pelos valores selecionados na Guia Rápida **Períodos fiscais por coluna**.

| Campo                | descrição |
|----------------------|-------------|
| Período atual       | O saldo do período fiscal atual será exibido.<blockquote>[!NOTE]<br>Por padrão, o período atual será determinado pela data da sessão. No espaço de trabalho **Controle de custos**, um período fiscal específico pode ser selecionado. O valor selecionado representa o período atual.</blockquote> |
| Período anterior      | O saldo do período fiscal anterior será exibido. Esta é a fórmula usada:<br>Período fiscal atual – 1<blockquote>[!NOTE]<br>Por padrão, o período anterior será obtido da data da sessão. No espaço de trabalho **Controle de custos**, um período fiscal específico pode ser selecionado como o período atual. **Período anterior** será recalculado adequadamente.</blockquote> |
| Ano até a data         | O valor Desde o início do ano é mostrado. Esta é a fórmula usada:<br>YearToDate (período fiscal atual)<blockquote>[!NOTE]<br>Por padrão, o período atual será determinado pela data da sessão. No espaço de trabalho **Controle de custos**, um período fiscal específico pode ser selecionado. O valor selecionado representa o período atual, e o valor **Desde o início do ano** será atualizado adequadamente.</blockquote> |
| Média desde o início do ano | A médio de Desde o início do ano é mostrada. Esta é a fórmula usada:<br>(YearToDate [período fiscal atual]) ÷ (Contagem [período fiscal atual])<p><strong>Exemplo</strong></p><ul><li>**Membro estatístico de dimensão:** Funcionários em tempo integral</li><li>**Data atual:** 21-03-2017</li><li>**Período:** Período fiscal 1, Período fiscal 2, Período fiscal 3</li><li>**Magnitude:** 10, 10, 12</li></ul>Nesse caso, **Média Desde o início do ano** = (10 + 10 + 12) = 3 ÷ 10.67<p>O valor **Média desde o início do ano** pode ser calculado para membros da dimensão do elemento de custo previsto e membros estatísticos de dimensão.</p><blockquote>[!NOTE]<br>Por padrão, o período atual será determinado pela data da sessão. No espaço de trabalho **Controle de custos**, um período fiscal específico pode ser selecionado. O valor selecionado representa o período atual, e os valores **Desde o início do ano** e **Média desde o início do ano** serão atualizados adequadamente.</blockquote> |

### <a name="columns-to-display-for-costs"></a>Colunas a serem exibidas para custos

Na Guia Rápida **Colunas para exibir custos**, o contador de custo decide quais colunas deverá conter o layout de relatórios. Há três categorias: Custo fixo, custo variável e custo não classificado.

| Campo                 | descrição |
|-----------------------|-------------|
| Custo fixo            | Esse tipo de coluna mostra os custos fixos, com base na ID de cálculo de custos indiretos selecionada.<blockquote>[!NOTE]<br>Esse tipo de coluna só mostrará um saldo quando uma ID de cálculo de custos indiretos for selecionada para o período fiscal.</blockquote> |
| Custo variável         | Esse tipo de coluna mostra o custo variável, com base na ID de cálculo de custos indiretos selecionada.<blockquote>[!NOTE]<br>Esse tipo de coluna só mostrará um saldo quando uma ID de cálculo de custos indiretos for selecionada para o período fiscal.</blockquote> |
| Custo fixo + variável | Esse tipo de coluna mostra o custo fixo e o custo variável, com base na ID de cálculo de custos indiretos selecionada.<blockquote>[!NOTE]<br>Esse tipo de coluna só mostrará um saldo quando uma ID de cálculo de custos indiretos for selecionada para o período fiscal.</blockquote> |
| Custo total            | Esse tipo de coluna mostra o custo total (custo não classificado, custo fixo e custo variável).<blockquote>[!NOTE]<br>O tipo de coluna mostrará o saldo sempre.</blockquote> |
| Custo não classificado     | Esse tipo de coluna mostra o custo não classificado.<blockquote>[!NOTE]<br>Esta coluna pode ser usada para validar se todos os custos foram classificados corretamente por cálculo de custos indiretos ou se as regras de custo de comportamento devem ser ajustadas.</blockquote> |

### <a name="columns-to-display-for-budgeted-costs"></a>Colunas a serem exibidas para custos orçados

Na Guia Rápida **Colunas a serem exibidas para custos orçados**, o contador decide quais colunas devem ser mostradas para as versões do orçamento selecionadas. As seleções individuais podem ser feitas para o o orçamento original e revisado.

> [!NOTE]
> Como os seguintes campos se comportam da mesma maneira para orçamento original e revisado, eles serão explicados somente uma vez.

| Campo                     | descrição |
|---------------------------|-------------|
| Orçamento                    | Os saldos de orçamento serão mostrados por colunas selecionadas.<blockquote>[!NOTE]<br>Os saldos serão baseados nas versões de orçamento selecionadas na Guia Rápida **Filtragem de dados**.</blockquote> |
| Variação do orçamento           | Calcule e mostre a diferença entre o orçamento e o real. Esta é a fórmula usada:<br>Saldo de orçamento – saldo real |
| Variação do orçamento em %      | Calcule e mostre a diferença em percentual entre o orçamento e o real. Esta é a fórmula usada:<br>(Saldo de orçamento – saldo real) ÷ saldo de orçamento |
| Limite de período de variação | Defina um limite para a variação no valor monetário do período atual. Se o limite for excedido, a linha estará realçada em vermelho no espaço de trabalho **Controle de custos**.<blockquote>[!NOTE]<br>Este campo só se aplica para elementos de custo que representam despesas.</blockquote> |
| Limite de ano de variação   | Defina um limite para a variação no valor monetário do ano. Se o limite for excedido, a linha estará realçada em vermelho no espaço de trabalho **Controle de custos**. |
| Limite de variação %      | Defina um limite para a variação em porcentagem. Se o limite for excedido, a linha estará realçada em vermelho no espaço de trabalho **Controle de custos**.<blockquote>[!NOTE]<br>O mesmo limite de percentual se aplica ao período atual e ao ano.</blockquote> |

## <a name="cost-control-workspace"></a>Espaço de trabalho de controle de custos

O espaço trabalho **Controle de custos** é criado como um relatório da Web. Portanto, todos os gerentes responsáveis por um objeto de custo podem ter acesso como descrito em [Definir direitos de acesso para controladores do objeto de custo](access-rights-cost-object-controller.md).

A lista dos relatórios disponíveis para usuários, como gerentes, é controlada pela configuração da opção **Publicado** na página **Configurações do espaço de trabalho de controle de custo**.

![Um relatório que os usuários podem consultar no espaço de trabalho de Controle de custo](./media/report-cost-control.png)

O gerente poderá selecionar o período do calendário fiscal para exibir. A data da sessão é usada para determinar o período atual padrão.

Os valores do período do calendário fiscal são determinados por nome do relatório e o calendário fiscal selecionado para o razão da contabilização de custo é associado ao nome do relatório na página **Configurações do espaço de trabalho de controle de custo**.

Na hierarquia de dimensão de objeto de custo, os usuários podem marcar o nível de agregação no qual os saldos devem ser mostrados. Ativando a segurança em nível de acesso, você controla as permissões, para que os usuários possam selecionar somente os níveis de hierarquia aos quais têm acesso. Portanto, eles podem ver apenas os saldos agregados aos quais eles têm acesso.

### <a name="add-or-remove-columns"></a>Adicionar ou remover colunas

Os usuários podem personalizar as colunas em um relatório de acordo os requisitos.

### <a name="view-details"></a>Exibir detalhes

Os usuários podem detalhar os saldos mostrados no espaço de trabalho. Se os usuários selecionarem um nó da hierarquia de dimensão do elemento, e clicar em **Exibir detalhes**, a caixa de diálogo **Detalhes do elemento de custo** mostrará informações detalhadas do nó.

A grade mostra cada elemento de custo associado ao nó da hierarquia de dimensão do elemento de custo e seus valores. As colunas que aparecem na grade corresponde às configurações do espaço de trabalho.

Dois gráficos mostram um resumo do custo real versus orçamento e variação de orçamento por período.

![Os gráficos que mostram um resumo do custo real versus orçamento e variação de orçamento por período.](./media/cost-element-details-operations.png)

Os usuários podem clicar em **Entradas de custo** para fazer busca detalhada na entrada, conforme necessário.

![Entradas de custo](./media/cost-entries.png)

Por exemplo, aluguel é uma despesa que é distribuída para centros de custos. Um usuário que quer entender o custo de aluguel que seu centro custo de custos deve ter pode fazer uma busca detalhada para saber como aluguel foi calculado.

Se os usuários clicarem em **Base de alocação** na página **Entradas de custo**, será exibida uma caixa de diálogo. Os usuários podem atribuir a base de alocação à regra e exibir medições estatísticas correspondentes registrados para o período.

No exemplo a seguir, a base de alocação é do tipo **Base de alocação da fórmula** e a fórmula é mostrada. Os fatores que definem a fórmula são listados. Além disso, uma grade mostra o cálculo que é feito por objeto de custo.

![Cálculos por objeto de custo](./media/cost-entries-allocation-base.png)

Consulte também 

[Definir direitos de acesso para controladores do objeto de custo](access-rights-cost-object-controller.md)




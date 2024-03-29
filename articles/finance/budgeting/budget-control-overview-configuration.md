---
title: Visão geral de controle de orçamento
description: Este artigo apresenta um recurso de controle de orçamento e oferece informações para ajudar você a configurar o controle de orçamento para otimizar o gerenciamento de recursos financeiros da organização.
author: panolte
ms.date: 03/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27eb31919937e7f43a785616b547e3d6952eaaf2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898288"
---
# <a name="budget-control-overview"></a>Visão geral de controle de orçamento

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo apresenta um recurso de controle de orçamento e oferece informações para ajudar você a configurar o controle de orçamento para otimizar o gerenciamento de recursos financeiros da organização.

O controle de orçamento oferece suporte ao gerenciamento dos recursos financeiros de uma organização por meio do plano de contas, de fluxos de trabalho, grupos de usuários, documentos de origem e diários, cálculo configurável de fundos disponíveis, ciclos orçamentários e limites. Quando os controles estão em vigor, uma organização pode planejar, medir, gerenciar e prever os recursos financeiros ao longo do ano fiscal. 

Depois que os orçamentos foram aprovados no sistema, você pode usar planos de orçamento para gerar entradas de registro de orçamento a fim de registrar o orçamento de despesas de uma organização. Como alternativa, você pode criar ou importar entradas de registro de orçamento de um programa de terceiros em vez de usar a funcionalidade de planejamento de orçamento. 

As despesas podem ser registradas usando as contas e dimensões financeiras. Você pode configurar o controle de despesas totais para atender as diretivas e os requisitos da organização para agrupar diversas combinações de dimensões financeiras e contas principais. 

O gráfico a seguir mostra o local do controle de orçamento em fases de um ciclo orçamentário típico.

[![Ciclo de orçamento típico.](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

Você pode configurar o controle de orçamento de acordo com diversos fatores:

- **Dimensões financeiras** — Quais dimensões financeiras precisam ser usadas em orçamentos de relatório e valores reais, e quais dimensões financeiras são necessárias para controlar os orçamentos? Há combinações de dimensões ou contas principais que exijam atenção específica? Por exemplo, há um requisito para controlar o orçamento para valores reais por centro de custo e programa? Despesas de viagem exigem atenção especial?
- **Hora** - Que intervalo de tempo (período fiscal, período fiscal até a data etc.) será usado para avaliar fundos de orçamento disponíveis?
- **Documentos de origem** – Que documentos de origem precisam ser avaliados para controle de orçamento? O documento deve ser avaliado por linha ou por documento?
- **Cálculo de fundos disponíveis** - Documentos como requisições de compra (pré-ônus) e ordens de compra (ônus) devem ser considerados no cálculo de fundos disponíveis? Os documentos que têm um status de rascunho devem ser considerados no cálculo?
- **Permissão de substituição** - Quem tem permissão para exceder o orçamento disponível?

O controle de orçamento é totalmente integrado ao aplicativo. Consequentemente, você pode classificar o orçamento disponível para compras planejadas e compras reais. Consultas de orçamento e relatórios estão disponíveis. Portanto, os usuários podem avaliar o orçamento por meio do ciclo de orçamento, e podem fazer quaisquer ajustes que são necessários, na forma de revisões de orçamento ou transferências. Um gerente de orçamento também pode exportar o orçamento e os valores reais para o Microsoft Excel para fazer análises e previsões mais precisas, conforme necessário.

## <a name="configuring-budget-control"></a>Configuração do controle de orçamento

### <a name="budget-cycle-time-span"></a>Período de tempo do ciclo orçamentário

Depois que o orçamento básico for configurado, você pode definir o tempo ou os períodos inicial e final para orçamento e controle de orçamento na página **Período de tempo do ciclo orçamentário**. Os ciclos orçamentários geralmente correspondem aos calendários fiscais, mas podem medir anos fiscais.

As próximas etapas na configuração são concluídas nas guias abertas na página **Configuração do controle de orçamento**.

### <a name="define-parameters"></a>Definir parâmetros

Com base nas dimensões financeiras habilitadas para o orçamento, você pode usar todas ou um subconjunto das dimensões financeiras para controle de orçamento. 

Além disso, você pode especificar o intervalo de tempo padrão (por exemplo, **Ano fiscal**, **Ano fiscal até a data**, **Período fiscal** ou **Trimestral**) que o controle de orçamento será realizado para o período de tempo do orçamento relacionado. Você também pode especificar um gerente de orçamento padrão e o limite que será usado para notificar os usuários quando o limite foi alcançado. Os valores nesses campos serão usados como os valores padrão em qualquer nova regra de controle de orçamento ou grupo orçamentário que é criado. No entanto, os valores padrão podem ser alterados para grupos individuais ou regras. 

É importante saber como os orçamentos são criados e registrados no registro de orçamento ajudam a determinar o período de tempo que é selecionado quando os fundos de orçamento disponíveis são avaliados. Se um valor anualizado para uma combinação de valores de dimensão for desenvolvido e usado, talvez faça sentido uma abordagem do ano fiscal ou do ano fiscal até a data. Entretanto, se uma organização cria o orçamento por período fiscal, ou aloca em períodos fiscais e deseja um controle mais detalhado, talvez queira considerar o período fiscal até a data ou intervalos de tempo trimestrais. 

Além disso, a cultura de uma organização em sua relação com o orçamento e o controle orçamentário influencia na definição da configuração.

### <a name="over-budget-permissions"></a>Permissões de orçamento excedido

Em seguida, na guia **Permissões de orçamento excedido**, você pode especificar grupos de usuários. Você também pode especificar se os usuários membros de um grupo têm permissão exceder o orçamento. Você pode impedir que os usuários excedam o orçamento após o limite de orçamento definido na página **Parâmetros de orçamento**, ou pode impedir que excedam o orçamento em qualquer valor, independentemente do limite. Com base no nível de proatividade com que uma organização gerencia seus gastos, essas permissões podem ajudá-la a gerenciar seus recursos financeiros. 

### <a name="budget-funds-available"></a>Fundos de orçamentos disponíveis

Em seguida, na guia **Fundos disponíveis de orçamento**, você pode definir a fórmula usada para calcular de orçamento de fundos disponíveis. Com base no nível de conservadorismo com que uma organização gerencia os recursos financeiros, ou considerando as regulamentações ou os requisitos do setor, o cálculo pode incluir documentos de rascunho ou não lançados. 

> [!NOTE]
> Se esse cálculo for alterado durante um ciclo orçamentário, os documentos que porventura tenham passado em verificações de controle de orçamento e sido lançados ou concluídos permanecerão nesse estado. Um recurso chamado **Rastrear valores apenas de fundos de orçamento disponíveis para cálculo** permite alterar quais dados são rastreados nas tabelas BudgetSourceTracking. Quando o recurso está ativado, os valores são armazenados apenas se forem selecionados para serem usados no cálculo de fundos de orçamento disponíveis. Para obter mais informações, consulte [Fundos de orçamentos disponíveis](budget-funds-available.md).

### <a name="documents-and-journals"></a>Documentos e diários

Na guia **Documentos e diários**, você pode selecionar quais documentos de origem e diários estarão sujeitos a verificações de controle de orçamento, e se a verificação ocorrerá na entrada de linha ou no documento inteiro. Além disso, o novo recurso **Aprimoramento na filtragem de documentos do controle de orçamento** disponível no Microsoft Dynamics 365 Finance versão 10.0.27 fornece uma opção de filtro baseada em consulta para cada documento incluído no controle de orçamento. Portanto, você pode especificar quais documentos do controle de orçamento passam por verificação de orçamento. Dessa forma, o recurso permite que apenas um subconjunto de um tipo de documento passe por verificação de orçamento. Por exemplo, você pode verificar somente as ordens de compra em que o campo **Grupo** está definido como **01**. Uma nova coluna adicionada à guia **Documentos e diários** indica se uma consulta está definida para o tipo de documento selecionado. Além disso, dois novos botões adicionados à barra de ferramentas acima da grade do documento permitem que você adicione, edite ou exclua a filtragem. 

Você deve coincidir os documentos de origem selecionados com as caixas de seleção para saldos incluídos no cálculo de fundos de orçamento disponíveis. Por exemplo, se você selecionar **Reservas de orçamento para ônus**, selecione a opção **Ordens de compra**. Quando uma verificação de orçamento é executada para os valores e as contas em uma linha de compra, a categoria de controle de orçamento que é atribuída à reserva é **Ônus**. Quando uma verificação de orçamento é executada para os valores e as contas em uma requisição de compra, a categoria de controle de orçamento que é atribuída à reserva é **Pré-ônus**. 

Se **Reservas de orçamento para ônus** e/ou **Reservas de orçamento para pré-ônus** estiver incluído no cálculo disponível de fundos de orçamento e precisar ser refletido em lançamentos na contabilidade, as seleções no grupo **Contabilidade de obrigações** deverão ser marcadas na página **Parâmetros de contabilidade**.

### <a name="assign-budget-models"></a>Atribuir modelos de orçamento

Em seguida, na guia **Atribuir modelos de orçamento**, você atribui modelos de orçamento aos períodos de tempo do ciclo de orçamento a serem incluídos no controle de orçamento.

### <a name="define-budget-control-rules"></a>Definir regras de controle de orçamento

Em seguida, na guia **Definir regras de controle de orçamento**, você deve criar regras específicas com base em dimensões financeiras habilitadas pelo controle de orçamento. Por exemplo, se houver um foco nas despesas ou no intervalo de despesas para um departamento, você pode usar as configurações nesta guia para definir e avaliar essas despesas. Você pode definir limites diferentes para cada regra de controle de orçamento. 

> [!Important]
> O controle de orçamento será habilitado para conta principal para tipos de **Lucro e perda**, **Despesa**, **Receita, balanço, passivo, capital próprio** ou **Ativo**. Se a guia **Definir regras de controle de orçamento** contém uma regra com critérios vazios, o controle de orçamento é habilitado para **todas** as combinações de dimensões financeiras que incluem contas desses tipos principais. Portanto, certifique-se de que você criou uma regra de controle de orçamento que define as variações das combinações de dimensão financeira onde é importante que o controle de orçamento seja devolvido.

### <a name="select-main-accounts"></a>Selecionar contas principais

Se **Conta principal** não estiver selecionada como uma dimensão de controles de orçamento na página **Definir parâmetros** , mas as despesas específicas são gerenciadas, você pode selecionar essas despesas na guia **Selecionar contas principais**. Se a **Conta principal** for selecionada como uma dimensão de controles de orçamento, nenhuma entrada é necessária.

### <a name="define-budget-groups"></a>Definir os grupos orçamentários

Em seguida, na guia **Definir grupos de orçamento**, você pode, opcionalmente, definir combinações exclusivas de dimensões financeiras, em que os recursos de orçamento são agrupados para verificação secundária do orçamento. Você pode criar um único registro que inclui a organização inteira, ou definir vários grupos para representar departamentos ou centros de custo separados.

### <a name="define-message-levels"></a>Definir níveis de mensagem

Se as mensagens de aviso do controle de orçamento são suprimidas para quaisquer grupos de usuários, você pode especificar esses grupos na página **Definir níveis de mensagem**. Os membros do grupo de usuários continuarão a receber mensagens de erro quando os fundos de orçamento disponíveis forem excedidos, com base nas permissões de orçamento excedido.

### <a name="activate-budget-control"></a>Ativar controle de orçamento

Depois que o controle de orçamento foi configurado, você poderá gerencia-lo e ativá-lo na guia **Ativar controle de orçamento**. A versão de rascunho se tornará efetiva.

> [!Important]
> Quando o controle de orçamento está ativado e ativo, e as transações são lançadas, ele não deve ser desativado na metade do ano. Quando o controle de orçamento é desativado, as atividades não são registradas para fins de controle de orçamento, e as verificações de orçamento não são mais executadas. Consequentemente, os documentos que foram lançados corretamente não podem refletir os saldos ou valores de alívio em consultas e relatórios relacionados ao controle de orçamento. Eles incluem estatísticas de controle de orçamento para qualquer downstream ou documentos e diários de ajuste. 

Além disso, lembre-se de que as transações que foram lançadas antes de o controle de orçamento a ser ativado, incluindo entradas de registo de orçamento, não são consideradas no controle de orçamento. Portanto, é recomendável ativar o controle de orçamento somente no início do novo ciclo orçamentário. Verifique se as entradas de Registro de orçamento contendo os saldos do orçamento inicial para o controle de orçamento obtêm os saldos do orçamento atualizados somente após a ativação do controle de orçamento. Qualquer documento aberto (por exemplo, uma ordem de compra) será verificado para fundos de orçamento disponíveis e obterá uma reserva de orçamento para controle de orçamento, quando o usuário disparar manualmente a verificação de controle de orçamento no documento.

## <a name="using-budget-control"></a>Uso do controle de orçamento
Depois que o controle de orçamento é ativado, você recebe o aviso do controle de orçamento e mensagens de erro em documentos e diários configurados para controle de orçamento. Lembre-se, você pode configurar o controle de orçamento de forma que os usuários sejam advertidos quando excedam os fundos de orçamento, mas ainda possam continuar a confirmar ou lançar transações. Você pode ver os detalhes de verificações de orçamento ou falhas na página **Erros e avisos de controle de orçamento**.

Nesta página, os usuários podem entrar na página **Estatísticas de controle de orçamento por período** para ver os detalhes de disponibilidade de orçamento e reservas para uma combinação de dimensão de controle de orçamento selecionado. Os usuários podem também entrar na página **Estatística de controle de orçamento** exibir a disponibilidade de orçamento para todas as combinações de dimensões financeiras que são usadas no controle de orçamento. 

Se o controle de orçamento for ligado nas ordens de compra, o gerente do orçamento pode usar a área de trabalho **Orçamentos razão e previsões** a revisar a fila de todas as ordens de compra não confirmadas que foram verificadas com avisos de orçamento e erros. Se o gerente de orçamento tiver permissões de orçamento configuradas, as ordens de compra poderão ser confirmadas diretamente no espaço de trabalho.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

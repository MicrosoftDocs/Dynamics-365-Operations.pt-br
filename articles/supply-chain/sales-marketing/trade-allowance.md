---
title: Gerenciamento de bonificação comercial
description: Este artigo descreve o gerenciamento de bonificação comercial do Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCRBrokerClaims, MCRBrokerWriteOffReasonPrompt, MCRRoyaltyVendTable, MCRRoyaltyVendTrans, PdsCustRebateGroup, PdsRebateAgreement, TAMCopyTradePromotions, TAMDeduction, TAMDeductionCreate, TAMDeductionDenyReason, TAMDeductionParmDeny, TAMDeductionParmMassUpdate, TAMDeductionParmMatch, TAMDeductionParmSplit, TAMDeductionParmWriteOff, TAMDeductionType, TAMDeductionWriteOffReason, TAMFundManagement, TAMFundUsage, TAMListPage, TAMMarketingObjective, TAMMerchEventType, TAMOneTimePromotion, TAMPromoCompareGraph, TAMPromoStatistic, TAMPromotionAnalysisSummary, TAMPromotionParameters, TAMPromotionPeriod, TAMTemplateListPage, TAMTradePromotionAnalysis, TAMTradePromotions, TAMWhatIfPromotionAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2018-01-31
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: d6592d21c184aea19be30cece7007854302ddc17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901782"
---
# <a name="trade-allowance-management"></a>Gerenciamento de bonificação comercial

[!include [banner](../includes/banner.md)]

O gerenciamento de bonificação comercial ajuda as empresas a gerenciar programas de promoção de vendas que oferecem recompensas monetárias de "pagamento por desempenho" aos clientes que atingem metas de volume e comportamentais. As capacidades do recurso foram desenvolvidas para empresas que se concentram em processos abrangentes de promoção para lucro, desde orçamento e alocação de fundos de promoção até configuração de contrato de bonificação, criação e processamento de solicitações, processamento de pagamentos e análise de eficácia de promoção.


Este artigo fornecerá uma visão geral ampla do recurso de gerenciamento de bonificação e permitirá que você se familiarize com o conjunto típico de tarefas incluídas no gerenciamento de um programa de promoção de vendas. Espera-se que vários tipos de usuários com responsabilidades operacionais e de tomada de decisão usem essa funcionalidade para atingir seus respectivos objetivos:

- Alocação de fundos discricionários para as contas selecionadas e configuração de contratos de bonificação comercial para promoções, com base em reembolso de despesas e pagamentos únicos de valor total (para um serviço acordado)
- Execução dos contratos de promoção negociados por meio de vendas contínuas e geração de solicitações de reembolso de despesas
- Calcular, aprovar e processar as solicitações geradas e direcioná-las para Contas a receber (A/R) como deduções para liquidação de pagamentos
- Conciliar o pagamento curto do cliente com a dedução devida
- Acompanhamento do uso do fundo promocional e avaliação da rentabilidade e eficácia do programa

## <a name="audience-and-purpose"></a>Público-alvo e finalidade

As informações deste documento são direcionadas para tomadores de decisão de negócios das empresas, em posições como gerente da compra, diretor financeiro (CFO) e gerente de contabilidade que têm as seguintes responsabilidades:

- Orçamentos de alto nível e alocação de fundos
- Planejamento e análise de promoções de vendas
- Gerenciamento da equipe que processa solicitações de reembolso de despesas, executa pagamentos com base em eventos de merchandising e liquida pagamentos curtos e deduções

As pessoas nestas funções estão procurando maneiras de atingir estas metas:

- Usar melhor fundos promocionais de marketing.
- Acomodar de forma flexível diferentes tipos de programas de promoção e bonificações.
- Reduzir a carga e erros administrativos associados ao monitoramento de desempenho da promoção e às solicitações de processamento.
- Aumentar as previsões de fluxo de caixa acumulando para futuro passivo.
- Ter uma base quantificada para negociações atuais e futuras com os clientes sobre promoções.

## <a name="promotional-fund-and-trade-allowance-agreement"></a>Fundo promocional e contrato de bonificação comercial

Um contrato de bonificação comercial é um programa de incentivo no qual recompensas monetárias de pagamento por desempenho são oferecidas a clientes que atingem metas específicas de volume e/ou comportamentais. Fundos promocionais são despesas orçadas. Dessa forma, as campanhas promocionais podem ser capturadas.

### <a name="promotional-fund"></a>Fundo promocional

Os fundos alocados para contratos de bonificação comercial são registrados na página **Fundos**. Para abrir a página **Fundos**, selecione **Vendas e marketing** \> **Incentivos comerciais** \> **Fundos** \> **Fundos**.

![Página de fundos.](./media/trade-allowance-management-funds-page.png "Página de fundos")

Na página **Fundos**, você pode exibir os detalhes de fundos promocionais.

A Guia Rápida **Geral** mostra o período para o qual o fundo é válido e seu valor orçado. Para que o fundo seja atribuído ao contrato de promoção, o campo **Status** deve ter um valor de **Aprovado**.

A Guia Rápida **Clientes** mostra a hierarquia do cliente. Para selecionar os clientes aos quais o fundo se destina, arraste-os para que fiquem em **Financiar clientes**. A Guia Rápida também mostra como o valor total do fundo é distribuído.

A Guia Rápida **Itens** mostra os itens incluídos na promoção.

### <a name="trade-allowance-agreement"></a>Contrato de bonificação comercial

Após a definição do fundo, a próxima etapa no planejamento da promoção é registrar contratos de promoção (que são conhecidos como contratos de bonificação comercial), alocar fundos e definir metas de desempenho para cada evento de merchandising.

Os contratos de bonificação comercial são registrados na página **Contratos de bonificação comercial**. Para abrir a página **Contratos de bonificação comercial**, selecione **Vendas e marketing** \> **Incentivos comerciais** \> **Contratos de bonificação comercial**.

![Página de contratos de bonificação comercial.](./media/trade-allowance-management-agreements-page.png "Página de contratos de bonificação comercial")

#### <a name="header"></a>Cabeçalho

Selecione **Cabeçalho** para alternar para a exibição de cabeçalho.

Na Guia Rápida **Geral**, os campos **Solicitar para** e **Solicitar de** definem o período em que o contrato é válido. Um status de aprovação de **Aprovado internamente** para o contrato indica que este ainda não é válido e não pode ser aplicado durante o processamento de ordens de vendas.

A seção **Análise** da Guia Rápida **Geral** contém campos importantes que definem as quantidades e custos que são usados para avaliação de promoção:

- O campo **Unidades base** especifica a quantidade de produtos que devem ser vendidos para os clientes selecionados antes que a promoção seja aplicada.
- O valor **Quantidade de remessa calculada** é calculado com base no valor **Percentual de aumento**, que é um aumento de meta planejado para essa promoção.
- O campo **Custo de bonificação comercial** é calculado com base nas várias quantidades de eventos no contrato de bonificação comercial.

Na Guia Rápida **Clientes**, na lista à esquerda, você pode selecionar e exibir grupos de clientes, que são configurados como hierarquias predefinidas. Você pode então selecionar toda a hierarquia ou contas específicas como metas para o contrato de bonificação.

Na Guia Rápida **Itens**, como na Guia Rápida **Itens** da página **Fundos**, produtos são adicionados ao contrato para associar suas vendas com a bonificação que foi acordada.

Na Guia Rápida **Fundos**, você pode exibir os fundos de promoção associados a este contrato. Você também exibir a alocação de custos de evento do contrato. Uma alocação de custo de evento de 100% significa que essa promoção será financiada exclusivamente por um fundo. Como alternativa, um contrato de promoção pode recorrer a vários fundos e pode usar alocação percentual igual ou diferencial.

#### <a name="lines"></a>Linhas

Em seguida, selecione **Linhas** para alternar para a exibição de linhas.

A guia **Eventos de merchandising** mostra os tipos de eventos cobertos por um contrato. Existem três tipos: reembolso de despesas, quantia total e desconto em fatura.

Quando você seleciona o evento de merchandising e, em seguida, seleciona a guia **Valores**, os detalhes do evento são encontrados.

![Linhas de contrato de bonificação comercial.](./media/trade-allowance-management-agreements-lines.png "Linhas de contrato de bonificação comercial")

Na seção **Linhas de bonificação comercial**, você especifica as faixas de quantidade ou valor que o cliente deve atingir para que as definições obtenham as recompensas.

No caso de um evento de merchandising do tipo **Reembolso de despesas**, a seção superior, a guia **Valores** define as regras em que o reembolso de despesas será aplicado, gerado e pago. Por exemplo, as regras podem especificar as seguintes condições para a solicitação de reembolso de despesas:

- É baseado na data de criação do pedido de venda (o valor **Tipo de data de cálculo** é **Criado**).
- É calculado com base no valor da linha do pedido de vendas antes dos descontos, não no valor líquido, que inclui descontos (o valor **Extraído de** é **Bruto**).
- É baseado no volume dos produtos vendidos, não no valor (o valor **Tipo quebra de linha de reembolso** é **Quantidade**).
- É calculado por período de um mês (o valor **Acumular vendas por** é **Mês**). 
- É liquidado como dedução, não pelo uso de A/P (o valor **Tipo de pagamento** é **Deduções do cliente**).

No caso de um evento de merchandising do tipo **Quantia total**, a guia **Valores** mostra a quantidade que será paga ao cliente na forma de uma dedução quando o cliente atingir um desempenho específico. Um status de aprovação de **Abrir** indica que a quantia total ainda não foi paga.

Para aplicar o contrato a pedidos de vendas que atendam às condições do contrato, o status do contrato deve ser **Confirmado**. 

## <a name="perform-sales-under-the-planned-merchandising-event-and-generate-bill-back-claims"></a>Realizar vendas no evento de merchandising planejado e gerar solicitações de reembolso de despesas

Ao criar um pedido de vendas que possui linhas que atendem aos requisitos do contrato, você pode exibir as informações relacionadas na página **Ordem de venda** selecionando **Linha da ordem de venda** \> **Exibir** \> **Detalhes de preço**.

Na página **Detalhes de preço**, na Guia Rápida **Descontos**, o auxiliar de vendas pode ver um reembolso de despesas do contrato de bonificação comercial válido (a ID do programa de descontos é mostrada) e o valor total aplicado à linha. Esse valor também é mostrado no campo **Valor de reembolso** na seção **Estimativa de margem** da página **Detalhes de preço**.

Quando a fatura de venda é lançada, uma solicitação de reembolso de despesas correspondente é gerada para cada linha da fatura.

> [!NOTE]
> Para ver a página **Detalhes de preço**, na página **Parâmetros de contas a receber**, na guia **Preços**, marque a caixa de seleção **Ativar detalhes de preço**. I

## <a name="process-claims-and-pass-them-as-deductions-to-ar"></a>Processar solicitações e passá-las como deduções para A/R

As próximas etapas do processo de tratamento de reembolso de despesas são revisar, calcular e aprovar solicitações e convertê-las em deduções.

A bancada de reembolso de despesas é onde o proprietário do contrato de promoção analisa e processa periodicamente as solicitações geradas. Também é onde o administrador de A/R converte as solicitações aprovadas em deduções ou pagamentos regulares, dependendo do método de pagamento da solicitação.

Na página **Bancada de reembolso de despesas**, você pode rever as linhas de solicitação. Se as solicitações apresentarem o status **A serem recalculadas**, eles devem ser recalculados para qualquer efeito cumulativo.

### <a name="recalculate-claims"></a>Recalcular solicitações

Para recalcular as solicitações, no Painel de Ação, selecione **Acumular**. Em seguida, na caixa de diálogo **Acumular descontos**, selecione o cliente.

Como resultado do recálculo, o programa gera novas solicitações para os valores para ajustar as solicitações originais ao valor de qualificação por unidade. Uma solicitação de ajuste é gerada para cada combinação exclusiva de um cliente, um item, uma moeda, uma unidade de medida, dimensões de estoque, dimensões financeiras e um grupo de impostos. Essas solicitações de ajuste têm a mesma referência à ordem de venda e ao número da fatura que as solicitações que estão sendo ajustadas (ou seja, as solicitações originalmente criadas no documento de vendas). Diferentemente da solicitação original, a solicitação de ajuste não possui valores nos campos que descrevem os valores e a quantidade da linha da ordem de venda original.

Após a conclusão do recálculo, o status das solicitações é alterado para **Calculado**. Para aprovar as solicitações, no Painel de Ação, selecione **Aprovar**.

### <a name="process-claims-and-pass-them-to-ar"></a>Processar solicitações e passá-las para A/R

As solicitações agora estão prontas para processamento de A/R. Para processá-los, no Painel de Ação, selecione **Processar**. 

Após processar as solicitações, o status foi alterado para **Marcar** e indica que um lançamento de diário (o diário lançado é o diário de provisão de descontos, conforme especificado nos parâmetros de A/R) fez com que os seguintes eventos ocorressem: 

- As solicitações foram transferidas para o saldo temporário do cliente como deduções.
- A conta de provisão de descontos foi creditada para representar o passivo futuro do cliente.
- A conta de provisão de descontos foi debitada para reconhecer o custo incorrido em relação às vendas.

Para concluir o processo, o auxiliar de A/R agora deve administrar as deduções de provisão, transferindo-as para o saldo do cliente como uma nota de crédito (passivo). 

Para iniciar a tarefa, no Painel de Ação da página **Cliente**, selecione **Cobrar** \> **Liquidar transações**. Depois, na página **Liquidar transações**, selecione **Funções** \> **Programa de reembolso de despesas**. Esta página de reembolso mostra todas as solicitações de reembolso de despesas anteriormente processadas.

Se você deseja criar uma nota de crédito, marque a caixa de seleção **Marcar** para todas as linhas e selecione **Funções** \> **Criar nota de crédito**.

Após a criação da nota de crédito, um diário é lançado. (O diário lançado é o diário de consumo AR, conforme especificado nos parâmetros de A/R). Como resultado, o valor do passivo real (crédito) foi movido para o saldo do cliente. Financeiramente, tal situação implica que os seguintes eventos ocorreram:

- A conta a receber do cliente foi creditada.
- A conta de provisão de reembolso foi debitada.

Para aprovar um evento de merchandising do tipo **Quantia total**, selecione o evento na página **Contratos de bonificação comercial**, e, na guia **Valor**, selecione **Aprovar**.

## <a name="settle-the-deduction-that-is-due-and-the-customer-short-pay-by-using-the-deduction-workbench"></a>Liquidar a dedução devida e o pagamento curto do cliente usando a bancada de dedução

Geralmente, em antecipação aos reembolsos de despesas, os clientes optam por pagar as faturas selecionadas. Para evitar problemas de reconciliação de pagamento no futuro, o auxiliar de A/R registra os pagamentos curtos como deduções quando ele registra os pagamentos reais do cliente. Em seguida, na bancada de dedução, essas deduções de cliente podem ser facilmente liquidadas em relação aos valores da solicitação devidos pela empresa.

Para registrar um pagamento curto do cliente no diário de pagamento, selecione **Contas a receber** \> **Pagamentos** \> **Diário de pagamentos** e crie um diário de pagamento. Em seguida, no Painel de Ação, selecione **Deduções**. Na página **Dedução**, você pode criar e rastrear o valor que foi pago.

O gerente de cobrança agora é responsável por liquidar a transação de nota de crédito aberta e a transação de pagamento curto uma em relação à outra na bancada de dedução.

Para gerenciar deduções, selecione **Vendas e marketing** \> **Incentivos comerciais** \> **Deduções** \> **Bancada de dedução**. A seção superior da página contém linhas que representam os pagamentos curtos do cliente. A seção inferior da página contém as transações de crédito abertas do cliente. 

Para liquidar a dedução em relação à transação aberta, marque a linha de dedução e, na guia Transações abertas, marque a linha. No Painel de Ação, clique em Manter > Conciliar.

O status das solicitações de origem agora está definido como **Concluído**.

## <a name="analyze-the-effectiveness-of-the-promotion-and-fund-consumption"></a>Analisar a eficácia da promoção e do consumo do fundo

Para obter uma visão geral das principais estatísticas e do uso de recursos do programa, você pode usar vários relatórios e visões analíticas que estão disponíveis no Gerenciamento de bonificação comercial.

Na página **Atividade de bonificação comercial**, a guia **Visão geral** mostra os principais detalhes do contrato de bonificação comercial. As outras guias mostram detalhes mais específicos sobre os documentos associados, pagamentos e outros eventos relacionados ao programa.

A guia **Resumo** mostra a quantidade total de produtos vendidos na promoção, o valor de vendas faturado e as faturas e montantes fixos pagos.

A guia **Créditos de reembolso de despesas** contém os detalhes de reembolsos de despesas que foram creditados ao cliente.

Para obter uma visão geral mais analítica das várias medidas de desempenho para a promoção, você pode usar a exibição Análise. Para acessar a exibição Análise, clique em **Vendas e marketing** \> **Incentivos comerciais** \> **Contratos de bonificação comercial**. No Painel de Ação, clique em **Análise**.  

Para obter uma visão geral mais analítica das várias medidas de desempenho para a promoção, você pode usar a exibição Análise. Para acessar a exibição Análise, clique em **Vendas e marketing** \> **Incentivos comerciais** \> **Contratos de bonificação comercial**. No Painel de Ação, clique em **Análise**. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
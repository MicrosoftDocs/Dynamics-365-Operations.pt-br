---
title: Reembolsos de fornecedor
description: Este tópico fornece uma visão geral das tarefas mais comuns que você pode querer executar ao trabalhar com reembolsos de fornecedor. Os reembolsos de fornecedor ajudam as empresas a gerenciar melhor seus programas de reembolsos do fornecedor, automatizando as tarefas que são necessárias para administrar, rastrear e solicitar reembolsos que são obtidos.
author: omulvad
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: 42c35fcca90b7dc55c8ef2985283d2ce92c4c8bc
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344211"
---
# <a name="vendor-rebates"></a>Reembolsos de fornecedor

[!include [banner](../includes/banner.md)]

Os reembolsos de fornecedor ajudam as empresas a gerenciar melhor seus programas de reembolsos do fornecedor, automatizando as tarefas que são necessárias para administrar, rastrear e solicitar reembolsos que são obtidos.

Este tópico fornece uma visão geral das tarefas mais comuns que você pode querer executar ao trabalhar com reembolsos de fornecedor. A visão geral abrange as seguintes tarefas:

- Revisar detalhes de um contrato de reembolso.
- Identificar as ordens que qualificam reembolsos e gerenciar as solicitações de reembolso.
- Revisar e aprovar reembolsos.

## <a name="audience-and-purpose"></a>Público-alvo e finalidade

As informações deste tópico são direcionadas para tomadores de decisão de negócios das empresas, em posições como gerente da compra, diretor financeiro (CFO) e gerente de contabilidade que têm as seguintes responsabilidades:

- Negociar preço, desconto e contratos de reembolso com o fornecedor.
- Gerenciar a equipe que processa as solicitações de reembolso e coleta pagamentos.
- Solicitar o estoque com os melhores preços possíveis.

As pessoas nestas posições estão procurando maneiras de atingir várias metas. Eis alguns exemplos:

- Acomodar de forma flexível diferentes tipos de programas de promoção e condições de reembolso do fornecedor.
- Reduzir a carga e erros administrativos associados ao monitoramento de desempenho da promoção e às solicitações de processamento.
- Aumentar as previsões de fluxo de caixa acumulando para futuras contas a receber.
- Ter uma base quantificada para negociações atuais e futuras com fornecedores sobre reembolsos.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>Revisar detalhes de um contrato de reembolso do fornecedor.

Um contrato de reembolso do fornecedor é um registro de um contrato com um fornecedor que especifica os temos e condições negociados, nos quais a empresa é qualificada para uma recompensa monetária em troca de obter metas de compra predefinidas. Os contratos de reembolso do fornecedor são registrados na página **Contratos de reembolso**.

Para abrir a página **Contratos de reembolso de fornecedor**, selecione &gt; **Compras** **Reembolsos de fornecedor** &gt; **Contratos de reembolso**.

![Contrato de compra.](media/purchase-agreement.PNG)

Na página **Contratos de reembolso de fornecedor**, você pode exibir detalhes sobre as condições negociadas de um contrato de fornecedor.

O cabeçalho do contrato especifica as condições gerais que qualificam uma empresa para reembolsos. Na verdade, as informações de cabeçalho especificam se um fornecedor concede um reembolso quando um produto específico é comprado com uma quantidade específica. No cabeçalho, você também pode especificar a opção de descontos da unidade de medida e o tipo de data de cálculo.

- Na guia **Visão geral**, se você tiver linhas com **código de item** definido como *tabela* para especificar o item, o contrato será para aquele item específico. Se você tiver linhas com **código de item** definido como *Grupo* ou *Todos* para especificar os itens, o contrato de desconto do fornecedor será, individualmente, processado por item qualificado para o código de item, não em todos os itens qualificados para o código de item.

- Na guia **Geral**, no campo **Unidade de medida da opção de reembolso**, você pode definir se uma unidade de medida deve ser uma condição para a linha de ordem de compra qualificar uma solicitação de reembolso.

    - **Converter** – Uma linha de ordem de compra é qualificada para reembolso do fornecedor por contrato de reembolso. Você receberá um reembolso, independentemente de unidade de medida aplicada na linha.
    - **Correspondência exata** – Para qualificar para um reembolso, uma linha de compra deve ter a mesma unidade de medida especificada no contrato.

- Na guia **Geral**, no campo **Tipo de data de cálculo**, selecione a data usada para determinar se a compra ocorre no período de validade do acordo de reembolso.

    - **Criado** – Use a data de criação da ordem de compra.
    - **Entrega solicitada** – Use a data de entrega solicitada.

Nas linhas do contrato, você poderá especificar o acordo de reembolso do fornecedor com mais detalhes.

- No campo **Acumular compras por**, defina o cálculo da solicitação de reembolso. O valor pode ser definido para depender de um período (de semana, mês, ano, tempo de vida ou um período personalizado.) O valor **Fatura** indica que uma solicitação de reembolso será determinada sempre que uma linha de ordem de compra for faturada.
- No campo **Extraído de**, você pode especificar a base para o cálculo do reembolso.

    - **Bruto** – o reembolso é calculado com base no preço bruto do item.
    - **Líquido** – o reembolso é calculado com base no preço líquido do item (isto é, o preço depois que outros descontos tiverem sido aplicados).

- Os campos **Conta de competência do programa de reembolso** e **Conta de despesas do programa de reembolso** especifica os números de conta que receberão os valores acumulados de descontos no estágio intermediário entre aprovação e o processamento.
- Quando a opção **Aprovação necessária** for definida como **Sim**, uma solicitação de reembolso deverá ser aprovada para ser acumulada ou paga.
- O campo **Tipo quebra de linha de reembolso** especifica a base para os reembolsos.

    - **Quantidade** – Os reembolsos são baseados no volume.
    - **Valor** – Os reembolsos são baseados no valor.

- Na Guia Rápida **Linhas**, é possível ver como diferentes camadas de quantidade podem ser configuradas para conceder reembolsos diferentes. Por exemplo, na ilustração anterior, os campos **Valor - De** e **Valor - Até** indicam se uma quantidade de produtos entre 10 e 19 unidades será qualificada para reembolso de BRL 15 por unidade.

    > [!NOTE]
    > O **Valor - De** é inclusivo, enquanto o **Valor - Até** é exclusivo. Por exemplo, o campo **Tipo quebra de linha de reembolso** é definido como **Quantidade** e você insere **1** no campo **Valor - De** e **3** no campo **Valor - Até**. Nesse caso, o valor de reembolso se aplica quando você compra um ou dois itens, mas não quando você compra três itens.

- No campo **Status de aprovação de fluxo de trabalho**, o valor **Aprovado** indica que o contrato pode ser aplicado a ordens de compra que atendam as condições de contrato.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>Identificar as ordens que qualificam reembolsos e gerenciar as solicitações de reembolso

Quando as ordens de compra são feitas com um fornecedor que a empresa tem um contrato de reembolso, com o programa identifica quaisquer pagamentos futuros de crédito do fornecedor. Se as ordens de compra se qualificam para um reembolso, uma solicitação de reembolso é gerada para cada linha da ordem, assim que uma fatura for lançada. Este processo é automático. Depois, você pode revisar os reembolsos esperados e consultar e o impacto desses reembolsos no custo e a margem de lucro.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>Exiba detalhes de descontos que são aplicados a uma linha de ordem de compra por contrato de desconto do fornecedor

1. Na página **Ordem de compra**, selecione uma linha de ordem e depois **Linha de ordem de compra** &gt; **Exibir** &gt; **Detalhes de preço**.
2. Na página **Detalhes de preço**, selecione a Guia Rápida **Reembolsos**.

As informações de reembolso também são mostradas no campo **Reembolso do fornecedor** na seção **Estimativa de margem** da página **Detalhes de preço**.

> [!NOTE]
> Na página **Parâmetros de compras**, na guia **Preços**, verifique se a opção **Habilitar detalhes de preço** foi definida como **Sim**. Se a opção estiver definida como **Não**, não será possível exibir os reembolsos.

## <a name="review-and-approve-claims"></a>Revisar e aprovar reembolsos

As solicitações de reembolsos que são geradas representam pagamentos futuros que podem ser esperados do fornecedor. Antes que uma nota de crédito seja emitida ao fornecedor, o responsável de contrato normalmente quer rever as solicitações e aprová-las. Porém, observe que o status de uma solicitação determina se a solicitação está pronta para ir para o processo de aprovação.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>O status das solicitações e o efeito no processo de aprovação

Quando uma solicitação é gerada, seu status é definido como **A ser calculado** se o reembolso for concedido em uma base cumulativa ou **Calculado** se o desconto for concedido por fatura. Se o status de uma solicitação for **A ser calculado**, a solicitação deve passar por um processo de cálculo que será tratado pela função Acumular. Apenas as solicitações com status **Calculado** podem ser incluídas no processo de aprovação.

> [!NOTE]
> Se a opção **Aprovação necessária** em um contrato de reembolso do fornecedor for definida como **Não**, as solicitações que forem geradas terão o status **Aprovado**. A aprovação é obrigatória para as solicitações concedidas em uma base cumulativa.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>Aprovar solicitações e exibir lançamentos e detalhes da fatura

Quando as solicitações são aprovadas, elas podem ser processadas pelo Contas a pagar (A/P). Um memorando de crédito (fatura do fornecedor) para o valor de solicitação de reembolso é gerado automaticamente. O crédito pode ser adicionado ao saldo do fornecedor, e a equipe de A/P pode incluí-lo no processo de liquidação regular.

1. Selecione **Compras** &gt; **Reembolsos de fornecedor** &gt; **Solicitações de reembolso** para abrir uma solicitação de reembolso.
2. Fechar a solicitação de reembolso.
3. Marque a solicitação e, em seguida, no Painel de ação, selecione **Aprovar**.
4. Na página de solicitação, no campo **Fornecedor**, selecione o fornecedor que você autorizou a receber um reembolso e selecione **OK**.

    Um diário de provisão de reembolso é lançado para o valor da solicitação. Este lançamento debita a conta Reembolsos do fornecedor acumulado a receber para o crédito do fornecedor esperado e credita a conta temporária Reembolsos recebidos do fornecedor acumulado.

    ![Mensagem.](media/message.png)

5. Na lista de reembolso, selecione a linha e no Painel de ação, selecione **Transações de reembolso** para ver e navegar para o número de lote do diário para este lançamento de provisão de reembolso.

    Para mover as solicitações o processo de A/P normal, o funcionário de A/P agora deve concluir o processamento da solicitação de reembolso, executando a função Processar.

6. No painel de ações, selecione **Processar**, e **Filtro**. No campo **Critérios** do campo **Conta de fornecedor**, selecione o fornecedor para processar solicitações de reembolso, selecione outros filtros relevantes e **OK**.

    As barras de mensagens e o fato de que o status é alterado **Concluído** indicam que os seguintes eventos ocorrem:

    - Um lançamento de diário de provisão de reembolso estornou os valores temporários anteriores nas contas de despesa e contas a receber acumuladas.
    - Uma fatura de fornecedor (nota de crédito) para o valor do reembolso foi criada.

        > [!NOTE]
        > A configuração da opção **Lançamento de fatura manual** na guia **Programa de reembolso** da página **Parâmetros de compras** determina se uma fatura de fornecedor será lançada manualmente ou automaticamente como parte do processamento da solicitação.

    - Quando a fatura de fornecedor é lançada, automaticamente ou manualmente, a conta a pagar de fornecedor for lançada e os descontos e a conta de Provisões recebidas for creditada.

        > [!NOTE] 
        > O número da conta Descontos e provisões recebidos é especificado para a categoria de compras que é usada na linha da fatura de compras para o reembolso. A categoria de compras, é definida, por sua vez na guia **Programa de reembolso** da página **Parâmetros de compras**.

7. Na lista de reembolso, selecione a linha e no Painel de ação, selecione **Transações de reembolso** para ver e navegar para o número de lote do diário para este lançamento de provisão de reembolso e também para o número da fatura do fornecedor.
8. Selecione a linha para a transação de fatura de fornecedor e, depois, no painel de ações, selecione **Fatura de fornecedor**. Se a fatura de fornecedor for lançada, você verá o diário de faturas. Caso contrário, você verá a fatura de fornecedor como pendente que exige lançamento manual.

    A linha da fatura especifica detalhes de fatura de fornecedor para a categoria de compras **Comissões e reembolsos**.

9. Na página **Todos os fornecedores**, selecione o fornecedor do qual você recebe um desconto e, em seguida, no painel de ações, selecione **Transações**. Localize a linha da fatura. O valor do reembolso agora foi adicionado ao saldo do fornecedor.

## <a name="summary"></a>Resumo

O processo para processar reembolsos do fornecedor envolve várias tarefas de acompanhamento manual que geralmente são cansativas. Automatizando essas tarefas, o recurso de gerenciamento de reembolso do fornecedor pode ajudá-lo a ir para os seguintes processos:

- Geração de solicitações de reembolso precisas
- Aumento do lucro provisório e a receber esperado na contabilidade
- Atualização do saldo de fornecedor e a declaração de imposto com permissão devida


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
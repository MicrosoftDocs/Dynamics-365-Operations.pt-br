---
title: Dimensões financeiras padrão em diários financeiros
description: Este artigo descreve as regras que estabelecem como os valores de dimensão financeira são definidos nas transações inseridas por meio de diários financeiros. Ele também inclui detalhes de cenários em que as dimensões fixas são usadas.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d0fcf836e22207baae562801fb082d735df0f96
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907912"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>Dimensões financeiras padrão em diários financeiros

[!include [banner](../includes/banner.md)]

Este artigo descreve as regras que estabelecem como os valores de dimensão financeira são definidos nas transações inseridas por meio de diários financeiros (porém não por meio de diários de estoque ou de projeto). Ele também inclui detalhes de cenários em que as dimensões fixas são usadas.

## <a name="symptom"></a>Sintoma

Os valores de dimensão financeira não são definidos como esperado na Conta ou Contrapartida em um diário financeiro. Os cenários a seguir mostram dois exemplos:

Um comprovante é inserido em um diário geral. A Conta é de fornecedor e a Contrapartida é uma Conta bancária. As dimensões financeiras do fornecedor são inseridas por padrão na Conta, mas as dimensões financeiras do banco não são inseridas por padrão na Contrapartida. Em vez disso, os valores de dimensão da Conta são inseridos por padrão na Contrapartida.

Um cliente tem valores de dimensão financeira padrão atribuídos e uma conta principal de receita tem um valor de dimensão fixa atribuído para a dimensão financeira do Departamento. Um comprovante é inserido em um diário geral.  A Conta é o cliente e a Contrapartida é uma conta contábil, especificamente a conta de receita com o valor de dimensão fixa. A dimensão fixa não é definida na Contrapartida para a conta principal de receita. Em vez disso, ela é definida como o valor de dimensão do Departamento da Conta, que é proveniente do cliente.  Depois de lançar o comprovante, o valor da dimensão fixa é usado na entrada contábil lançada, mas o comprovante ainda mostra o valor do departamento do cliente na conta de receita. 

Quais regras são seguidas para os valores de dimensão financeira definidos nos comprovantes de um diário?

## <a name="resolution"></a>Resolução

Estas regras são seguidas para inserir valores de dimensão financeira por padrão nas linhas de um comprovante em diários financeiros, como o diário geral ou o diário de fatura de fornecedor. 

1. **Cabeçalho do diário**

   - As dimensões do cabeçalho do diário são inseridas por padrão nas dimensões do nome do diário.

2. **Conta de linha do diário**

   - As dimensões da conta de linha do diário são inseridas por padrão nas dimensões do cabeçalho do diário.
   - Se as dimensões financeiras estiverem em branco, os valores são inseridos por padrão das dimensões de cliente, fornecedor, banco, ativo fixo, projeto ou razão.

     - Se o tipo de conta for **Razão**, uma dimensão fixa em uma conta contábil será tratada como uma dimensão padrão durante a entrada da transação.
     - Se o tipo de conta for **Cliente**, **Fornecedor**, **Banco**, **Ativos fixos** ou **Projeto**, ainda não será possível determinar a conta principal. Portanto, uma dimensão fixa nunca será inserida por padrão para a conta.

3. **Contrapartida da linha do diário**

 - Primeiro, as dimensões de Contrapartida da linha do diário vêm do padrão das dimensões de Conta da linha do diário.

 - Se as dimensões financeiras estiverem em branco, a próxima entrada padrão será proveniente das dimensões padrão de Cliente, Fornecedor, Banco, Ativos fixos, Projeto ou Razão.
   1. Se o tipo de Contrapartida for **Razão**, uma dimensão fixa em uma Conta contábil será tratada como uma dimensão padrão durante a entrada da transação. Se um valor de dimensão já foi inserido por padrão a partir da Conta, o valor padrão ou de dimensão fixa da conta principal não substituirá o valor existente.
   2. Se o tipo de Contrapartida for **Cliente**, **Fornecedor**, **Banco**, **Ativos fixos** ou **Projeto**, a conta principal ainda não será conhecida. Então, uma dimensão fixa nunca será padrão para a Contrapartida.

4. **Lançamento**

    1. Durante o lançamento, a conta principal de cada linha da entrada contábil (para a Conta e a Contrapartida) é avaliada para determinar se há um valor de dimensão fixa. Se uma dimensão fixa for definida, os valores existentes ou vazios serão substituídos pelo valor da dimensão fixa.

        O valor da dimensão fixa **não** é exibido nas linhas do diário após o lançamento. Em vez disso, ele é mostrado na entrada contábil quando você exibe o comprovante depois de lançá-lo.

    2. Nenhum outro valor de dimensão é inserido por padrão durante o lançamento, incluindo contas contábeis adicionais que podem ser adicionadas durante o lançamento, como contas de arredondamento e intercompanhia a vencer e vencidas. As entradas de dimensão padrão para contas contábeis adicionais são obtidas da Conta ou das Contrapartidas.

Com a finalidade de inserir valores de dimensão por padrão, o processo padrão do diário não pode determinar se um valor de dimensão em branco foi intencionalmente deixado em branco ou se a entrada padrão não foi realizada. Se um valor de dimensão for intencionalmente deixado em branco, um valor ainda poderá ser inserido por padrão usando a ordem padrão descrita anteriormente. Se você precisar que uma dimensão tenha um valor em branco, talvez seja necessário criar uma dimensão com um valor de **0** (zero) ou **Em branco**, para que possa ser usada no lugar de uma dimensão em branco.

Analise os cenários a seguir para ver exemplos da ordem padrão da dimensão financeira.

### <a name="scenario-1"></a>Cenário 1

Vá para **Contabilidade \> Configuração do diário \> Nomes de diário** e selecione o nome de diário **GenJrn**. Em seguida, na Guia Rápida **Dimensões financeiras**, defina os seguintes valores para as dimensões financeiras padrão:

- **BUSINESSUNIT:** 001
- **DEPARTMENT:** 024

[![Página de nomes de diário](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

Vá para **Contabilidade \> Entradas do diário \> Diário geral** e crie um novo diário geral que usa o nome **GenJrn**. As dimensões são inseridas por padrão no nome do diário (tabela LedgerJournalName) para o cabeçalho do diário (tabela LedgerJournalTable), conforme mostrado na guia **Dimensões financeiras**.

[![Guia Dimensões financeiras na página Diários gerais](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

Vá para **Linhas**. No campo **Tipo de conta**, selecione **Razão** e, no campo **Conta**, insira **170150**. Em seguida, selecione a tecla **Tab** para sair do campo. As dimensões são inseridas por padrão do cabeçalho do diário. Portanto, o valor da **Conta** é mostrado como **170150-001-024**.

[![Linhas do diário para um diário geral na página Comprovante de diário](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

Altere o valor da **Conta** para **170150-001-023**. Insira um valor de débito ou de crédito. No campo **Tipo de contrapartida**, selecione **Razão** e, no campo **Contrapartida**, insira **600150**. Os valores de dimensão são inseridos por padrão da conta. Portanto, o valor da **Contrapartida** é mostrado como **600150-001-023**.

### <a name="scenario-2"></a>Cenário 2

Use as mesmas dimensões financeiras definidas para o nome do diário no cenário 1. Depois, vá para **Contas a receber \> Clientes \> Todos os clientes** e defina valores de dimensão financeira padrão para o cliente US-001. Selecione o cliente para abrir os detalhes dele. Na guia **Dimensões financeiras**, mantenha o valor padrão da dimensão **BUSINESSUNIT** (**001**). Adicione a dimensão **COSTCENTER** e insira **007** como o valor.

Crie um novo diário geral que usa o nome de diário **GenJrn**. Na guia **Dimensões financeiras**, altere o valor padrão de **BUSINESSUNIT** de **001** para **002**.

Vá para **Linhas**. No campo **Tipo de conta**, selecione **Cliente** e, no campo **Conta**, insira **US-001**. Para exibir as dimensões financeiras dos tipos de conta não contábil, selecione **Dimensões financeiras \> Conta**. Estas entradas padrão para os valores de dimensão financeira são inseridas:

- **BUSINESSUNIT:** 002 – a entrada padrão é obtida do cabeçalho do diário. O valor **001** não é inserido por padrão do cliente US-001, porque um valor padrão já foi inserido.
- **COSTCENTER:** 007 – a entrada padrão é obtida da configuração do cliente US-001.
- **DEPARTMENT:** 024 – a entrada padrão é obtida do cabeçalho do diário.

Ao voltar para a linha, em **Tipo de contrapartida**, selecione **Razão** e, no campo **Contrapartida**, insira **600150**. Estes valores padrão de dimensão financeira são inseridos na linha:

- **BUSINESSUNIT:** 002 – a entrada padrão é obtida das dimensões financeiras da conta. (Ela foi originalmente inserida por padrão do cabeçalho do diário.)
- **DEPARTMENT:** 024 – a entrada padrão é obtida das dimensões financeiras da conta. (Ela foi originalmente inserida por padrão do cabeçalho do diário.)
- **COSTCENTER:** 007 – a entrada padrão é obtida das dimensões financeiras da conta. (Ela foi originalmente inserida por padrão do cabeçalho do cliente.)

### <a name="scenario-3"></a>Cenário 3

No mesmo diário usado no cenário 2, adicione uma nova linha. No campo **Tipo de conta**, selecione **Razão** e, no campo **Conta**, insira **170150**. Limpe os valores de dimensão padrão para que somente a conta principal 170150 permaneça. No campo **Tipo de contrapartida**, selecione **Cliente** e, no campo **Contrapartida**, insira **US-001**. Estas entradas padrão para os valores de dimensão financeira são inseridas:

- **BUSINESSUNIT:** 002 – a entrada padrão é obtida do cabeçalho do diário, porque o valor da dimensão Conta está em branco. O valor **001** não é inserido por padrão do cliente US-001, porque um valor padrão já foi obtido do cabeçalho do diário. Se o valor de **BUSINESSUNIT** tiver sido intencionalmente deixado em branco, você deverá remover também a dimensão financeira na Contrapartida.
- **COSTCENTER:** 007 – a entrada padrão é obtida do cliente US-001, porque o valor da dimensão Conta e o valor da dimensão do cabeçalho do diário estão em branco. Se o valor de **COSTCENTER** tiver sido intencionalmente deixado em branco, você deverá remover também a dimensão financeira na Contrapartida.
- **DEPARTMENT:** 024 – a entrada padrão é obtida do cabeçalho do diário, porque o valor da dimensão Conta está em branco. Se o valor de **DEPARTMENT** tiver sido intencionalmente deixado em branco, você deverá remover também a dimensão financeira na Contrapartida.

### <a name="scenario-4"></a>Cenário 4

Use os mesmos valores de dimensão financeira padrão que você definiu para o nome do diário e o cliente nos cenários 1 e 2. Em seguida, defina um valor de dimensão fixa para a dimensão **BUSINESSUNIT** na conta principal 170150. Vá para **Contabilidade \> Plano de contas \> Contas \> Contas principais**. No campo **Conta principal**, selecione **170150** e, na guia **Substituições de entidade legal**, selecione **Adicionar**. Selecione **USMF** como a entidade legal e, em seguida, **Adicionar**. Selecione esse registro e, em seguida, **Dimensões padrão**. Altere a dimensão **BUSINESSUNIT** para **Valor fixo** e insira **003** como o valor.

Crie um novo diário geral que usa o nome de diário **GenJrn**. Na guia **Dimensões financeiras**, remova todos os valores de dimensão padrão.

Vá para **Linhas**. No campo **Tipo de conta**, selecione **Razão** e, no campo **Conta**, insira **170150**. Em seguida, selecione a tecla **Tab** para sair do campo. Os valores de dimensão são inseridos por padrão da configuração da conta principal para a conta 170150. Portanto, o valor da **Conta** é mostrado como **170150-003-**.

Altere o valor da **Conta** para **170150-004-**. **A funcionalidade de diário não impede que um valor de dimensão fixa seja alterado.** Insira um valor de débito ou de crédito. No campo **Tipo de contrapartida**, selecione **Razão** e, no campo **Contrapartida**, insira **170250**. O valor de dimensão financeira 004 é inserido como um padrão da Conta. Em seguida, lance o documento. No diário, selecione **Comprovante**. Observe que o valor **BUSINESSUNIT** é revertido para o valor de dimensão fixa, **003**, durante o lançamento.

Quando você retorna ao comprovante no diário, a dimensão **BUSINESSUNIT** **não** reflete o valor da dimensão fixa. Ela sempre tem o valor mostrado na tela antes do lançamento. O processo de lançamento não altera nada que foi inserido no comprovante. Somente a entrada contábil é alterada durante o lançamento.

## <a name="developer-notes"></a>Notas para o desenvolvedor

Se você for um desenvolvedor e quiser ver o código do processo padrão, analise os seguintes métodos:

- **LedgerJournalEngine.accountModified()** – este método é o principal ponto de entrada para o processo de padronização da dimensão de conta principal que é padrão para todos os diários (e substituído por alguns tipos de diários).
- **LedgerJournalEngine.offsetAccountModified()** – este método é o principal ponto de entrada para o processo de padronização da dimensão da contrapartida.

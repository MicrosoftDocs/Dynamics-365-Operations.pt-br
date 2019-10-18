---
title: Moeda dupla
description: Este tópico fornece informações sobre moeda dupla, em que a moeda de relatório é usada como uma segunda moeda contábil para o Microsoft Dynamics 365 Finance.
author: kweekley
manager: AnnBe
ms.date: 08/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 580f0c885373006cb9cd955a61c41704a2ac9a94
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186684"
---
# <a name="dual-currency"></a>Moeda dupla

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A funcionalidade que foi introduzida no Microsoft Dynamics 365 for Finance and Operations versão 8.1 (outubro de 2018) permite que a moeda de relatório seja realocada e usada como uma segunda moeda contábil. Essa funcionalidade é chamada de *moeda dupla*. As alterações para a moeda dupla não podem ser desativadas por meio de uma chave ou de um parâmetro de configuração. Como a moeda de relatório é usada como uma segunda moeda contábil, a forma como a moeda de relatório é calculada na lógica de lançamento foi alterada.

Além disso, diversos módulos foram aprimorados para rastrear, relatar e usar a moeda de relatório em vários processos. Os módulos afetados incluem:

- Contabilidade 
- Relatórios financeiros 
- Contas a pagar
- Contas a receber 
- Gerenciamento de caixa e bancos 
- Ativos fixos 
- Consolidações

Após um upgrade, você deve completar etapas específicas para o Gerenciamento de caixa e de bancos e Ativos fixos. Portanto, leia e entenda as seções relevantes deste tópico.

## <a name="posting-process"></a>Processo de lançamento

A lógica de lançamento foi alterada para todas as transações que geram uma entrada contábil para a contabilidade. Veja como a moeda de relatório era calculada anteriormente:

Valor na moeda de transação \> Valor na moeda contábil \> Valor na moeda de relatório

Por exemplo, uma transação é inserida na moeda dólar canadense (CAD). O valor em CAD é convertido na moeda contábil, que é o dólar americano (USD). O valor em USD é então convertido na moeda de relatório, que é o euro (EUR). Portanto, as taxas de câmbio devem existir entre CAD e USD e entre USD e EUR.

Este é o novo cálculo:

Valor na moeda de transação \> Valor na moeda contábil

Valor na moeda de transação \> Valor na moeda de relatório

Por causa dessa alteração, agora as taxas de câmbio devem existir entre CAD e USD e entre CAD e EUR.

## <a name="reports-and-inquiries"></a>Relatórios e consultas

Diversos relatórios e consultas agora mostram os valores na moeda de relatório e valores na moeda contábil. Nem todo relatório ou consulta foi atualizado. Por exemplo, os relatórios que mostram os valores apenas na moeda de transação não foram alterados.

As alterações seguem um de dois padrões:

- Se o relatório ou a consulta tivesse espaço suficiente para mostrar os valores na moeda contábil e na moeda de relatório, os valores na moeda de relatório seriam adicionados.
- Se o relatório ou a consulta não tiverem espaço suficiente para mostrar os valores nas duas moedas, foi adicionada uma opção para que os usuários pudessem selecionar a moeda que é mostrada.

Em vários relatórios e consultas, a lógica também foi adicionada para suprimir os valores de moeda de relatório se a moeda de relatório for igual à moeda contábil, ou se a moeda de relatório não tiver sido definida no razão para a entidade legal.

## <a name="financial-journals"></a>Diários financeiros

Os diários financeiros, como o diário geral e o diário de fatura de fornecedor, foram atualizados de forma que incluíssem informações adicionais sobre a moeda de relatório. Os totais para o comprovante e o diário agora são mostrados na moeda de relatório. Além disso, as informações sobre a taxa de câmbio da moeda de relatório aparecem agora na guia **Geral** das linhas do diário. Portanto, é possível substituir a taxa de câmbio da moeda de relatório quando você insere transações.

## <a name="vendor-invoices-sales-orders-and-sales-agreements"></a>Faturas de fornecedores, ordens de vendas e contratos de vendas
Faturas do fornecedor, ordens de venda e contratos de vendas foram atualizados para incluir uma taxa de câmbio fixa para a moeda do relatório. Uma taxa de câmbio fixa pode ser definida tanto para a moeda contábil quanto para a moeda de relatório quando a moeda da transação é diferente. Quando a moeda contábil e a moeda de relatório são as mesmas, a taxa de câmbio fixa será mantida em sincronia usando a taxa fixa da moeda contábil como a taxa fixa da moeda de relatório. A taxa de câmbio fixa da moeda de relatório não pode ser alterada para essa configuração. Quando a moeda contábil e a moeda de relatório são diferentes, uma taxa de câmbio fixa pode ser definida para a moeda contábil e a moeda de relatório durante a entrada da transação. Se a moeda de relatório não tiver sido definida no razão, o campo **Taxa de câmbio fixa da moeda de relatório** não está habilitado e nenhum valor de moeda de relatório é calculado.

## <a name="module-changes"></a>Alterações de módulo

Os módulos a seguir usam a moeda de relatório como uma segunda moeda contábil:

- [Contabilidade](#general-ledger)
- [Relatórios financeiros](#financial-reporting)
- [Contas a pagar](#accounts-payable-and-accounts-receivable)
- [Contas a receber](#accounts-payable-and-accounts-receivable)
- [Gerenciamento de caixa e bancos](#cash-and-bank-management)
- [Ativos fixos](#fixed-assets)
- [Consolidações](#consolidations)

### <a name="general-ledger"></a>Contabilidade

Se uma moeda de relatório tiver sido definida no razão, a contabilidade já acompanhou os valores na moeda de relatório em todas as entradas de contabilidade. No entanto, esses valores agora são convertidos em valores na moeda da transação.

As seguintes alterações adicionais foram efetuadas no módulo **Contabilidade**:

- Um tipo de taxa de câmbio separado para a moeda de relatório pode ser definido no razão. Se uma organização não quiser usar um tipo de taxa de câmbio diferente, você poderá deixar o campo do tipo de taxa de câmbio para a moeda de relatório em branco. Como alternativa, você pode selecionar o mesmo tipo de taxa de câmbio usado para a moeda contábil. Se você deixar o campo em branco, o sistema usará o tipo de taxa de câmbio para a moeda contábil.
- Um novo diário, o Diário de ajuste de moeda de relatório, permite que os ajustes sejam lançados nas contas contábeis somente na moeda de relatório. O diário permite o lançamento somente nas contas contábeis. Ele não dá suporte a intercompanhia, e a moeda deve ser a moeda de relatório da entidade legal onde o diário é lançado. Quando o diário é lançado, os valores na moeda da transação e na moeda contábil são 0 (zero) e o valor na moeda de relatório é lançado com o valor inserido na transação. Como a maneira como a moeda de relatório é usada nos módulos **Contas a pagar**, **Contas a receber** e **Ativos fixos** foi alterada, esse diário poderá ser usado para ajustes depois de um upgrade. Para obter exemplos que mostram como esse diário pode ser usado, consulte as seções sobre aqueles módulos.
- O processo de alocação de período foi atualizado de modo que alocasse valores nas moedas de transação, contábil e de relatório. Anteriormente, os valores eram alocados nas moedas da transação e contábil, e então o valor na moeda contábil era convertido na moeda de relatório. Esse comportamento poderia fazer com qeu um saldo permanecesse na conta contábil na moeda de relatório. Agora, quando os valores são calculados e usados na entrada contábil, não ocorre a conversão.
- O processo para a reavaliação de moeda estrangeira já reavaliou valores na moeda de relatório. Entretanto, o valor na moeda de relatório agora é calculado por meio do valor na moeda da transação, como descrito na seção [Processo de lançamento](#posting-process) anteriormente neste tópico.
- Muitos relatórios e consultas na Contabilidade já tinham a moeda de relatório, mas alguns não. Um exemplo é a página de listagem **Balancete**. Essa página de listagem inclui agora colunas para a moeda contábil e a moeda de relatório. Observe que as colunas da moeda de relatório estarão ocultas se a moeda contábil e a moeda de relatório forem iguais, ou se nenhuma moeda de relatório tiver sido definida no razão.

### <a name="financial-reporting"></a>Relatório financeiro

Um aprimoramento feito no módulo **Relatório financeiro** permite incluir valores na moeda de relatório em um demonstrativo financeiro de duas maneiras. Na definição de coluna, você pode relatar diretamente os valores na moeda de relatório que são lançados no razão (nova funcionalidade). Como alternativa, você pode continuar a converter os valores da moeda contábil na moeda de relatório (funcionalidade existente).

Essa alteração está disponível por meio da configuração **Exibição de moeda** na definição de coluna. Se você selecionar **Moeda de relatório do razão**, os valores na coluna não serão convertidos. Em vez disso, serão relatados diretamente na contabilidade. Se quiser a coluna para mostrar os valores convertidos, selecione a opção **Converter em XXXX**, onde *XXXX* é a moeda de relatório que a coluna deverá mostrar. Nesse caso, os valores na moeda contábil serão convertidos na moeda selecionada usando a funcionalidade existente de conversão.

### <a name="accounts-payable-and-accounts-receivable"></a>Contas a pagar e Contas a receber

Os módulos **Contas a pagar** e **Contas a receber** já acompanhavam valores de moeda de relatório. Entretanto, os valores não eram exibidos ou usados por diversos processos. Foram feitas as seguintes alterações:

- Os valores de moeda de relatório são exibidas agora em transações para clientes e fornecedores. Os valores na moeda de relatório também serão mostrados para o saldo em aberto de cada transação.
- O processo de classificação por vencimento foi atualizado de modo que uma organização pode exibir as classificações por vencimento na moeda contábil ou de relatório.
- Várias consultas e relatórios foram atualizados para que mostrem valores na moeda de relatório. Os exemplos incluem os relatórios **Reconciliação do cliente para o razão** e **Reconciliação do fornecedor para o razão**.
- O processo para a reavaliação de moeda estrangeira já reavaliou valores na moeda de relatório. Entretanto, o valor na moeda de relatório agora é calculado por meio do valor na moeda da transação, como descrito na seção [Processo de lançamento](#posting-process).
- **Consideração sobre o upgrade:** antes de um upgrade, os valores na moeda de relatório para documentos (faturas, pagamentos e assim por diante) são calculados na moeda contábil. Por exemplo, uma fatura é lançada antes do upgrade feito por uma organização, e a fatura não é paga. Durante o upgrade, a entrada contábil da fatura não é alterada. Contudo, depois do upgrade, as alterações para a moeda dupla estão em vigor. Portanto, quando é feito um pagamento para a fatura, o valor de moeda de relatório de pagamento é calculado agora com o valor na moeda da transação. Quando o pagamento e a fatura são liquidados, uma pequena diferença pode ser calculada no valor de ganho/perda realizado, já que os valores n moeda de relatórios agora são calculados de forma diferente. Se a diferença calculada for considerada significativa, o novo Diário de ajuste cambial do relatório pode ser usado para ajustar o saldo de ganho/perda realizado e das contas contábeis Contas a pagar/Contas a receber somente na moeda de relatório.

### <a name="cash-and-bank-management"></a>Gerenciamento de pagamentos à vista e bancos

Anteriormente, o módulo **Gerenciamento de caixa e de bancos** não acompanhava os valores na moeda de relatório das transações lançadas em cada conta bancária. Após um upgrade, os valores na moeda de relatório são rastreadas automaticamente para quaisquer novas transações que sejam lançadas. Entretanto, os valores na moeda de relatório devem ser adicionados às transações lançadas anteriormente no sub-razão.

- **Consideração sobre o upgrade:** como as transações de conta bancária não acompanhavam anteriormente os valores na moeda de relatório no sub-razão, foi adicionado um assistente para que você possa adicionar valores na moeda de relatório às transações de conta bancária. Esse assistente **não** lança na contabilidade novamente. Em vez disso, ele obtém os valores na moeda de relatório da contabilidade e os atualiza nas tabelas do sub-razão.

    - Para iniciar o assistente, selecione **Gerenciamento de caixa e de bancos** \> **Configuração** \> **Adicionar valores na moeda de relatório às transações de conta bancária**.
    - O assistente exibirá transações para todas as contas bancárias na empresa atual com um valor na moeda de relatório 0 (zero). Somente as transações lançadas antes do upgrade são incluídas.
    - Para cada transação de conta bancária, o assistente localiza as entradas contábeis correspondentes na contabilidade e insere um valor padrão na moeda de relatório. Embora os valores possam ser editados, recomendamos que você **não** os edite. Caso contrário, talvez você não consiga reconciliar os saldos da conta bancária na contabilidade. A única vez que você deve editar um valor é se o valor na moeda de relatório não puder ser encontrado na contabilidade. Nesse caso, o assistente mostrará um valor 0 (zero) para a moeda de relatório.
    - Se você selecionar **Cancelar** no assistente, as transações de conta bancária e todas as alterações nos valores na moeda de relatório serão salvas até a próxima vez em que você executar o assistente. Entretanto, os valores na moeda de relatório não são atualizados nas transações de conta bancária. Essa atualização só ocorrerá quando você selecionar **Concluir** no assistente. Você pode executar o assistente várias vezes. Portanto, você pode corrigir quaisquer valores incorretos na moeda de relatório se cometer um erro.

- Nenhum processo no Gerenciametno de caixa e de bancos foi alterado, mas diversos relatórios e consultas foram atualizadas de forma que mostrassem valores na moeda de relatório. Os relatórios de previsão de fluxo de caixa são uma exceção. Eles não foram atualizados para incluir os valores na moeda de relatório.

### <a name="fixed-assets"></a>Ativos Fixos

Anteriormente, o módulo **Ativos fixos** não acompanhavam os valores na moeda de relatório das transações lançadas em cada registro de ativos fixos. Após um upgrade, os valores na moeda de relatório são rastreadas automaticamente para quaisquer novas transações que sejam lançadas. Entretanto, os valores na moeda de relatório devem ser adicionados às transações lançadas anteriormente no sub-razão.

Além disso, foram feitas alterações importantes no processo de depreciação. Essas alterações exigem ação do usuário depois de um upgrade. É importante que você e leia e compreenda as alterações a seguir, mesmo se você ainda não estiver usando Ativos fixos.

- A maneira como o processo de depreciação determina o valor na moeda de relatório foi alterada. O cenário a seguir compara a forma como a depreciação anteriormente determinava o valor na moeda de relatório e como ela o determina agora.



    **Cenário de depreciação**

    Um ativo é adquirido e lançado com os valores a seguir. Observe que o valor na moeda de relatório é lançado na contabilidade, mas não é armazenado nas tabelas do sub-razão Ativo fixo.

    | Tipo de transação | Valor da transação | Taxa de câmbio | Valor em moeda contábil | Taxa de câmbio | Valor na moeda de relatório |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Aquisição      | DKK 1.000.000      | 2.0           | USD 500.000                | 2,5           | EUR 200.000               |

    **Depreciação anterior para a moeda de relatório**

    No final do ano, a proposta de depreciação é executada e calcula os valores a seguir.

    | Tipo de transação | Valor da transação | Taxa de câmbio | Valor em moeda contábil | Taxa de câmbio | Valor na moeda de relatório |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Depreciação     | USD 50.000         | 1.0           | USD 50.000                 | 2.6           | EUR 19,230.77             |

    Quando a proposta de depreciação é executada, calcula o valor na moeda contábil usando o método de depreciação. Converte então esse valor na moeda de relatório usando a taxa de câmbio entre USD e EUR. Essa conversão causa problemas, já que o ativo não pode ser totalmente depreciado na moeda de relatório quando a taxa à vista é usada.

    **Nova depreciação para a moeda de relatório**

    O processo de depreciação foi alterado de forma que o valor na moeda de relatório também é calculado usando o método de depreciação. Veja os resultados quando a depreciação é executada no ativo.

    | Tipo de transação | Valor da transação | Taxa de câmbio | Valor em moeda contábil | Taxa de câmbio                                                       | Valor na moeda de relatório |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | Depreciação     | USD 50.000         | 1.0           | USD 50.000                 | 2,5<blockquote>[!NOTE] Embora essa taxa de câmbio seja mostrada, ela não é usadas para converter na moeda de relatório.</blockquote> | EUR 20.000                |

    Quando a proposta de depreciação é executada, calcula o valor na moeda contábil e o valor na moeda de relatório usando o método de depreciação. Os valores são então usados na entrada contábil na contabilidade. Nenhuma conversão será feita para determinar o valor na moeda de relatório.

- **Consideração sobre o upgrade:** como as transações de registro de ativos fixos não acompanhavam anteriormente a moeda de relatório, foi adicionado um assistente para que você possa adicionar valores na moeda de relatório às transações de registro de ativos fixos. Esse assistente **não** lança na contabilidade novamente. Como a maneira que a proposta de depreciação calcula os valores na moeda de relatório foi alterada, o assistente **deve** ser executado e conculído para cada empresa antes que uma organização possa inserir alguma transação de depreciação.

    - Para iniciar o assistente, selecione **Ativos fixos** \> **Configuração** \> **Adicionar valores na moeda de relatório a registros de ativos fixos**.
    - O assistente exibirá transações para todos os registros de ativos fixos na empresa atual com um valor na moeda de relatório 0 (zero). Somente as transações lançadas antes do upgrade são incluídas.
    - O assistente **não** efetua pull dos valores na moeda de relatório desde a contabilidade. Como descrito no cenário anterior, os valores na moeda de relatório originalmente lançados na contabilidade incorretamente usavam a taxa de ponto. Os valores não devem aparecer no sub-razão de ativo fixo, já que o próximo cálculo de depreciação usará os valores incorretos. Em vez disso, o assistente localiza a taxa de câmbio na data da primeira aquisição. Ele então usa essa taxa de câmbio para recomendar o valor na moeda de relatório que deve ser lançado no sub-razão. Por exemplo, veja o que o assistente pode mostrar para o cenário anterior.

        | Ativo Fixo | Reserva      | Tipo de transação | Data da transação | Moeda | Valor na moeda da transação | Valor  | Taxa de câmbio | Valor na moeda de relatório |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_SLLT | Aquisição      | 6/3/2016         | DKK      | 1.000.000                      | 500,000 | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Depreciação     | 6/3/2016         | DKK      | 50.000                         | 50.000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Depreciação     | 6/3/2016         | DKK      | 50.000                         | 50.000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Depreciação     | 6/3/2016         | DKK      | 50.000                         | 50.000  | 2,5       | 250,000                   |

    - Muitos clientes acompanharam os detalhes da transação de ativos nas pastas de trabalho. Esses detalhes incluem as taxas de câmbio e os valores. Se você tiver esses dados em uma pasta de trabalho, poderá criar um tipo de taxa de câmbio personalizado e atualizá-lo com as taxas de câmbio desde a pasta de trabalho. Esse tipo de taxa de câmbio será então usado para inserir uma taxa de câmbio padrão na data de aquisição e para calcular o valor na moeda de relatório. Se um tipo de taxa de câmbio não estiver selecionado, o assistente usará o tipo de taxa de câmbio definido no razão.
    - Os valores da taxa de câmbio e da moeda de relatório não podem ser alterados. Se a taxa de câmbio for alterada, o valor na moeda de relatório será recalculado usando a nova taxa.
    - Se você selecionar **Cancelar** no assistente, as transações de registro de ativos fixos e todas as alterações nos valores de taxa de câmbio e na moeda de relatório serão salvas até a próxima vez em que você executar o assistente. Entretanto, os valores na moeda de relatório não são atualizados nas transações de registro de ativos fixos. Essa atualização só ocorrerá quando você selecionar **Concluir** no assistente. Você pode executar o assistente várias vezes. Portanto, você pode corrigir quaisquer valores incorretos na moeda de relatório se cometer um erro.
    - Quando os valores na moeda de relatório forem totalmente atualizados no sub-razão, você **deverá** definir a opção **Você atualizou todos os valores na moeda de relatório nas transações de registro de ativos fixos?** como **Sim** e então selecione **Concluir**. Os cálculos de depreciação não poderão ser concluídos até você definir a opção **Você atualizou todos os valores na moeda de relatório nas transações de registro de ativos fixos?** como **Sim**. Depois que essa opção for definida como **Sim**, o assistente não estará mais disponível.
    - Depois que as transações de ativo fixo no sub-razão são atualizadas com os valores na moeda de relatório, esses valores não corresponderão aos valores originalmente lançados na contabilidade. Entretanto, o diário Ajuste de moeda de relatório pode ser usado para atualizar os saldos das contas contábeis de depreciação na contabilidade, de forma que eles correspondam aos valores originalmente lançados.
    - Uma nova entidade **Valores na moeda de relatório de transação de ativos** adicionada ao espaço de trabalho **Gerenciamento de dados** permite que você exporte os dados do assistente. Você pode então usar os dados para determinar o saldo no sub-razão de ativos fixos para as transações de depreciação. Esse saldo pode ser então usado para determinar o valor de ajuste na moeda de relatório na contabilidade.

- **Consideração sobre o upgrade:** os novos campos de instalação foram adicionados aos ativos fixos e são uasdos no cálculo de depreciação. Pode ser necessário atualizar esses campos antes do próximo cálculo de depreciação.

    - No registro de ativos fixos (**Ativos fixos** \> **Registros**), a FastTab **Geral** tem um novo campo **Preço de aquisição na moeda de relatório**.
    - No registro de ativos fixos (**Ativos fixos** \> **Registros**), a FastTab **Geral** tem um novo campo **Valor de sucada esperado na moeda de relatório**.
    - Nos Parâmetros de ativo fixo (**Ativos fixos** \> **Configuração** \> **Parâmetros de ativo fixo**), a FastTab **Geral** tem um novo campo **Valor mínimo da depreciação na moeda de relatório**.
    - Em Registros (**Ativos fixos** \> **Configuração** \> **Registros**), a FastTab **Geral** tem dois novos campos: **Arredondar depreciação na moeda de relatório** e **Deixar o valor líquido contábil na moeda de relatório**.

- Porque a proposta de depreciação calcula agora valores na moeda contábil e na moeda de relatório, o Diário de ativo fixo foi atualizado para mostrar valores de depreciação na moeda de relatório. Para as transações de depreciação, a moeda da transação sempre será a moeda contábil. Portanto, esses valores continuarão a ser exibidos nas colunas **Débito** e **Crédito**. Duas novas colunas, **Débito na moeda de relatório** e **Crédito na moeda de relatório**, foram adicionadas à grade.

    - Os novos campos só estarão disponíveis quando o tipo de transação for um dos quatro tipos de depreciação: **Depreciação**, **Ajuste de depreciação**, **Depreciação extraordinária** ou **Provisão para depreciação especial**.
    - Se um tipo de transação de depreciação for inserido no Diário de ativo fixo, os valores na moeda de relatório aparecerão nas novas colunas. Esses valores podem ser alterados.
    - Se a moeda contábil e as moedas de relatório no razão forem iguais, os valores serão mantidos na sincronização. Se você alterar o valor de **Crédito**, o valor de **Crédito na moeda de relatório** será alterado automaticamente para corresponder a ele.
    - Se qualquer outro tipo de transação for inserido no Diário de ativo fixo, os valores de **Débito na moeda de relatório** e de **Crédito na moeda de relatório** nunca são mostrados, antes ou depois do lançamento. Os valores de moeda contábil e de moeda de relatório ainda estarão disponíveis no comprovante que lança na contabilidade.
    
### <a name="consolidations"></a>Consolidações
    
A funcionalidade introduzida no Dynamics 365 Finance versão 10.0.5 (outubro de 2019) permite, por meio do gerenciamento de recursos, mais flexibilidade de consolidação e moeda dupla. Para habilitá-la, acesse o espaço de trabalho **Gerenciamento de recursos** e selecione **Habilitar funcionalidade de moeda dupla na consolidação da Contabilidade**.

Na consolidação da Contabilidade, uma nova opção foi adicionada para consolidar os valores da moeda contábil ou de relatório das empresas de origem. Se a moeda contábil ou de relatório for a mesma que a moeda contábil ou de relatório na empresa de consolidação, os valores serão copiados diretamente em vez de convertidos.

-  Agora você pode optar por usar a moeda contábil ou a moeda de relatório da empresa de origem como a moeda da transação na empresa de consolidação.

- Os valores da moeda contábil ou de relatório da empresa de origem serão copiados diretamente nos valores da moeda contábil ou de relatório na empresa de consolidação, se uma das moedas for a mesma. Os valores da moeda contábil e de relatório na empresa de consolidação são calculados usando a taxa de câmbio, se nenhuma das moedas for a mesma.

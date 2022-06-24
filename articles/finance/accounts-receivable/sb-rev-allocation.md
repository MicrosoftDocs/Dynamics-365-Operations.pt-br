---
title: Alocação de receita
description: Este artigo explica como usar a alocação de receita na Cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 18739e0871592bc9eefcdf00f67dd4dd18f5d6f1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864358"
---
# <a name="revenue-allocation"></a>Alocação de receita

Este artigo explica como configurar parâmetros de alocação de receita para uma agenda de cobrança. Você pode configurar ou editar a alocação de receita ao criar a agenda de cobrança. Quando você abre a página **Alocação de receita** para uma agenda de cobrança ativa ou finalizada, os campos são somente leitura.

## <a name="specify-the-revenue-allocation-for-a-billing-schedule"></a>Especificar a alocação de receita para uma agenda de cobrança

Para especificar uma alocação de receita de uma agenda de cobrança, siga estas etapas:

1. Na página de listagem **Todas as agendas de cobrança/Agendas de cobrança ativas**, selecione uma agenda de cobrança ou uma linha de agenda de cobrança.
2. Na guia **Alocação de receita** na parte superior da página, selecione **Alocação de receita**.
3. No campo **Tipo de organização de vários elementos**, selecione o tipo de organização de vários elementos (MEA).
4. No campo **Número de organização de vários elementos**, especifique o número do MEA. Em seguida, no campo **Conta de receita de contrato adiada**, especifique a conta de receita de contrato adiado.

    Se você definir o campo **Tipo de organização de vários elementos** como **Único**, os mesmos valores de **Tipo de organização de vários elementos** e **Conta de receita de contrato adiada** serão aplicados a cada linha. Se você definir o campo **Tipo de organização de vários elementos** como **Vários**, você pode especificar valores diferentes de **Tipo de organização de vários elementos** e **Conta de receita de contrato adiada** para cada linha.
    
    Um número de MEA pode ser atribuído somente a dois ou mais itens. Uma única linha não pode ter seu próprio número MEA.

5. Selecione **Salvar**.

### <a name="fields"></a>Campos

A página **Organização de vários elementos** contém os seguintes campos.

| Campo | Descrição |
|---|---| 
| Tipo de organização de vários elementos | <p>Selecione o tipo de MEA para a transação:</p><ul><li>**Vários** – os itens de linha na transação fazem parte do MEA ou há mais de uma organização.</li><li>**Nenhum** – a transação é uma transação padrão que não tem alocação de receita.</li><li>**Único** – todos os itens na transação fazem parte de um único MEA.</li></ul> |
| Número de organização de vários elementos | <p>O número de MEA da linha. Este campo está disponível somente quando o campo **Tipo de organização de vários elementos** estiver definido como **Vários**.</p><p>Se este campo estiver em branco e você atribuir um número de MEA, os campos **Origem de preço de venda autônomo** e **Preço de venda autônomo** serão atualizados automaticamente com base nos valores da página **Preço de venda autônomo de item**. Somente os números de MEA atribuídos a outras linhas na ordem de venda estarão disponíveis.</p> |
| Conta de receita de contrato adiada | Especifique a conta a ser usada para entradas de diário quando uma fatura de contrato de MEA é criada. Este campo só está disponível quando a cobrança de contrato recorrente é usada. |
| **Linhas** | |
| Número da grade | O número da variante da ordem de venda. |
| Número do item | O número do item da ordem de venda. |
| Frequência de cobrança | A frequência para a alocação da receita: **Diária**, **Mensal**, **Trimestral**, **Semestral** ou **Anual**. |
| Quantidade | O valor da ordem de venda. |
| Valor do contrato | O valor do contrato. |
| Número de organização de vários elementos | <p>O número de MEA da linha. Este campo está disponível somente quando o campo **Tipo de organização de vários elementos** estiver definido como **Vários**.</p><p>Se este campo estiver em branco e você atribuir um número de MEA, os campos **Origem de preço de venda autônomo** e **Preço de venda autônomo** serão atualizados automaticamente com base nos valores da página **Preço de venda autônomo de item**. Somente os números de MEA atribuídos a outras linhas na ordem de venda estarão disponíveis. Se esses valores não estiverem configurados para o item, os valores da página **Parâmetros de alocação de receita de vários elementos** serão usados.</p> | 
| Origem de preço de venda autônomo | <p>A origem do preço de venda autônomo:</p><ul><li>**Valor** – O preço de venda autônomo é um valor que você especifica que é maior do que 0 (zero). O valor é convertido entre as moedas funcionais e de origem, conforme necessário.</li><li>**Preço de venda base** – O preço de venda autônomo corresponde ao preço de venda base do item.</li><li>**Preço da fatura** – O preço de venda autônomo corresponde ao preço da fatura do item.</li><li>**Porcentagem do item** – O preço de venda autônomo é especificado como um valor percentual e é calculado com base no preço do item. Se você selecionar essa opção, especifique a porcentagem padrão.</li><li>**Alocar valor residual** – A origem do preço de venda autônomo é calculada como *Valor do contrato total do item pai* – *Preço de venda autônomo total dos itens filhos*:</p><ul><li>*O valor total do contrato do item pai* é o valor líquido ou cobrado.</li><li>*O preço de venda autônomo total de itens filho* é a soma do preço de venda estendido ou de contrato autônomo de todos os itens filhos, exceto o item filho que usa essa origem de preço de venda autônomo.</li></ul><p>Se o valor calculado for negativo, o valor será definido como 0 (zero).</p><p>**Observação:** esta opção pode ser selecionada para apenas um item filho na divisão de receita.</p></li><li>**Nenhum** – A origem do preço de venda autônomo se baseia nos itens filhos. Esta opção se aplica a itens definidos como itens pai em um modelo de divisão de receita. Se a caixa de seleção **Divisão de receita** estiver selecionada, esta opção será selecionada automaticamente e a configuração não poderá ser alterada.</li><li>**Porcentagem de preço da fatura pai** – A origem do preço de venda autônomo é uma porcentagem do preço da fatura do item pai. Esta opção está disponível somente para itens filho em um modelo de divisão de receita.</li><li>**Porcentagem de preço padrão pai** – A origem do preço de venda autônomo é uma porcentagem do preço padrão do item pai. Esta opção está disponível somente para itens filho em um modelo de divisão de receita. Quando a opção de um item pai for alterada de **Porcentagem do preço padrão do item pai** para **Porcentagem de preço da fatura pai** ou de **Porcentagem de preço da fatura pai** para **Porcentagem de preço padrão pai**, os valores calculados também serão atualizados.</li></ul> |
| Preço de venda autônomo | <p>O preço de venda autônomo da linha, na moeda da transação.</p><p>O valor no campo **Valor** é inserido ou calculado.</p> |
| Preço de venda autônomo do contrato | O preço de venda autônomo do contrato. |
| Receita de contrato restante | O valor da receita restante do contrato. Esse valor é a soma de todas as linhas para as quais as faturas ainda não foram criadas. |
| Receita total do contrato | O valor da receita do contrato total para a linha. Esse valor é a soma de todas as linhas, independentemente de as faturas terem sido criadas para elas. |
| Conta de receita de contrato adiada | <p>Especifique a conta a ser usada para entradas de diário quando uma fatura de contrato de MEA é criada.</p><p>Este campo só está disponível quando a cobrança de contrato recorrente é usada.</p> |
| Erro | Os erros que ocorreram para a alocação de receita. |

## <a name="use-revenue-allocation-on-a-sales-order"></a>Use a alocação de receita em uma ordem de venda

Para usar a funcionalidade de alocação de receita em uma ordem de venda, siga estas etapas:

1. Na página **Todas as ordens de venda**, crie uma ordem de venda que tenha itens.
2. Na guia **Fatura**, em **Alocação de receita**, selecione **Alocação de receita**.
3. No campo **Tipo de organização de vários elementos**, selecione o tipo do MEA.
4. No campo **Número de organização de vários elementos**, especifique o número do MEA.
5. Se o campo **Tipo de organização de vários elementos** estiver definido como **Vários**, selecione as linhas que você deseja e, em seguida, selecione **Aplicar a selecionado**.
6. Selecione **Salvar**.

Se você usar os adiamentos de receita e despesas, a agenda de adiamento será criada automaticamente. Você pode ver isso na página **Todas as agendas de adiamento**.

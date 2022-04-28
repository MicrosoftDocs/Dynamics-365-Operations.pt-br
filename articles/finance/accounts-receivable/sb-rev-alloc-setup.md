---
title: Configurar alocação de receita de vários elementos
description: Este tópico descreve como configurar os parâmetros para a alocação de receita de elemento múltiplo na cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e422b16d1c4505b2837bb282918ecada902b806e
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8566352"
---
# <a name="set-up-multiple-element-revenue-allocation"></a>Configurar alocação de receita de vários elementos

A alocação de receita em vários elementos permite configurar modelos diferentes que são usados para calcular e alocar receita em vários itens. Essa funcionalidade pode ajudar você a obedecer ao Tópico 606 da Codificação de Padrões Contábeis (ASC 606) e/ou Padrão Internacional de Relatórios Financeiros 15 (IFRS 15).

## <a name="multiple-element-revenue-allocation-parameters"></a>Parâmetros de alocação de receita de vários elementos

Use a página **Parâmetros para alocação de receita de elementos múltiplos** para configurar os parâmetros para a alocação de receita de elementos múltiplos.

### <a name="standalone-selling-price-origin"></a>Origem de preço de venda autônomo

O campo **Origem de preço de venda autônomo** determina a origem do preço de venda autônomo. Você pode atualizar o valor na página **Preço de venda autônomo do item** e na transação. As opções a seguir estão disponíveis.

| Opção | Descrição |
|--------|-------------|
| Valor | O preço de venda autônomo é um valor que você especifica que é maior do que 0 (zero). O valor é convertido entre as moedas funcionais e de origem, conforme necessário. |
| Preço base de venda | O preço de venda autônomo corresponde ao preço de venda base do item. |
| Preço da fatura | O preço de venda autônomo corresponde ao preço da fatura do item. |
| Porcentagem de item | O preço de venda autônomo é especificado como um valor percentual e é calculado com base no preço do item. Se você selecionar essa opção, especifique a porcentagem padrão. |
| Alocar valor residual | <p>A origem do preço de venda autônomo é calculada como *Valor do contrato total do item pai* – *Preço de venda autônomo total dos itens filhos*:</p><ul><li>*O valor total do contrato do item pai* é o valor líquido ou cobrado.</li><li>*O preço de venda autônomo total de itens filho* é a soma do preço de venda estendido ou de contrato autônomo de todos os itens filhos, exceto o item filho que usa essa origem de preço de venda autônomo.</li></ul><p>Se o valor calculado for negativo, o valor será definido como 0 (zero).</p><p>**Observação:** esta opção pode ser selecionada para apenas um item filho na divisão de receita.</p> |
| Nenhum | A origem do preço de venda autônomo se baseia nos itens filhos. Esta opção se aplica a itens definidos como itens pai em um modelo de divisão de receita. Se a caixa de seleção **Divisão de receita** estiver selecionada, esta opção será selecionada automaticamente e a configuração não poderá ser alterada. |
| Porcentagem do preço da fatura pai | A origem do preço de venda autônomo é uma porcentagem do preço da fatura do item pai. Você pode alterar o valor padrão. Esta opção está disponível somente para itens filho em um modelo de divisão de receita. |
| Porcentagem do preço padrão pai | A origem do preço de venda autônomo é uma porcentagem do preço padrão do item pai. Você pode alterar o valor padrão. Esta opção está disponível somente para itens filho em um modelo de divisão de receita. É a opção padrão para itens filhos. Quando a opção de um item pai for alterada de **Porcentagem do preço padrão do item pai** para **Porcentagem de preço da fatura pai** ou de **Porcentagem de preço da fatura pai** para **Porcentagem de preço padrão pai**, os valores calculados também serão atualizados. |

### <a name="account-for-revenue-allocation-rounding-differences"></a>Conta para diferenças de arredondamento de alocação de receita

A **Conta de diferenças de arredondamento de alocação da receita** especifica a conta que é usada para registrar quaisquer ajustes de arredondamento para um valor de receita do contrato. Ela está disponível quando a cobrança de contrato recorrente é usada.

## <a name="item-standalone-selling-price"></a>Preço de venda autônomo de item

Use a página **Preço de venda autônomo do item** para especificar a origem e o preço de venda autônomo de um item. Os valores especificados nesta página são usados como os valores padrão na página **Alocação de receita** em várias alocações de receita de elementos e cobrança recorrente do contrato.

### <a name="specify-item-standalone-selling-price"></a>Especificar preço de venda autônomo do item

Para especificar o preço autônomo de um item, siga estas etapas.

1. Na página **Preço de venda autônomo do item**, no campo **Origem de preço de venda autônomo**, selecione a origem do preço de venda autônomo.
2. Siga uma destas etapas, dependendo do valor selecionado no campo **Origem de preço de venda autônomo**:

    * Se você selecionou **Porcentagem do item**, especifique a porcentagem no campo **Porcentagem**.
    * Se você selecionou **Valor**, especifique o valor no campo **Preço de venda autônomo**.

2. Para cada item que você quiser adicionar à lista, selecione **Adicionar**.
3. No campo **Código do item**, selecione o código do item. No campo **Relação de item**, selecione a relação do item. Para itens nos quais a caixa de seleção **Divisão de receita** estiver desmarcada, a combinação selecionada de um código de item e relação de itens deve ser exclusiva.
4. Altere o valor padrão da **Origem de preço de venda autônoma**, **Preço de venda autônomo** ou **Porcentagem**, conforme necessário.
5. Para cada item pai que você quiser adicionar à lista, selecione **Adicionar**.
6. No campo **Código do item**, selecione o código do item. No campo **Relação de item**, selecione a relação do item.
7. Marque a caixa de seleção **Divisão de receita**.
8. No campo **Relação de item**, selecione a relação do item. A lista é atualizada com o item pai e todos os itens filhos.
9. Para o item filho, altere o valor padrão do campo **Origem de preço de venda autônomo**, **Porcentagem do preço padrão pai**, **Porcentagem do preço da fatura pai** ou **Alocar valor residual**, conforme necessário.
10. Para adicionar vários itens ao mesmo tempo, selecione **Adicionar itens**.
11. Atualize a consulta para selecionar o intervalo de itens que você deseja adicionar.
12. Escolha **OK**, examine a lista de itens que você adicionou e selecione **OK**.

### <a name="fields"></a>Campos

A página **Preço de venda autônomo do item** contém os campos a seguir.

| Campo | Descrição |
|-------|-------------|
| Origem de preço de venda autônomo | <p>Selecione a origem do preço de venda autônomo:</p><ul><li>**Valor** – O preço de venda autônomo é um valor que você especifica que é maior do que 0 (zero). O valor é convertido entre as moedas funcionais e de origem, conforme necessário.</li><li>**Preço de venda base** – O preço de venda autônomo corresponde ao preço de venda base do item.</li><li>**Preço da fatura** – O preço de venda autônomo corresponde ao preço da fatura do item.</li><li>**Porcentagem do item** – O preço de venda autônomo é especificado como um valor percentual e é calculado com base no preço do item. Se você selecionar essa opção, especifique a porcentagem padrão.</li></ul>**Alocar valor residual** – A origem do preço de venda autônomo é calculada como *Valor do contrato total do item pai* – *Preço de venda autônomo total dos itens filhos*:</p><ul><li>*O valor total do contrato do item pai* é o valor líquido ou cobrado.</li><li>*O preço de venda autônomo total de itens filho* é a soma do preço de venda estendido ou de contrato autônomo de todos os itens filhos, exceto o item filho que usa essa origem de preço de venda autônomo.</li></ul><p>Se o valor calculado for negativo, o valor será definido como 0 (zero).</p><p>**Observação:** esta opção pode ser selecionada para apenas um item filho na divisão de receita.</p></li><li>**Nenhum** – A origem do preço de venda autônomo se baseia nos itens filhos. Esta opção se aplica a itens definidos como itens pai em um modelo de divisão de receita. Se a caixa de seleção **Divisão de receita** estiver selecionada, esta opção será selecionada automaticamente e a configuração não poderá ser alterada.</li><li>**Porcentagem de preço da fatura pai** – A origem do preço de venda autônomo é uma porcentagem do preço da fatura do item pai. Você pode alterar o valor padrão. Esta opção está disponível somente para itens filho em um modelo de divisão de receita.</li><li>**Porcentagem de preço padrão pai** – A origem do preço de venda autônomo é uma porcentagem do preço padrão do item pai. Você pode alterar o valor padrão. Esta opção está disponível somente para itens filho em um modelo de divisão de receita. É a opção padrão para itens filhos. Quando a opção de um item pai for alterada de **Porcentagem do preço padrão do item pai** para **Porcentagem de preço da fatura pai** ou de **Porcentagem de preço da fatura pai** para **Porcentagem de preço padrão pai**, os valores calculados também serão atualizados.</li></ul> |
| Preço de venda autônomo | Especificar o preço de venda autônomo do item. Este campo está disponível quando o campo **Origem de preço de venda autônomo** é definido como **Valor**. |
| Porcentagem | Especificar a porcentagem do preço de venda autônomo. Este campo está disponível quando o campo **Origem de preço de venda autônomo** é definido como **Porcentagem do item**, **Porcentagem do preço da fatura** ou **Porcentagem do preço padrão do pai**. |
| Divisão de receita | <p>Especifique se uma linha usa a divisão de receita:</p><ul><li>**Selecionado** – somente os itens que um modelo de divisão de receita está configurado para serem selecionados no campo **Relação de item**. Você pode selecionar esta caixa de seleção somente para itens pai de um modelo de divisão de receita.</li><li>**Desmarcado** – o item é um item padrão que não usa divisão de receita.</li></ul> |
| Relacionamento | Um símbolo indica se o item é um item pai ou filho em uma divisão de receita. |
| Código do item | <p>Selecione o código do item: **Tabela** ou **Grupo**.</p><p>Se a caixa de seleção **Divisão de receita** estiver selecionada, este campo será definido como **Tabela** e o valor não poderá ser alterado.</p> |
| Relação de item | <p>Selecione um número de item.</p><p>Se a caixa de seleção **Divisão de receita** estiver marcada, somente os itens que são itens pai para os quais um modelo de divisão de receita está configurado estarão disponíveis para seleção. Quando o item pai for selecionado, a lista será atualizada automaticamente com os itens filho desse item pai.</p> |
| Item pai | Para o item pai, este campo mostra o número do item. Para itens filhos em uma divisão de receita, ele mostra o número de item do item pai. |

## <a name="mea-templates"></a>Modelos de MEA

Use a página **Modelos de MEA** para criar e editar IDs de modelos de organização de vários elementos (MEA). Essas IDs são usadas na página **Alocação de receita** para agrupar itens.

### <a name="create-a-template"></a>Criar um modelo

Para configurar um modelo de MEA, siga estas etapas.

1. Na página **Modelos de MEA**, selecione **Novo**.
1. No campo **ID do Modelo de MEA**, insira uma ID exclusiva.
1. No campo **Descrição**, insira uma descrição.
1. No campo **Conta de receita de contrato adiada** selecione a conta que você deseja usar para entradas de diário quando uma fatura de contrato de MEA for criada. Este campo está disponível quando a cobrança de contrato recorrente é habilitada e usada.
1. Selecione **Salvar**.

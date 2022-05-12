---
title: Modelos de divisão de receita na Cobrança de assinatura
description: Este tópico explica como configurar modelos de divisão de receita para itens vendidos como pacotes.
author: JodiChristiansen
ms.date: 04/21/2022
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
ms.openlocfilehash: 5c2eb6c8e18770eb149c445f662ab7a90aad81a7
ms.sourcegitcommit: 367e323bfcfe41976e5d8aa5f5e24a279909d8ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2022
ms.locfileid: "8660446"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Modelos de divisão de receita na Cobrança de assinatura

Use a página **Modelo de divisão de receita** para configurar modelos de divisão de receita. A divisão de receita consiste em um item pai que tem itens filhos. Este tipo de item geralmente é vendido para clientes como um único item ou pacote.

Por exemplo, um item de computador pode ser criado da seguinte maneira:

- **Item pai:** Assinatura Prata
- **Itens de linha (filho):**

    - Suporte
    - Manutenção
    - Licença

Ao criar um item pai, tenha em mente as seguintes restrições:

- Um item pode ser especificado como um item pai apenas uma vez.
- O item pai pode ser selecionado como um item filho no mesmo modelo.
- Um modelo válido requer pelo menos um item filho.
- Um item pode ser especificado como um item filho para mais de um item de pacote.
- Cada relação pai-filho deve ser exclusiva.

## <a name="create-a-parent-item-that-has-child-items"></a>Crie um item pai que tem itens filhos

Siga estas etapas para criar um item pai que tenha itens filhos.

1. Na página **Modelo de divisão de receita**, selecione **Novo**.
1. No campo **Item pai**, selecione um item pai. O campo **Número da grade** será atualizado automaticamente. Você pode alterar o valor conforme desejado.
1. No campo **Método de alocação**, selecione um método de alocação.
1. Na lista de **Itens de componente**, selecione **Adicionar** para adicionar itens filhos.
1. Se você selecionou **Porcentagem** no campo **Método de alocação**, especifique uma porcentagem no campo **Porcentagem**.

    - Se você selecionou **Valor igual** no campo **Método de alocação**, o campo **Porcentagem** será atualizado automaticamente para que todos os itens tenham uma porcentagem igual.
    - Se você selecionou **Valor de variável**, **Valor pai zero** ou **Valor zero** no campo **Método de alocação**, o valor do campo **Porcentagem** será **0** (zero) e não poderá ser alterado.

1. Selecione **Salvar**.

## <a name="fields"></a>Campos

A página **Modelo de divisão de receita** contém os campos a seguir.

| Campo | Descrição |
|-------|-------------|
| Item pai | Selecione um número de item. Esse item se tornará o item pai para o item de pacote que você criar. |
| Nome do produto | O nome do produto. |
| Método de alocação | <p>Selecione o método de alocação:</p><ul><li>**Valor igual** – as porcentagens de alocação são calculadas automaticamente e igualmente divididas entre todos os itens no modelo.</li><li>**Porcentagem** – você pode especificar um valor percentual para a alocação. A soma de todas as porcentagens deve ser igual a 100.</li><li>**Valor de variável** – os itens filhos adicionados têm um valor líquido de 0 (zero). O preço dos itens filhos deve ser especificado no nível da transação.</li><li>**Valor zero** – o item pai retém o preço unitário e o valor líquido. Todos os itens filhos têm um valor líquido de 0 (zero).</li><li>**Valor pai zero** – o item pai tem um valor líquido fixo de 0 (zero). Todos os itens filhos são tratados como itens padrão. Nenhuma validação é feita para verificar se a soma dos valores de itens filhos é igual ao valor do item pai.</li></ul> |
| **Itens de componente** | |
| Item de componente | Selecione um número de item. Este item é um item filho. |
| Número da grade | Selecione o número da variante para o item. |
| Nome do produto | O nome do produto. |
| Porcentagem | <p>A porcentagem de alocação para a etapa:</p><ul><li>Se o campo **Método de alocação** estiver definido como **Porcentagem**, especifique a porcentagem.</li><li>Se o campo **Método de alocação** estiver definido como **Valor igual**, a porcentagem é calculada automaticamente de forma que cada item do modelo tenha uma porcentagem igual.</li><li>Se o campo **Método de alocação** estiver definido como **Valor da variável**, **Valor pai zero** ou **Valor zero**, a porcentagem será 0 (zero) e não poderá ser editada.</li></ul><p>O valor deste campo pode ser qualquer número positivo entre 0 (zero) e 100. A soma de todas as porcentagens deve ser igual a 100.</p> |
| Percentual total | <p>A soma dos valores na coluna **Porcentagem**.</p><ul><li>Se o campo **Método de alocação** estiver definido como **Valor igual** ou **Porcentagem**, a soma de todas as porcentagens deve ser igual a 100.</li><li>Se o campo **Método de alocação** estiver definido como **Valor da variável**, **Valor pai zero** ou **Valor zero**, a porcentagem total será 0 (zero).</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>Divisão de receita em uma ordem de venda

Para criar uma ordem de venda que tenha um item configurado para divisão de receita, siga estas etapas:

1. Na página **Ordem de venda**, crie uma ordem de venda.
2. Na linha de cada item configurado para divisão de receita, marque a caixa de seleção **Divisão de receita**. Esse item se tornará o item pai. Se o modelo já estiver configurado, os itens filhos aparecerão automaticamente na lista.
3. Para adicionar mais itens filhos, selecione **Adicionar filho de divisão de receita** e selecione o item filho que deseja adicionar.
4. Salve a ordem.

## <a name="revenue-split-with-billing-schedules"></a>Divisão de receita com agendas de cobrança

Para criar uma agenda de cobrança que tenha um item configurado para divisão de receita, siga estas etapas:

1. Na página **Todas/Agendas de cobrança ativas**, crie uma agenda de cobrança.
2. Na linha de cada item configurado para divisão de receita, marque a caixa de seleção **Divisão de receita**. Esse item se tornará o item pai. Se o modelo já estiver configurado, os itens filhos aparecerão automaticamente na lista.
3. Para adicionar mais itens filhos, selecione **Adicionar filho de divisão de receita** e selecione o item filho que deseja adicionar.
4. Continue as etapas para trabalhar com a agenda de cobrança.

> [!NOTE]
> Se a opção **Criar divisão de receita automaticamente** estiver definida como **Sim** na página **Parâmetros de cobrança recorrente de contrato**, ocorrerão as seguintes ações:
>
> - Se o item de linha for configurado como o item pai em um modelo de divisão de receita, a caixa de seleção **Divisão de receita** é selecionada automaticamente.
> - Os itens filhos são inseridos automaticamente na linha de ordem de venda ou da agenda de cobrança.
>
> Se a opção **Criar divisão de receita automaticamente** estiver definida como **Não**, o comportamento será conforme explicado anteriormente.

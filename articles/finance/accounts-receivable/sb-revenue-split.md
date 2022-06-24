---
title: Modelos de divisão de receita na Cobrança de assinatura
description: Este artigo explica como configurar modelos de divisão de receita para itens vendidos como pacotes.
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
ms.openlocfilehash: 145ca6e6f0673a5a09fe9a23cf5e163421617fd9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904749"
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

## <a name="additional-revenue-split-information"></a>Informações adicionais sobre divisão de receita

Ao adicionar um item que faz parte de uma divisão de receita, observe as seguintes informações: 

- O valor pai não pode ser adiado.
- Os valores de data de início, data de término, quantidade, unidade, local e depósito de itens filho são baseados no item pai. Esses valores não podem ser alterados para os itens filho. Todas as alterações devem ser feitas no item pai. 
- O método de precificação é **Simples** e não pode ser alterado.
- Os itens filho podem ser adicionados ou removidos.
- Os itens pai e filho devem usar o mesmo grupo de itens. 
- Os itens filho podem ter uma das seguintes configurações:

    - Os campos **Frequência de cobrança** e **Intervalos de cobrança** são definidos com o mesmo valor do item pai. 
    - O campo **Frequência da cobrança** está definido como **Uma vez**. Nesse caso, o campo **Intervalos de cobrança** é definido automaticamente como **1**. 

- A soma dos valores líquidos dos itens filho é igual ao valor pai. Se o método de alocação for **Valores zero**, tanto a soma dos valores do item filho quanto o valor pai serão 0 (zero). 

    > [!NOTE]
    > Se o método de alocação for **Valor pai zero**, a soma (diferente de zero) dos itens filho não será igual ao valor pai, que é 0 (zero). Esse método de alocação é usado para fins internos, para que os funcionários possam ver os itens filho. Contudo, os clientes só podem ver o item pai.

- Se o tipo de organização de vários elementos (MEA) do pedido de vendas for **Único**, a linha de transação de alocação de receita de vários elementos correspondente será criada quando os itens pai e filho forem adicionados. 
- Se o método de alocação para uma divisão de receita for **Valores iguais** e o valor pai for alterado, os valores serão recalculados para todas as linhas filho. 
- Para uma divisão de receita em que o método de alocação é **Valor variável**, ocorre o seguinte comportamento:

    - O valor líquido do item pai aparece na coluna **Valor pai**. Esse valor pode ser editado de forma. Contudo, o preço unitário, o valor líquido e o desconto são 0 (zero) e não podem ser editados.
    - O preço unitário dos itens filho é 0 (zero). É possível editar o preço unitário ou o valor líquido. Quando você edita um valor, o outro valor é atualizado automaticamente.

- Para uma divisão de receita em que o método de alocação é **Porcentagem**, ocorre o seguinte comportamento:

    - O valor líquido do item pai aparece na coluna **Valor pai**. Esse valor pode ser editado de forma. Contudo, o preço unitário, o valor líquido e o desconto são 0 (zero) e não podem ser editados. 
    - O valor líquido de itens filho é calculado como *Porcentagem* &times; *Valor pai*.

- Para uma divisão de receita em que o método de alocação é **Valor igual**, ocorre o seguinte comportamento:

    - O valor líquido do item pai aparece na coluna **Valor pai**. Esse valor pode ser editado de forma. Contudo, o preço unitário, o valor líquido e o desconto são 0 (zero) e não podem ser editados. 
    - O valor líquido de itens filho é calculado dividindo o valor pai em partes iguais entre todos os itens filho. 
    - Se os itens filho forem removidos ou adicionados, o valor líquido e os preços unitários serão recalculados para que todas as linhas filho tenham valores iguais. 
    - Se o valor pai não puder ser dividido igualmente, o valor líquido e o preço unitário do último item filho podem ser ligeiramente maiores ou menores do que o valor líquido e o preço unitário dos outros itens filho. 

- Para uma divisão de receita em que o método de alocação é **Valor zero**, ocorre o seguinte comportamento:

    - O preço unitário, o valor líquido e o desconto podem ser editados. O valor pai é 0 (zero) e não pode ser editado. 
    - Os valores de quantidade, unidade, local e depósito de itens filho são baseados no item pai. Não é possível alterar esses valores para os itens filho. Todas as alterações devem ser feitas no item pai. 
    - O preço unitário e o preço líquido dos itens filho são 0 (zero) e não podem ser editados. 

- Para uma divisão de receita em que o método de alocação é **Valor pai zero**, ocorre o seguinte comportamento:

    - O preço unitário, o valor pai e o valor líquido do item pai são 0 (zero).
    - Em uma agenda de cobrança, as linhas filho aparecem como se tivessem sido adicionadas manualmente e todos os valores são atualizados com base no grupo de agenda de cobrança selecionado. Esses valores podem ser editados. Em itens filho, você pode acessar as opções **Escalonamento e desconto** e **Preço avançado** usando os campos **Quantidade inserida**, **Preço unitário**, **Desconto** e **Valor líquido** em **Exibir detalhes de cobrança**. 
    - Em um pedido de venda, as linhas filho têm um desconto e uma porcentagem de desconto de 0 (zero). 
    - A frequência de cobrança dos itens pai e filho pode ser alterada e cada linha pode ter uma frequência diferente. Contudo, o item pai é atualizado automaticamente para que use a frequência menor entre suas linhas filho. Por exemplo, uma divisão de receita tem dois itens filho, um dos quais usa a frequência de cobrança **Mensal** e o outro usa a frequência de cobrança **Anual**. Nesse caso, a frequência de cobrança do item pai é atualizada para **Mensal**.

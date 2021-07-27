---
title: Preços de venda com base em atributo para a configuração de produtos baseada em restrição
description: Este tópico descreve como criar modelos de preço de venda com preços de venda com base em componentes e atributos em vez de na lista física de materiais e no roteiro.
author: sorenva
ms.date: 10/2/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2020-08-17
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 1538b806a60a9a9950f54c29bd19447c66ac9ec2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359092"
---
# <a name="attribute-based-sales-prices-for-constraint-based-product-configuration"></a>Preços de venda com base em atributo para a configuração de produtos baseada em restrição

Este tópico descreve como criar modelos de preço de venda com preços de venda com base em componentes e atributos em vez de na lista física de materiais e no roteiro. É possível criar vários modelos de preço de venda para cada modelo de configuração de produto.

## <a name="set-relevant-product-information-management-parameters"></a>Defina parâmetros relevantes de gerenciamento de informações do produto

Antes de começar a criar os modelos de preços, você deverá definir uma moeda padrão, que será usada quando você criar os modelos de preço de venda. Você também pode escolher se deseja anexar um arquivo do Microsoft Excel a um detalhamento de preço para todas as linhas de ordem ou de cotação. A divisão de preço permite compartilhar detalhes com clientes sobre a forma como você chegou a um preço de venda específico para um produto configurado.

Para definir a moeda padrão:

1. Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Parâmetros de gerenciamento de informações do produto**.
1. Abra a guia **Modelos de configuração do produto com base em restrições**.
1. Abra a lista suspensa **Moeda padrão** e selecione a sua moeda.

    ![Definir a moeda padrão para a configuração de produtos baseada em restrições.](media/prod-config-currency.png "Definir a moeda padrão para a configuração de produtos baseada em restrições")

1. Se você deseja anexar um arquivo do Excel com um detalhamento de preços para todas as linhas de ordem ou de cotação, na seção **Modelo de preço**, defina **Anexar** como *Sim*.

## <a name="build-your-sales-price-models"></a><a name="build-price-model"></a>Criar seus modelos de preço de venda

Para criar um modelo de preço de venda:

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Selecione o modelo de configuração de produto de destino.
1. No Painel de Ação, abra a guia **Modelo** e, no grupo **Configurar**, selecione **Modelos de preço**.
1. A página **Modelos de preço** é aberta.
1. Selecione um modelo de preço ou adicione um novo à grade.
1. Selecione **Editar** para abrir a página Editar do modelo selecionado, que fornece os seguintes recursos:
    - O cabeçalho do formulário mostra a moeda padrão e permite adicionar novas moedas para a configuração do seu preço.
    - O painel esquerdo mostra todos os componentes e requisitos de usuário do modelo de produto. Cada nó na árvore de modelo de produto pode ter uma expressão de preço base e um número opcional de regras de expressão. Uma regra de expressão consiste em uma condição e uma expressão e cada regra de expressão cobre uma opção de produto que ajuda a controlar o preço do produto.
    - Ao criar suas condições e expressões, você tem os mesmos operadores disponíveis para cálculos em um modelo de produto. O editor de expressões também oferece suporte a ambas as condições e expressões.
1. Selecione um nó na coluna à esquerda e use os recursos descritos na etapa anterior para estabelecer regras de definição de preços para ele (consulte também o exemplo fornecido após esse procedimento). Repita esta etapa para cada nó, conforme necessário.

O exemplo a seguir mostra um preço base de um número estático de 899,95 EUR, que pode ser modificado por uma ou mais destas cinco regras de expressão, dependendo da configuração selecionada pelo cliente:

- Para o acabamento branco do gabinete, subtraia 59,95 EUR.
- Para a proteção de cantos, adicione 35,95 euros.
- Para uma grelha frontal metálica, adicione 89,95 euros.
- Para o acabamento do gabinete de pau-rosa, adicione 119,95 euros.
- Adicione 12,95 EUR para cada unidade de altura de alto-falante.

![Exemplo de modelo de preço.](media/prod-config-rules-example.png "Exemplo de modelo de preço")

## <a name="add-support-for-multiple-currencies"></a>Adicionar suporte para várias moedas

Quando um produto configurável é vendido, o sistema verifica se os preços foram definidos explicitamente na moeda do cliente. Nesse caso, os valores explícitos são usados. Caso contrário, o sistema usará as taxas de câmbio estabelecidas para a empresa de vendas a fim de converter o valor de moeda padrão para a moeda do cliente.

Para adicionar preços explícitos em uma moeda adicional:

1. Abra a página Editar do modelo de preço, conforme descrito em [Criar seus modelos de preço de venda](#build-price-model).
1. Selecione o botão **Adicionar** no cabeçalho do modelo de preço para abrir a caixa de diálogo suspensa **Moedas**, que lista as moedas disponíveis.
1. Selecione a moeda que deseja adicionar na caixa de diálogo suspensa **Moedas** e, em seguida, selecione **OK**.
1. A lista suspensa **Moeda atual** agora inclui a moeda que você acabou de adicionar, além de todas as outras moedas que possam ter sido adicionadas anteriormente. Selecione a nova moeda e observe que a grade na seção **Regras de expressão** agora inclui dois campos de expressão:
    - **Expressão** - mostra a expressão (ou o valor constante) para encontrar o preço usando a moeda selecionada no momento para a **Moeda atual**.
    - **Expressões padrão** - mostra a expressão (ou o valor constante) para encontrar o preço usando o padrão no momento (mostrado no campo **Moeda atual**).

    > [!NOTE]
    > O campo **Condição** para as regras de expressão é "propriedade" da moeda padrão, o que significa que você não pode modificar a condição de outras moedas. Também não é possível adicionar novas regras de expressão enquanto uma moeda diferente da moeda padrão estiver selecionada como a **Moeda atual**.
1. Edite os valores na coluna **Expressão** conforme necessário para a moeda atual.

No exemplo abaixo, _EUR_ é a moeda padrão e _USD_ foi adicionado como uma moeda adicional.

![Exemplo de um modelo com várias moedas.](media/prod-config-rules-currency-example.png "Exemplo de um modelo com várias moedas")

> [!NOTE]
> Não é possível adicionar regras de expressão exclusivas para uma moeda não padrão. Para criar regras de expressão que seriam relevantes apenas para uma moeda diferente da moeda padrão, defina a expressão de preço para a moeda padrão como zero. Em seguida, defina a expressão apropriada para a moeda não padrão.

## <a name="test-your-price-model"></a>Testar seu modelo de preço

Para testar como os preços de venda funcionam em uma sessão de configuração, abra a página Editar do seu modelo de preço, conforme descrito em [Criar os modelos de preço de venda](#build-price-model) e, em seguida, selecione **Testar** no Painel de Ação. A caixa de diálogo **Testar modelo do produto** é aberta, e você pode fazer o seguinte:

- Use as definições de configuração oferecidas aqui para selecionar opções de produto e, em seguida, veja como elas afetam o valor mostrado para **Preço e data de remessa**.
- Selecione **Exibir detalhamento de preço** para baixar um documento do Excel que mostre detalhes completos sobre como o preço foi calculado.

![Testar seu modelo de produto.](media/prod-config-test.png "Testar seu modelo de produto")

A planilha baixada mostra o valor absoluto e a contribuição como uma porcentagem para cada elemento de preço ativo. Se você tiver definido a opção de modelo de preço **Anexar** na página **Parâmetros de gerenciamento de informações do produto**, essa planilha do Excel será anexada à ordem ou à linha de cotação.

![Planilha do Excel mostrando detalhamento de preço.](media/prod-config-excel-example.png "Planilha do Excel mostrando detalhamento de preço")

## <a name="set-up-selection-criteria-for-price-models"></a>Configurar critérios de seleção para modelos de preço

Quando os modelos de preço estiverem em vigor, você deverá estabelecer pelo menos um critério de seleção para selecionar o modelo de preço ao configurar a cotação ou a ordem. Para isso, você configurará uma ou mais consultas. Em uma combinação com modelos de preço de venda correspondentes, as consultas oferecem grande flexibilidade ao direcionar preços de venda para clientes, regiões, períodos e outros critérios específicos.

Para configurar critérios de seleção para modelos de preço:

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Selecione o modelo de configuração de produto de destino.
1. No Painel de Ação, abra a guia **Modelo** e, no grupo **Configurar**, selecione **Critérios de modelo de preço**. A página **Critérios do modelo de preço** é aberta.
1. Se a linha de consulta necessária ainda não existir, selecione **Novo** no Painel de Ação para adicionar uma nova linha à grade e fazer as seguintes configurações:
    - **Nome** - insira um nome para essa linha.
    - **Descrição** - descreva brevemente a consulta e para que ela serve.
    - **Modelo de preço** - selecione um [modelo de preço](#build-price-model) (do modelo de configuração atual) que a consulta aplicará quando disparada.
    - **Tipo de ordem** - selecione o tipo de ordem ao qual a consulta será aplicada.
    - **Válido de** - especifica o primeiro dia em que a consulta será aplicada.
    - **Expirar em** - especifique a última data em que a consulta será aplicada.

    ![Critério de modelo de preço.](media/prod-config-price-model-criteria.png "Critério de modelo de preço")

1. Selecione a linha da consulta que você deseja definir e, em seguida, selecione **Editar** no **Painel de Ação**. A caixa de diálogo do designer de consultas é aberta. Ele funciona como a maioria dos designers de consulta no Supply Chain Management. Use-o para definir as condições em que o modelo de preço da linha selecionada deve ser aplicado.

1. Repita as etapas 4 e 5 a para cada consulta necessária.
    > [!TIP]
    > Você pode economizar tempo copiando uma linha existente que já seja semelhante a uma nova que você precise adicionar. Para isso, selecione uma linha de destino e, em seguida, selecione **Duplicar** no Painel de Ação.

1. Depois de concluir a configuração dos critérios, organize-os na ordem apropriada na lista **Critérios do modelo de preço**. Para reposicionar uma linha, selecione a linha e, em seguida, selecione **Para Cima** ou **Para Baixo** no Painel de Ação.

    > [!IMPORTANT]
    > No momento da configuração, o sistema começa a pesquisar a partir da parte superior da lista e usa a primeira consulta que corresponde aos dados na cotação ou na linha da ordem. Portanto, você deve colocar suas consultas mais específicas na parte superior. Se você inserir uma consulta geral na parte superior da lista, esta será a que será usada, embora possa haver uma consulta mais abaixo na lista que tem como alvo o cliente ou o cliente potencial da configuração.

## <a name="set-attribute-based-sales-prices-for-the-product-model-version"></a>Definir preços de venda com base em atributo para a versão do modelo de produto

A etapa final é especificar preços de venda com base no atributo para a versão do modelo de produto. Para fazer isto:

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Selecione o modelo de configuração de produto de destino.
1. No Painel de Ação, abra a guia **Modelo** e, no grupo **Detalhes do modelo de produto**, selecione **Versões**.
1. A página **Versões** é aberta. Certifique-se de que o **Método de preço** esteja definido como **Com base em atributo**.
    ![Definir o método de preço para com base em atributo.](media/prod-config-versions.png "Definir o método de preço para com base em atributo")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
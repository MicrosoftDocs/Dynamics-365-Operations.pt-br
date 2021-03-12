---
title: Preços de venda de subscrição
description: Quando você cria uma subscrição, o preço de venda é derivado da configuração do preço de venda criada no formulário Subscrição do preço de venda.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35f4e3f3bdbdad7a48b89bad7da96d221f09bdb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974201"
---
# <a name="subscription-sales-prices"></a>Preços de venda de subscrição   

[!include [banner](../includes/banner.md)]


Quando você cria uma subscrição, o preço de venda é derivado da configuração do preço de venda criada no formulário **Subscrição do preço de venda**.

No formulário **Subscrição do preço de venda**, você pode criar preços de venda para uma subscrição específica ou pode criar preços de venda com uma aplicação mais ampla. Para que um preço de venda seja aplicado a uma subscrição, o código de período e a moeda da subscrição e do preço de venda devem ser idênticos.

Se o código de período e a moeda forem idênticos para ambas a subscrição e o preço de venda, os preços de venda da subscrição serão selecionados com base nas prioridades listadas na tabela a seguir. Uma célula em branco na tabela indica um campo vazio e um X indica um valor igual ao valor na subscrição da qual a transação é gerada.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Prioridade</p></th>
<th><p><strong>Categoria</strong></p></th>
<th><p><strong>ID do projeto</strong></p></th>
<th><p><strong>Subscrição</strong></p></th>
<th><p><strong>Moeda de venda</strong></p></th>
<th><p><strong>Código de período</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


Quando uma taxa de subscrição é criada, o preço de venda com o maior nível de detalhe, como observado na tabela acima, é selecionado como o preço de venda da subscrição.

## <a name="update-and-index-subscription-sales-prices"></a>Atualizar e indexar preços de venda da subscrição

Você pode atualizar o preço de venda da subscrição atualizando o preço base ou o índice. É possível atualizar por uma porcentagem ou para um novo valor.

## <a name="subscription-fee-sales-prices"></a>Preços de venda da taxa de subscrição

Quando você cria uma taxa de subscrição, o preço de venda se baseia na configuração do preço de venda da subscrição. Você pode usar o preço base da configuração do preço da subscrição ou criar preços de venda indexados.

## <a name="example"></a>exemplo

Você deseja configurar preços de venda da subscrição de EUR 500 para um novo projeto 9030. No formulário **Preço de venda (subscrição)**, crie uma linha de preço de venda de subscrição como indicado na tabela.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Válido de</p></th>
<th><p>Categoria</p></th>
<th><p>Projeto</p></th>
<th><p>Subscrição</p></th>
<th><p>Código de período</p></th>
<th><p>Moeda de venda</p></th>
<th><p>Preço de venda</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/08/2006</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mês</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Observe que os campos **Categoria** e **Subscrição** estão vazios.

Então, você cria as seguintes subscrições.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Subscrição no serviço</p></th>
<th><p>Projeto</p></th>
<th><p>Grupo de subscrições</p></th>
<th><p>Categoria</p></th>
<th><p>Moeda</p></th>
<th><p>Código de período</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat1</p></td>
<td><p>EUR</p></td>
<td><p>Mensalmente</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>Mensalmente</p></td>
</tr>
</tbody>
</table>


Agora, crie taxas de subscrição para as duas subscrições no grupo de subscrições Sub1:

1.  Clique em **Gerenciamento de serviço** \> **Configuração** \> **Subscrições de serviço** \> **Grupos de subscrições**.

2.  No formulário **Grupos de subscrição**, clique em **Funções** \> **Criar taxa de subscrição**.

3.  No formulário **Criar taxa de subscrição**, insira as informações apropriadas. Para obter mais informações, consulte [Criar transações de taxa de subscrição](create-subscription-fee-transactions.md).

Taxas de subscrição com um preço de venda de EUR 500 são criadas para as duas subscrições, como mostra a tabela a seguir.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Data do projeto</p></th>
<th><p>Subscrição no serviço</p></th>
<th><p>Projeto</p></th>
<th><p>Categoria</p></th>
<th><p>Data inicial</p></th>
<th><p>Data final</p></th>
<th><p>Moeda de venda</p></th>
<th><p>Preço de venda</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/08/2006</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01/01/2007</p></td>
<td><p>31/03/2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28/08/2006</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01/01/2007</p></td>
<td><p>31/03/2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Posteriormente, você decide que deseja especificar preços de venda para a categoria SubCat1 para o projeto 9030. Assim, cria uma nova linha de preço de venda com um preço de venda de EUR 550 para a combinação do projeto 9030 e a categoria de taxa SubCat1. Há agora duas linhas de preço de venda de subscrição para o projeto 9030, conforme mostrado na tabela.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Válido de</p></th>
<th><p>Categoria</p></th>
<th><p>Projeto</p></th>
<th><p>Subscrição</p></th>
<th><p>Código de período</p></th>
<th><p>Moeda</p></th>
<th><p>Preço de venda</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/08/2007</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mês</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28/08/2007</p></td>
<td><p>SubCat1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mês</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>


Repita o procedimento descrito acima para criar taxas de subscrição para as duas subscrições no grupo de subscrições Sub1. A tabela a seguir mostra as transações criadas para cada subscrição associada ao grupo de subscrições.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Data do projeto</p></th>
<th><p>Subscrição</p></th>
<th><p>Projeto</p></th>
<th><p>Categoria</p></th>
<th><p>Data inicial</p></th>
<th><p>Data final</p></th>
<th><p>Moeda de venda</p></th>
<th><p>Preço de venda</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/07/2007</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01/01/2008</p></td>
<td><p>31/03/2008</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>28/07/2008</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01/01/2008</p></td>
<td><p>31/03/2008</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Na primeira transação da subscrição 00020\_135, o preço de venda de EUR 550 é derivado do preço de venda da subscrição configurado para a combinação do projeto e da categoria específicos. Na segunda transação da subscrição 00021\_135, o preço de venda de EUR 500 é usado como preço de venda da subscrição do projeto porque não há um preço configurado para a combinação do projeto 9030 e da categoria SubCat2.

## <a name="see-also"></a>Consulte também

[Atualizar e indexar preços de venda da subscrição](update-and-index-subscription-sales-prices.md)

  



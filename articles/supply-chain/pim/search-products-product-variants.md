---
title: Procurar produtos e grades de produtos durante uma entrada de ordem
description: Use o campo **Número de item** para procurar produtos e grades de produtos ao criar manualmente uma linha de ordem de venda ou uma linha de ordem de compra. Isso permite que você encontre rapidamente grades de produto quando você tem somente a cadeia de caracteres de configuração ou uma das dimensões de produto disponíveis.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, PurchTablePart, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9fea7f82ac7723d4cb83c5c8224251fd6c43a315
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565679"
---
# <a name="search-for-products-and-product-variants-during-order-entry"></a>Procurar produtos e grades de produtos durante uma entrada de ordem

[!include [banner](../includes/banner.md)]

Use o campo **Número de item** para procurar produtos e grades de produtos ao criar manualmente uma linha de ordem de venda ou uma linha de ordem de compra.  Isso permite que você encontre rapidamente grades de produto quando você tem somente a cadeia de caracteres de configuração ou uma das dimensões de produto disponíveis.

Às vezes, ter algo em grande quantidade é uma situação na qual não se deseja estar, especialmente quando você vende vários produtos semelhantes e está tentando se lembrar de números de itens ou nomes de pesquisa de produto para encontrar o produto certo que será colocado em uma ordem de venda. Você pode usar o campo **Número do item** em uma linha da ordem de venda ou uma linha da ordem de compra como um campo de pesquisa. É possível inserir qualquer parte do nome, número ou dimensão de um produto e obter uma pesquisa que exiba todos os itens correspondentes à palavra da pesquisa.

## <a name="how-search-works"></a>Como a pesquisa funciona
Ao procurar produtos ou grades de produtos, é importante entender como o recurso de pesquisa encontra os produtos correspondentes ao texto inserido por você. As principais regras de pesquisa em resultados de pesquisa são:

-   Os resultados de pesquisa retornarão qualquer registro correspondente, independentemente do campo no qual o texto de pesquisa é inserido.
-   O texto da pesquisa precisa estar presente no registro correspondente em seu tamanho total.
-   A correspondência ocorrerá mesmo que o texto da pesquisa esteja localizado no meio de uma cadeia de caracteres de texto no registro correspondente. Ela não precisa aparecer no início da cadeia de caracteres de texto.
-   O texto da pesquisa é tratado como uma única cadeia de caracteres mesmo que contenha espaços em branco.

### <a name="examples"></a>Exemplos

Os seguintes exemplos usam produtos e grades de produtos para ilustrar como a pesquisa é tratada em vários cenários. **Pré-requisito:** em **Vendas e marketing &gt; Configuração &gt; Pesquisa &gt; Parâmetros de pesquisa &gt; Tipo de pesquisa**, selecione a opção **Correspondência total**.

| Tipo de Produto     | Nome do produto    | Exibir número do produto | Nº de itens | Configuração |
|------------------|-----------------|------------------------|-------------|---------------|
| Produto distinto | SpeakerMidRange | D0001                  | D0001       | N/A            |
| Grade de produto  | Alto-falante ativo  | D0010:::Black:         | D0010       | 000005        |
| Grade de produto  | Alto-falante ativo  | D0010:::White:         | D0010       | Branco         |

Se você digitar "fala" no campo **Número do item**, obterá todos os produtos acima como resultado da pesquisa. Ao digitar "preto" no campo **Número de item**, você obterá o segundo produto como resultado, porque ele tem o texto "preto" no número de produto de exibição. Esses dois exemplos mostram que a pesquisa não é feita apenas no início do campo, pois uma correspondência ocorrerá mesmo que o texto da pesquisa seja encontrado no meio de uma cadeia de caracteres de texto no registro correspondente.  

Ao digitar "05", você obterá apenas a segunda grade de produto como resultado, porque ela tem "05" na configuração. Isso mostra que a pesquisa está em todos os campos habilitados na página **Critérios de pesquisa**.  

Ao digitar "fala 05", você não obterá qualquer resultado. Isso porque a pesquisa procura o texto completo inserido. A pesquisa não tentará encontrar "fala" e depois restringir os resultados àqueles contendo "05".  

Você pode limitar o número de resultados de pesquisa usando o campo **Número de resultados** na página **Vendas e marketing &gt; Configuração &gt; Pesquisa &gt; Parâmetros de pesquisa**. Ao definir esse campo como 0, todos os resultados da pesquisa serão retornados. Ao defini-lo como 10, por exemplo, ele retornará 10 resultados de pesquisa no máximo.

## <a name="configure-the-product-search"></a>Configurar a pesquisa de produtos
Antes de usar o recurso de pesquisa de produtos e grades de produtos, siga estas etapas para configurar a pesquisa de produtos. [![3 etapas para configurar a pesquisa de produtos\_AXAppFall.](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>1ª etapa: inclua todos os identificadores e dimensões relevantes de produtos e grades de produtos nos critérios de pesquisa

Os exemplos de identificadores e dimensões de produtos e grades de produtos pelos quais você pode realizar uma pesquisa são **Nome do produto, Número do item**, **Exibir número do produto, Configuração, Cor, Tamanho, Estilo, Nome de pesquisa etc**.  

Acesse a página **Vendas e marketing &gt; Configuração &gt; Pesquisa &gt; Critérios de pesquisa**. A página **Critérios de pesquisa** permite definir os critérios para pesquisa de cliente, cliente potencial e produto. Filtre a página usando critérios de pesquisa de produtos. Você pode fazer isso alternando para **Produto** no menu da página.  

Para adicionar o número do produto de exibição aos critérios de pesquisa, clique em **Novo** no menu da página. Isto irá adicionar um novo registro na grade **critérios de pesquisa**. Abra a pesquisa da coluna **Nome do campo** e selecione **DisplayProductNumber**. Para adicionar a configuração do produto aos critérios de pesquisa, crie um registro na grade **Critérios de pesquisa** e selecione **configId** na coluna **Nome do campo**. Da mesma forma, crie um registro com **Nome do campo** **InventColorId** para a dimensão de cor, **InventSizeId** para a dimensão de tamanho e **InventStyleId** para a dimensão de estilo.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>2ª etapa: preencha o tabela de banco de dados que é usada na pesquisa de produto

Na página **Critérios de pesquisa**, clique no botão **Atualizar dados de pesquisa**. Na caixa de diálogo **Atualizar dados de pesquisa**, verifique se **Origem** está definido como **Produto** e, em seguida, clique em **OK**. O sistema agregará em uma tabela todos os critérios de pesquisa selecionados especificados na etapa 1. Se você tiver uma grande quantidade de produtos e grades de produtos, essa operação poderá ser bastante longa e você poderá receber um aviso. É recomendável agendar o preenchimento da tabela de pesquisa no servidor de lote no momento em que o servidor não estiver muito ocupado.  

Até que a tabela seja preenchida, a pesquisa de produto não fornecerá os resultados corretos. Se não obtiver qualquer resultado de pesquisa, verifique se essa tabela está preenchida.  

A tabela só precisa ser preenchida quando os critérios de pesquisa são modificados. Produtos e grades recentemente lançados são adicionados à tabela de forma automática. Produtos e grades excluídos são removidos automaticamente da tabela.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>3ª etapa: habilite a busca por pesquisa de produto em linhas de ordem de venda e compra

Você pode habilitar essa funcionalidade acessando **Vendas e marketing &gt; Configuração &gt; Pesquisa &gt; Parâmetros de pesquisa** e definindo **Habilitar pesquisa para pesquisa** como **Sim** na guia **Geral**.  

Na entrada de linha da ordem de venda, o comportamento padrão é abrir a página **Pesquisa de produtos** quando você começa a digitar no campo **Número do item** e depois pressiona a tecla **Tab**. A página **Pesquisa de produtos** altera o contexto durante a criação da linha de ordem e pode ser considerada desnecessariamente intrusiva. Se desejar obter os resultados de pesquisa em uma busca e não perder o contexto durante a entrada da linha de ordem, você pode usar a busca por pesquisa em vez disso. Se você procurar um produto ou uma grade de produto, mas não selecionar nada na pesquisa e pressionar a tecla **Tab**, a página **Pesquisa de produtos** será exibida.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
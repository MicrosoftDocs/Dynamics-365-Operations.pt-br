---
title: Perguntas frequentes sobre transações relacionadas ao produto
description: Este tópico descreve como gerenciar traduções para produtos, valores de dimensão de produto e atributos de produto.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList, EcoResProductListPage, EcoResProductVariants, EcoResProductDetailsExtended, EcoResProductCreate, EcoResProductDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c60ed8ede095306f5a950711bdf094d5abe05433
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213023"
---
# <a name="product-related-translations-faq"></a>Perguntas frequentes sobre transações relacionadas ao produto

[!include [banner](../includes/banner.md)]

Este tópico descreve como gerenciar traduções para produtos, valores de dimensão de produto e atributos de produto. 

<a name="what-product-related-data-can-be-translated"></a>Quais dados relacionados ao produto podem ser traduzidos?
--------------------------------------------

Você pode criar traduções para as seguintes informações relacionadas ao produto:
-   Os nomes e as descrições de produtos.
-   Descrições, nomes amigáveis e texto de ajuda de valores de atributo de produto.
-   Nomes e descrições de valores de dimensão do produto.

Você pode traduzir as informações relacionadas ao produto para qualquer idioma que esteja disponível na página **Tradução do texto**. Para obter mais informações, consulte a seção a seguir **Como posso criar traduções para informações relacionadas ao produto**.

## <a name="where-can-i-view-the-translated-information"></a>Onde eu pode exibir as informações traduzidas?
Você pode exibir traduções de informações relacionadas ao produto em qualquer documento de origem externo, como uma fatura, que use um idioma onde as traduções estejam disponíveis.

## <a name="how-do-i-create-translations-for-product-related-information"></a>Como posso criar traduções para informações relacionadas ao produto?
Para criar traduções para um produto, siga estas etapas:
1.  Clique em **Gerenciamento de informações do produto** &gt; **Comum** &gt; **Produtos liberados**.
2.  Selecione um produto, e no Painel de ação, grupo **Idiomas**, clique em **Traduções**.
3.  Na página **Conversão de texto**, no campo **Idioma**, selecione um idioma. Para adicionar mais idiomas, expanda o campo **Idioma**, e clique em **OK**.
4.  No grupo **Texto traduzido**, insira traduções nos campos **Descrição** e **Nome do produto**.

Para criar traduções para atributos de produto, siga estas etapas:
1.  Clique em **Gerenciamento de informações do produto** &gt; **Comum** &gt; **Produtos liberados**.
2.  Em **Configuração**, clique em **Atributos** e, em seguida **Atributos**.
3.  Na página **Atributos**, clique em **Traduzir**.
4.  Na página **Conversão de texto**, no campo **Idioma**, selecione um idioma. Para adicionar mais idiomas, expanda o campo **Idioma**, e clique em **OK**.
5.  No grupo **Texto traduzido**, insira traduções nos campos **Descrição** e **Nome do produto** e **Texto de ajuda**.

Para criar traduções para valores de dimensão de produto, siga estas etapas:
1.  Clique em **Gerenciamento de informações do produto** &gt; **Comum** &gt; **Produtos liberados**.
2.  Selecione um produto e clique em **Dimensões do produto**.
3.  Selecione um dos links para as dimensões do produto: **Configurações**, **Tamanhos**, **Cores** ou **Estilo**.
4.  Selecione um valor de dimensão e clique em **Traduzir**.
5.  Na página **Conversão de texto**, no campo **Idioma**, selecione um idioma. Para adicionar mais idiomas, expanda o campo **Idioma**, e clique em **OK**.
6.  No grupo **Texto traduzido**, insira as traduções nos campos **Nome** e **Descrição**.

## <a name="can-the-names-of-product-variants-be-translated"></a>Os nomes de variantes de produto podem ser traduzidos?
As variantes de produto se baseiam nas dimensões de um produto lançado. Os nomes de variante de produto se baseiam em uma combinação de valores de dimensão. Quando os valores de dimensão associados a uma variante de produto são traduzidos, o nome da variante de produto aparece na versão traduzida.  

**Exemplo**  

Seu produto é uma camiseta que é vendida em diferentes tamanhos e cores e os nomes de variante se baseiam nos seguintes detalhes:
-   Número do produto: \#3
-   Dimensões: Tamanho e cor
-   Valores de dimensão de tamanho: Pequeno, Médio, Grande
-   Valores de dimensão de cor: Vermelho, Verde, Preto

O nome de uma variante de produto baseada nos valores de dimensão Pequeno e Vermelho é **\#3:Small:Red**.  

Um cliente deseja comprar algumas camisetas pequenas e vermelhas e o nome da camiseta deverá aparecer em francês na fatura. Você traduz os valores de dimensão, Pequeno e Vermelho, para o francês e o nome da variante de produto é **\#3:Petit:Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Dica</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Para definir o idioma preferencial de um cliente, siga estas etapas:
<ol><br/><li>Clique em <strong>Vendas e marketing</strong> &gt; <strong>Comum</strong> &gt; <strong>Clientes</strong> &gt; <strong>Todos</strong> <strong>clientes</strong>.</li>
<li>Clique duas vezes em uma conta de cliente para abrir a página <strong>Clientes</strong>. Na guia <strong>Geral</strong>, no campo <strong>Idioma</strong>, selecione <strong>idioma</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>O que acontece se um cliente tiver um idioma preferencial para o qual não haja traduções disponíveis?
Se não houver traduções disponíveis no idioma preferencial do cliente, os nomes e as descrições serão exibidos no idioma global de sua própria empresa.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Posso gerenciar traduções para uma série de valores de dimensão ao mesmo tempo?
Os valores de dimensão são específicos de produtos e você pode gerenciar as traduções para os valores de dimensão para cada produto. No entanto, se você criar um grupo de valores de dimensão e criar traduções para os valores do grupo de valores, será mais fácil gerenciar as traduções.   

**Exemplo**  

Sua empresa produz camisetas em estilos diferentes, cada estilo disponível nos tamanhos Pequeno, Médio e Grande. Os tamanhos são reunidos em um grupo de valores de dimensão. Quando um novo estilo de camiseta for adicionado, você poderá associá-lo ao grupo do valores de dimensão usado para tamanhos, de forma que todos os tamanhos estejam disponíveis para o produto. Você também pode adicionar ou alterar traduções para os tamanhos no grupo de valores de dimensão a qualquer momento.  

Um valor de dimensão associado a um produto por meio de um grupo de variantes de dimensão deve ser mantido do grupo de variantes de produto.   
Para criar um grupo de valores de dimensão, siga estas etapas:
1.  Clique em **Gerenciamento de informações do produto** &gt; **Configuração** &gt; **Grupos de grades**.
2.  Selecione **Tamanho** **grupos**, **Grupos de cores** ou **Grupos de estilo**.
3.  Clique em **Novo**, e então insira um nome para o grupo no **grupo** **Tamanho**, **Grupo de cores**, ou **Grupo de estilos**. Clique em **Tamanhos**, **Cores** ou **Estilos** para criar linhas para os grupos.
4.  Na página **Tamanho** **grupo** linhas, **Cor** **grupo** **linhas**, ou **Linhas do grupo de estilo**, clique em **Novo**, e depois criar os tamanhos, cores e estilos para os grupos.

Para gerenciar traduções para valores em um grupo de valores de dimensão, siga estas etapas:
1.  Siga as etapas no procedimento anterior para criar um grupo de valores de dimensão para abrir a página **Linhas de grupo de tamanhos**, **Linhas do grupo de cores** ou **Linhas de grupo de estilos**.
2.  Clique em **Tradução do texto**. Na página **Tradução de texto**, no grupo **Texto traduzido**, insira as traduções nos campos **Nome** e **Descrição**.

## <a name="when-can-translations-of-product-related-information-be-managed"></a>Quando as traduções de informações relacionadas ao produto podem ser gerenciadas?
As traduções de informações relacionadas ao produto podem ser gerenciadas em qualquer ocasião. Quando as traduções são atualizadas para um valor de dimensão associado a um produto, as informações sobre o produto são atualizadas, independentemente de o produto ter ou não transações.






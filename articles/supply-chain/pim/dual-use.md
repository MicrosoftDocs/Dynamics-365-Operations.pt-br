---
title: Mercadorias de uso duplo
description: Este tópico explica como monitorar produtos identificados como mercadorias de uso duplo, armazenar números de certificado para cada país de destino e produto relevante e imprimir números de certificado válidos em faturas, guias de remessa e/ou ordens de venda relevantes.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0847dc1ce01a6e6f4f8b72db115445f75de4aac2
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596201"
---
# <a name="dual-use-goods"></a>Mercadorias de uso duplo

[!include [banner](../includes/banner.md)]

As mercadorias de uso duplo normalmente são itens que têm aplicações civis e militares. Por exemplo, um produto químico pode ser usado como fertilizante ou explosivo. Muitos países têm regulamentações especiais que se aplicam à exportação, à importação e ao transporte de mercadorias de uso duplo. Portanto, é importante que as empresas envolvidas no comércio internacional de mercadorias de uso duplo acompanhem as várias políticas e certificados.

O recurso de uso duplo ajuda as empresas a monitorar produtos identificados como mercadorias de uso duplo, armazenar números de certificado para cada país de destino e produto relevante e imprimir números de certificado válidos em faturas, guias de remessa e/ou ordens de venda relevantes. Ele ajuda a garantir que, quando os produtos forem enviados, eles sempre incluam certificações atualizadas.

Considere o cenário a seguir:

1. A página **Configuração de país de uso duplo** no sistema indica que as remessas para a França exigem uma certificação.
2. A página **Detalhes do produto liberado** do produto X-100 indica que ele é uma mercadoria de uso duplo. Juntos, o código, a categoria, o grupo e o regime indicam a classificação do controle de exportações à qual o produto pertence.
3. A página **Certificados de uso duplo** inclui um certificado para o produto X-100 quando ele é enviado à França. Esse certificado expira em 1º de janeiro de 2020.
4. Em 17 de junho de 2020, você cria uma ordem de venda para uma empresa de cliente sediada na França e a ordem inclui o produto X-100.
5. Quando você salva a ordem de venda, o sistema determina as seguintes informações:

    1. A ordem inclui algum produto que seja uma mercadoria de uso duplo?
    2. Se a ordem incluir mercadorias de uso duplo, o país de destino exigirá certificados de uso duplo?
    3. Se o país exigir certificados de uso duplo, haverá um certificado válido para cada mercadoria de uso duplo no país de destino?

6. A ordem inclui o produto X-100, o produto está sendo enviado à França e existe um certificado francês para ele. No entanto, o certificado expirou. Portanto, você recebe a seguinte mensagem de aviso: "Os certificados de uso duplo de um ou mais itens de uso duplo nesta ordem de venda não são válidos. Deseja continuar com a confirmação?"

Este tópico explica como definir todas as configurações necessárias para configurar mercadorias de uso duplo e oferecer suporte a esse cenário.

## <a name="define-dual-use-requirements-for-each-relevant-country"></a>Definir requisitos de uso duplo para cada país relevante

Países diferentes têm requisitos diferentes para mercadorias de uso duplo. Use a página **Configuração de país de uso duplo** para monitorar os países que exigem e não exigem um certificado. As informações especificadas aqui são verificadas durante a criação de ordens de venda e você será lembrado de fornecer as certificações necessárias.

Para configurar as informações sobre requisitos de uso duplo para países diferentes, siga estas etapas.

1. Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> Produtos de uso duplo \> Configuração de país de uso duplo**.
2. Selecione uma configuração de país existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova configuração de país.
3. Defina os valores a seguir para a configuração de país nova ou selecionada.

    | Campo | descrição |
    |---|---|
    | País/região | Selecione o país para o qual você está monitorando os requisitos. |
    | Certificado Necessário | Marque esta caixa de seleção para os países que exigem uma certificação para mercadorias de uso duplo. Desmarque-a para os países que não exigem essa certificação. |

## <a name="create-dual-use-categories"></a>Criar categorias de uso duplo

As mercadorias de uso duplo geralmente devem ser categorizadas de acordo com seu número de classificação do controle de exportações (ECCN). O ECCN é um código alfanumérico que categoriza os itens com base em fatores como a mercadoria e a tecnologia. A página **Categorias de uso duplo** ajuda você a criar uma lista das categorias usadas, para fins de relatório.

Para configurar categorias de uso duplo, siga estas etapas.

1. Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> Produtos de uso duplo \> Categorias de uso duplo**.
2. Selecione uma categoria existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova categoria.
3. Defina os valores a seguir para a categoria nova ou selecionada.

    | Campos | descrição |
    |---|---|
    | Código de uso duplo | Insira o código ECCN completo (por exemplo, *3A001*).|
    | Categoria de uso duplo | Insira a parte da categoria CCL (lista de controle de comércio) do código ECCN. Por exemplo, para o código ECCN *3A001*, esse valor é *3*. |
    | Grupo de uso duplo | Insira a parte do grupo de produtos do código ECCN. Por exemplo, para o código ECCN *3A001*, esse valor é *A*. |
    | Regime de uso duplo | Insira o código de regime do item. Esse código identifica o motivo pelo qual o item é classificado como mercadoria de uso duplo. Por exemplo, para o código ECCN *3A001*, esse valor é *001*. |

## <a name="apply-dual-use-categories-to-products"></a>Aplicar categorias de uso duplo a produtos

Para identificar um produto como uma mercadoria de uso duplo e aplicar uma categoria de uso duplo a ele, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione ou crie um produto para abrir sua página **Detalhes do produto liberado**.
1. Na FastTab **Comércio exterior**, defina a opção **Produtos de uso duplo** como **Sim** para identificar o produto atual como uma mercadoria de uso duplo.
1. Defina o campo **Código de uso duplo** como o código que se aplica ao produto atual. (Você definiu esse código na página **Categorias de uso duplo** .)

Essa configuração é verificada quando você cria uma ordem de venda.

## <a name="set-up-dual-use-certificates"></a>Configurar certificados de uso duplo

Use a página **Certificados de uso duplo** para configurar e gerenciar os certificados de uso duplo necessários para cada produto e país. Você pode acompanhar os detalhes de cada certificado, como o país e as datas de validade. Você também pode definir opções para especificar onde essas informações devem ser impressas. Por exemplo, as informações podem ser impressas na fatura, na guia de remessa e/ou na ordem de venda. Essa configuração é verificada quando você cria uma ordem de venda.

1. Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> Produtos de uso duplo \> Certificados de uso duplo**.
2. Selecione um certificado existente para editá-lo ou selecione **Novo** no Painel de Ação para criar um novo certificado.
3. Defina os valores a seguir para o certificado novo ou selecionado.

    | Campo | descrição |
    |---|---|
    | Nº de itens | Selecione o número de itens da mercadoria de uso duplo à qual este certificado se aplica. |
    | País/região | O país ou a região de destino em que você deve usar este certificado. |
    | Número do certificado | O número que aparece no certificado emitido para o fornecedor ou cliente. |
    | Em vigor | Selecione a primeira data em que o certificado atual é válido.|
    | Vencimento | Selecione a última data em que o certificado atual é válido. |
    | Imprimir na fatura | Marque esta caixa de seleção para imprimir o número do certificado nas faturas endereçadas ao país especificado durante o intervalo de datas especificado. |
    | Imprimir na guia de remessa | Marque esta caixa de seleção para imprimir o número do certificado nas guias de remessa endereçadas ao país especificado durante o intervalo de datas especificado. |
    | Imprimir na ordem de venda | Marque esta caixa de seleção para imprimir o número do certificado nas ordens de venda endereçadas ao país especificado durante o intervalo de datas especificado. |

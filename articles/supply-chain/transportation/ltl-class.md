---
title: Classes de carga parcial (LTL)
description: Este artigo explica o que são classes de carga parcial (LTL) e descreve como configurá-las no Microsoft Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9c1c7233b637b84ec901d7f83ae00f8a04895edb
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838409"
---
# <a name="less-than-truckload-ltl-classes"></a>Classes de carga parcial (LTL)

[!include [banner](../includes/banner.md)]

Uma classe de carga parcial (LTL) é uma classe de remessa de frete usada para classificar itens que podem ser enviados. Geralmente, cada tipo de produto ou mercadoria tem um código National Motor Freight Classification (NMFC) que corresponde a um número de classe de frete específico para remessas LTL. As classes de frete LTL representam categorias de itens, enquanto os códigos NMFC estão relacionados a mercadorias específicas em cada uma das 18 classes de frete.

Este recurso permite usar o seu sistema para executar as seguintes tarefas:

- Defina as classes de frete LTL usadas na sua empresa.
- Atribua cada classe LTL a um código NMFC na página **Códigos NMFC**. Para obter mais informações, consulte [Códigos National Motor Freight Classification (NMFC)](nmfc-codes.md).
- Atribua um código NMFC (e, portanto, o código LTL associado) a cada produto na página **Produtos**.
- Avalie com precisão a classe LTL de cada produto ao qual um código NMFC é atribuído.
- Determine os requisitos de embalagem para cada classe LTL, verificando os padrões internacionais da LTL. Dessa forma, você garante que os produtos serão bem protegidos e enviados com segurança.
- Obtenha estimativas de remessa precisas, com base na classe de frete LTL para cada produto.

Este artigo descreve como criar classes LTL no Microsoft Dynamics 365 Supply Chain Management.

## <a name="create-an-ltl-class"></a>Criar uma classe LTL

Para criar uma classe LTL, siga estas etapas.

1. Siga uma destas etapas:

    - Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Classes LTL**.
    - Acesse **Gerenciamento de transporte \> Configuração \> Padrões de transporte \> Classes LTL**.

2. No Painel de Ações, selecione **Novo** para criar uma classe LTL. Defina os seguintes campos:

    - **Classe LTL** – insira o identificador de classe (ID) LTL interno da empresa para o tipo de mercadoria. A maioria das empresas usam o padrão internacional. Nesse caso, o valor desse campo corresponderá ao valor do campo **Classe**. Mas, se a empresa usar seu próprio padrão, insira um código que cumpra esse padrão.
    - **Nome** – insira um nome descritivo que ajudará você e outros usuários a selecionarem a classe LTL correta para cada código NMFC.
    - **Classe** – insira a ID da classe LTL padrão internacional para o tipo de mercadoria. O código inserido aqui deve estar de acordo com o padrão oficial.

## <a name="example-set-up-ltl-classes"></a>Exemplo: Configurar classes LTL

O exemplo a seguir mostra como configurar duas classes LTL diferentes que podem ser usadas com diferentes tipos de produtos.

1. Ir para **Warehouse Management \> Configuração \> Inventário \> Classes LTL** ou **Gerenciamento de transporte \> Configurar \> Padrões de transporte \> Classes LTL**.
1. No Painel de Ações, selecione **Novo**.
1. Na nova linha, defina os valores a seguir:

    - **Classe LTL:** *92,5*
    - **Nome:** *Computadores, monitores, refrigeradores*
    - **Classe:** *92,5*

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ações, selecione **Novo**.
1. Na nova linha, defina os valores a seguir:

    - **Classe LTL:** *125*
    - **Nome:** *Pequenos dispositivos domésticos*
    - **Classe:** *125*

1. No Painel de ações, selecione **Salvar**.

## <a name="additional-resources"></a>Recursos adicionais

- [Códigos National Motor Freight Classification (NMFC)](nmfc-codes.md)
- [Criar um conhecimento de embarque](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

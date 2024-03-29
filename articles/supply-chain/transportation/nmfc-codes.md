---
title: Códigos National Motor Freight Classification (NMFC)
description: Este artigo descreve como trabalhar com códigos National Motor Freight Classification (NMFC) no Microsoft Dynamics 365 Supply Chain Management
author: Weijiesa
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: c173057b8e1357790e780469c5806afb857be62a
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838308"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>Códigos National Motor Freight Classification (NMFC)

[!include [banner](../includes/banner.md)]

Os códigos National Motor Freight Classification (NMFC) ajudam você a classificar itens que podem ser enviados. O código NMFC é uma designação usada para agrupar mercadorias. Ele permite que empresas de transporte avaliem mercadorias para remessa por meio da classificação de itens com base em considerações como ajuste de caminhão, problemas de carregamento, problemas de manipulação e perecibilidade. As mercadorias são agrupadas em uma de 18 classes de frete usando um intervalo de números de 50 a 500. A classe na qual uma mercadoria é agrupada se baseia em uma avaliação de quatro características de transporte: densidade, capacidade de armazenamento, manuseio e responsabilidade. Juntas, essas características estabelecem a transportabilidade da mercadoria.

Um código NMFC está associado a cada item de remessa de carga parcial (LTL). Por exemplo, um laptop pode receber um NMFC classificado como 2,5, enquanto os cabos elétricos podem receber um NMFC classificado como 65.

Esse recurso pode ajudar os trabalhadores a usar códigos NMFC para classificar itens de remessa LTL. Veja alguns exemplos:

- Se a sua empresa incluir uma descrição de frete no conhecimento de embarque (BOL), a operadora terá uma ideia do que é o frete. O frete é uma classificação importante, pois muitas empresas de transporte baseiam todo o modelo comercial nos tipos de frete enviados.
- Essa classificação pode ser essencial para a sua empresa, pois ela é usada para determinar o custo de determinada carga.
- Sua empresa pode identificar a lucratividade de uma empresa de transporte e logística LTL.

Este artigo descreve como trabalhar com códigos NMFC no Microsoft Dynamics 365 Supply Chain Management.

## <a name="prerequisites"></a>Pré-requisitos

Para poder criar códigos NMFC, você deve configurar todas as classes de frete LTL a serem mapeadas para eles. As classes de frete LTL representam categorias de itens, enquanto os códigos NMFC estão relacionados a mercadorias específicas em cada uma das 18 classes de frete. Para obter mais informações sobre como trabalhar com classes LTL, consulte [Classes de carga parcial (LTL)](ltl-class.md).

## <a name="create-an-nmfc-code"></a>Criar um código NMFC

Para criar um código NMFC, siga estas etapas.

1. Siga uma destas etapas:

    - Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Códigos NMFC**.
    - Acesse **Gerenciamento de transporte \> Configuração \> Padrões de transporte \> Códigos NMFC**.

1. Selecione **Novo** para criar um código NMFC. Defina os seguintes campos:

    - **Código NMFC** – insira o código NMFC para o tipo de mercadoria.
    - **Nome** – insira um nome para o código NMFC.
    - **Classe LTL** – selecione a classe LTL associada ao código NMFC.
    - **Unidade de manuseio de material BOL** – defina o tipo de manuseio padrão para a remessa.

## <a name="example-set-up-nmfc-codes"></a>Exemplo: Configurar códigos NMFC

O exemplo a seguir mostra como configurar dois códigos NMFC diferentes que podem ser usados com diferentes produtos.

1. Ir para **Warehouse Management \> Configuração \> Inventário \> Códigos NMFC** ou **Gerenciamento de transporte \> Configuração \> Padrões de transporte \> Códigos NMFC**.
1. No Painel de Ações, selecione **Novo**.
1. Na nova linha, defina os valores a seguir:

    - **Código NMFC:** *92,5*
    - **Nome:** *Computadores*
    - **Classe LTL:** *92,5*
    - **Unidade de manuseio de material BOL:** *Unidade*

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ações, selecione **Novo**.
1. Na nova linha, defina os valores a seguir:

    - **Código NMFC:** *125*
    - **Nome:** *Telefones*
    - **Classe LTL:** *125*
    - **Unidade de manuseio de material BOL:** *Unidade*

1. No Painel de ações, selecione **Salvar**.

## <a name="additional-resources"></a>Recursos adicionais

- [Classes de carga parcial (LTL)](ltl-class.md)
- [Criar um conhecimento de embarque](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

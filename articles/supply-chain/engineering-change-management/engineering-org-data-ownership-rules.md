---
title: Empresas de engenharia e regras de propriedade de dados
description: Este tópico explica como você pode usar uma ou mais empresas de engenharia para garantir que os dados mestre de produtos sejam criados e mantidos centralmente. Uma empresa de engenharia representa a empresa proprietária dos produtos de engenharia e os dados relevantes da engenharia.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 837960a628ef03df4d73909e96713e256d0f5e60
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262300"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>Empresas de engenharia e regras de propriedade de dados

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>Empresas de engenharia e empresas operacionais

Para garantir que os dados mestre de produtos sejam criados e mantidos centralmente, você pode usar uma ou mais *empresas de engenharia*. Uma empresa de engenharia é proprietária dos produtos de engenharia e dos dados relevantes da engenharia. Ela está sempre conectada a (baseada em) uma *entidade legal* existente , que também é uma empresa. Por meio dessa conexão, o sistema estabelece um ponto de entrada central para todos os dados relevantes de engenharia para produtos de engenharia na empresa de engenharia. Neste ponto de entrada central, os produtos de engenharia são criados e os dados relevantes de engenharia são mantidos. Nele, os produtos de engenharia e os dados relevantes de engenharia serão liberados para *empresas operacionais*, que são outras entidades legais. (Para obter mais informações sobre o gerenciamento de liberação, consulte [Liberar estruturas de produtos](release-product-structure.md).) Essas empresas operacionais usarão os dados de engenharia da forma como foram criados pela empresa de engenharia. Qualquer dado logístico é mantido localmente por cada empresa de engenharia e empresa operacional.

Para criar uma empresa de engenharia, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Organizações de engenharia**. Selecione **Novo**, insira um nome para a empresa de engenharia e selecione a empresa existente (entidade legal) na qual ela se baseia.

Se você estiver se integrando a sistemas externos de gerenciamento do ciclo de vida do produto (PLM), deverá criar uma unidade de negócios (tipo de empresa) que se tornará uma empresa externa.

## <a name="engineering-product-categories-and-engineering-companies"></a>Categorias de produtos de engenharia e empresas de engenharia

As *categorias de produtos de engenharia* ajudam a garantir que produtos de engenharia sejam criados de acordo com as regras comerciais da empresa e se comportem conforme exigido. Para obter mais informações sobre categorias de produto de engenharia, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).

Cada categoria de produto de engenharia pertence a uma empresa de engenharia específica e só pode criar produtos pertencentes a essa empresa. Da mesma forma, o direito de manter um produto de engenharia pertence também à empresa associada à categoria de produtos de engenharia do produto.

## <a name="data-that-is-owned-by-the-engineering-company"></a>Dados de propriedade da empresa de engenharia

Como a empresa de engenharia tem os dados relevantes de engenharia, ela controla os seguintes processos:

- **Criação de produtos de engenharia:** cada empresa de engenharia só pode criar novos produtos de engenharia que se baseiem em uma categoria de produto de engenharia de propriedade dela. Em alguns casos, as empresas operacionais mantêm seus próprios dados locais relativos a esses produtos.
- **Criação de versões de engenharia:** quando uma empresa cria um novo produto de engenharia, o sistema cria automaticamente uma versão de engenharia inicial para ele. Somente a empresa de engenharia proprietária poderá criar novas versões desse produto.
- **Criação e manutenção de atributos de engenharia:** quando uma empresa cria um novo produto de engenharia, o sistema adiciona automaticamente atributos de engenharia a ela. Somente a empresa de engenharia proprietária poderá criar e manter os valores desses atributos. Para obter mais informações sobre atributos de engenharia, consulte [Atributos de engenharia e pesquisa de atributos de engenharia](engineering-attributes-and-search.md).
- **Criação e manutenção de listas de materiais (BOMs) que estão conectadas às versões de engenharia:** a empresa proprietária de engenharia pode conectar diretamente uma BOM a uma versão de produto de engenharia. Quando essas BOMs são liberadas para outras entidades legais, as alterações nos dados de engenharia nas BOMs são limitadas das seguintes maneiras:

    - A empresa operacional não pode remover linhas de BOM liberadas.
    - Os campos de engenharia nas linhas da BOM são somente leitura para a empresa operacional. Todos os outros campos são campos de implementação logística e podem ser editados pela empresa operacional.
    - A empresa operacional pode adicionar linhas de BOM à mesma BOM. Dessa forma, ele pode incluir adições locais, como materiais de embalagem ou fluidos de lubrificação.
    - A empresa operacional pode adicionar uma BOM local, totalmente nova. Essa alteração pode ser necessária, por exemplo, quando nenhuma BOM é fornecida durante a liberação. A empresa operacional é proprietária e mantém essas BOMs locais. Para obter mais informações sobre o gerenciamento de liberações, consulte [Liberar estruturas de produtos](release-product-structure.md).
    - Todas as BOMs locais e as linhas da BOM são preservadas quando a empresa de engenharia atualiza a BOM.

- **Criação e manutenção de roteiros que estão conectados às versões de engenharia:** a empresa de engenharia pode conectar diretamente um roteiro a cada versão de engenharia. Quando esses roteiros são liberados para outras entidades legais, as alterações nos dados nos roteiros são limitadas das seguintes maneiras:

    - As outras entidades legais não podem remover os dados de engenharia nos roteiros.
    - As outras entidades legais podem adicionar operações ao roteiro. Dessa forma, eles podem adicionar etapas de roteiro local.
    - As empresas operacionais podem adicionar roteiros locais, totalmente novos. Essa alteração poderá ser necessária se, por exemplo, você não tiver incluído roteiros durante a liberação. As empresas operacionais são proprietárias e mantêm esses roteiros locais. Para obter mais informações sobre o gerenciamento de liberações, consulte [Liberar estruturas de produtos](release-product-structure.md).
    - Todas as alterações feitas localmente são preservadas quando as atualizações da empresa de engenharia são liberadas novamente para os roteiros.

- **Criação e manutenção de documentos de engenharia:** a empresa de engenharia pode associar documentos de engenharia a cada versão de engenharia.

    - Quando esses documentos são liberados para outras entidades legais, os documentos são protegidos contra remoção pela empresa operacional.
    - Outras entidades legais podem adicionar documentos locais, totalmente novos. A empresa operacional é proprietária e mantém esses documentos locais.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
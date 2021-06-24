---
title: Regras de configuração
description: Este artigo oferece informações gerais sobre as regras de configuração. As regras de configuração definem as relações entre os itens em uma lista de materiais (BOM) de produtos que usam a tecnologia de configuração baseada em dimensão.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70aff927dfea602ee6c4ad5c195274248f831bcb
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6190175"
---
# <a name="configuration-rules"></a>Regras de configuração

[!include [banner](../includes/banner.md)]

Este artigo oferece informações gerais sobre as regras de configuração. As regras de configuração definem as relações entre os itens em uma lista de materiais (BOM) de produtos que usam a tecnologia de configuração baseada em dimensão.

As regras de configuração ficam disponíveis quando você define modelos de configuração baseada em dimensão. As regras de configuração são usadas para aplicar ou proibir combinações específicas do item em uma lista de materiais (BOM). Depois que uma BOM for criada e os itens relevantes forem atribuídos aos seus respectivos grupos de configuração, uma ou mais regras de configuração poderão ser definidas. Se dois itens pertencem, o operador **Select** será usado para garantir a inclusão. Se dois itens forem mutuamente exclusivos, o operador, **Cancelar seleção** será usado para garantir a exclusão.  

**Observação:** Essas informações só se aplicam aos produtos mestres que usam a tecnologia de configuração baseada em dimensão.  

As configurações existentes não são afetadas pelas alterações subsequentes às regras de configuração. Porém, é importante que você defina as regras antes de estabelecer uma nova configuração e que as verifique, caso presuma que as regras tenham sido alteradas.  

**Observação:** Para o método **Select**, o grupo de configuração, o número do item e a configuração resultantes são automaticamente selecionados. Para o método **Cancelar seleção**, o grupo de configurações, o número do item e a configuração resultantes não podem ser selecionados.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de configuração de produtos baseada em dimensão](dimension-based-product-configuration.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
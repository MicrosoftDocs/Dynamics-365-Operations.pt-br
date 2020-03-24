---
title: Filtragem avançada no RCS/repositório global
description: Este tópico descreve os recursos aprimorados de filtragem para o repositório global RCS, que foram aprimorados para incluir os filtros adicionais.
author: JaneA07
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ed5a217b8844bfc76d53370ab4c4c339f5bece36
ms.sourcegitcommit: 0dcdfedec7125562f6b33deb009a3e044a1243eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "3099858"
---
# <a name="enhanced-filtering-options-for-finding-configurations-in-the-global-repository"></a>Opções de filtragem aprimoradas para localizar configurações no repositório global

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve os recursos aprimorados de filtragem para o repositório global do Regulatory Configuration Services (RCS), que foram aprimorados para incluir os filtros a seguir: 
- **País/região** - baseado em códigos de país ISO  
- **Tags** - para área funcional/recurso; indústria, tipo de documento comercial 

Você pode aplicar filtros, individualmente ou em grupos, para localizar configurações específicas ou relacionadas. Por exemplo, para localizar todos os documentos comerciais configuráveis relacionados a notas fiscais de fornecedor, você pode aplicar o filtro **Tipo de documento comercial**. 

Você pode refinar ainda mais uma pesquisa selecionando o código do país e clicando em **Aplicar filtro**.  

[![Filtrar seção do repositório global](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

O exemplo a seguir mostra os resultados ao filtrar o **Tipo de documento comercial**. 

[![Filtro e importação aplicados para tipo de documento comercial](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Os resultados filtrados podem ser importados para os usuários RCS ou ambiente do Dynamics 365 Finance, individualmente ou como um conjunto (selecionando o grupo de configurações) e clicando em **Importar**.







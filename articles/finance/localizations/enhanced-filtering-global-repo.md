---
title: Filtragem avançada no RCS/Repositório global
description: Este tópico descreve os recursos aprimorados de filtragem para o repositório global RCS, que foram aprimorados para incluir os filtros adicionais.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
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
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440226"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>Opções de filtragem avançada no RCS para encontrar configurações no RCS/Repositório global

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos de filtragem avançada para o repositório global do Regulatory Configuration Services (RCS), que foram aprimorados para incluir a possibilidade de filtrar com os seguintes critérios: 
- **País/região** — com base nos códigos de país ISO  
- Tipos de **marcas** para:
  - Área funcional
  - Área de recursos
  - Indústria 
  - Documento comercial 

Para facilitar a descoberta de configurações específicas ou relacionadas às quais você pode aplicar filtros, individualmente ou em grupo. Por exemplo, para encontrar um único tipo de documento comercial configurável que esteja relacionado a notas fiscais de fornecedor, você pode aplicar um filtro de **Tipo de documento comercial** para procurar esse tipo de documento. 

[![Filtrar seção do repositório global](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

É possível refinar ainda mais a pesquisa selecionando o tipo de documento, por exemplo "fatura de fornecedor" clicando em **Aplicar filtro**. O exemplo a seguir mostra os resultados ao filtrar em **Tipo de documento comercial** co o tipo de documento adicionado. 

[![Filtro e importação aplicados para tipo de documento comercial](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Os resultados filtrados podem ser importados em um repositório do RCS ou em um ambiente do Dynamics 365 Finance dos usuários, individualmente ou como um conjunto. Para fazer isso, selecione o grupo de configurações e clique em **Importar**.

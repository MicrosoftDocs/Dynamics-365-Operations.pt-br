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
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: a67a4345271cbeffc100fc1d9077cc866846a4d4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005833"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
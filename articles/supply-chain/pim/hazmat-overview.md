---
title: Visão geral de materiais perigosos
description: Este tópico fornece uma visão geral dos recursos relacionados ao manuseio e à documentação de materiais perigosos durante o gerenciamento de informações do produto e o gerenciamento de depósito.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 5f8c3dc084f4f260f8cc29b3957913e9bc1b762d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356990"
---
# <a name="hazardous-materials-overview"></a>Visão geral de materiais perigosos

[!include [banner](../includes/banner.md)]

Para permanecer em conformidade com as regulamentações de remessa e transporte, as organizações que enviam materiais que são classificados como mercadorias perigosas devem incluir documentos adicionais com suas remessas. O recurso materiais perigosos permite que os clientes armazenem informações relacionadas aos itens liberados. Essas informações podem ser usadas para ajudar a preparar a documentação de remessa. Uma organização que envia mercadorias perigosas deve ter seus próprios processos e procedimentos para o gerenciamento do processo de remessa. O Microsoft Dynamics 365 Supply Chain Management é a ferramenta que pode ajudar a gerar os documentos necessários.

O diagrama a seguir ilustra as etapas necessárias para configurar e usar o recurso materiais perigosos.

![Configurar e usar o recurso materiais perigosos.](media/hazmat-overview.png "Configurar e usar o recurso materiais perigosos")

O recurso materiais perigosos é configurado no Gerenciamento de informações do produto e fornece documentos que podem ser impressos por meio do Gerenciamento de depósito. Portanto, em geral, essas áreas são as duas principais áreas nas quais você vai revisar, configurar e usar a funcionalidade desse recurso:

- **Gerenciamento de informações do produto** — configure os códigos que serão aplicados a um produto liberado.
- **Gerenciamento de depósito** — trabalhe com documentos de remessa adicionais que serão impressos para remessas.

> [!IMPORTANT]
> Os recursos materiais perigosos no Supply Chain Management fornecem uma coleção de campos úteis de informações de produtos e funcionalidades relacionadas que podem ajudar você a registrar e consultar informações relacionadas aos produtos perigosos. Esses recursos também podem ajudá-lo a criar e imprimir documentos de remessa que incluam algumas das mesmas informações sobre materiais perigosos que você está enviando. No entanto, o sistema não o tornará automaticamente compatível com todos os regulamentos aplicáveis em seu país ou região. Embora essas ferramentas tenham a finalidade de ajudá-lo a cumprir as regulamentações comuns, elas não são suficientes, nem garantidas. Sua organização é responsável por conhecer todas as regulamentações aplicáveis e por executar todas as etapas necessárias para cumpri-las.

## <a name="product-information-management"></a>Gerenciamento de informações do produto

O Gerenciamento de informações do produto fornece uma variedade de tabelas de configuração em que você pode inserir as informações de referência de várias listas de mercadorias perigosas para frete rodoviário, aéreo e marítimo.

As seguintes regulamentações comuns foram usadas como referência quando essa funcionalidade foi desenvolvida:

- **ADR** – regulamentações relacionadas ao transporte internacional de mercadorias perigosas por rodovias
- **CFR 49** – regulamentações nos Estados Unidos para o transporte de mercadorias perigosas
- **IMDG** – o código International Marine Dangerous Goods (Código Marítimo Internacional de Mercadorias Perigosas)
- **IATA** – os regulamentos de mercadorias perigosas da International Air Transport Association (Associação Internacional de Transportes Aéreos)

Cada conjunto de regulamentos fornece listas padronizadas de mercadorias perigosas e códigos de referência. Portanto, o Supply Chain Management fornece uma tabela de referência para os códigos comuns nessas listas. Cada lista tem também alguns códigos exclusivos que você pode definir.

Para obter mais informações sobre como configurar regulamentos e valores para materiais perigosos e como atribuir os valores aos produtos relevantes, consulte os seguintes tópicos:

- [Configurar materiais perigosos](hazmat-setup.md)
- [Materiais perigosos em produtos, ordens, remessas e cargas](hazmat-items.md)

## <a name="warehouse-management"></a>Gerenciamento de depósito

Ao preparar uma remessa no Gerenciamento de depósito, você poderá imprimir vários relatórios novos que usam as informações configuradas no Gerenciamento de informações do produto. Para obter mais informações sobre os relatórios disponíveis e sobre como usá-los, consulte [Consultas e relatórios de materiais perigosos](hazmat-reports.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
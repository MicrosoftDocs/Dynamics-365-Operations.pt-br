---
title: Experimentar unidades de escala em uma topologia híbrida distribuída
description: Este tópico oferece informações sobre como experimentar as unidades de escala de nuvem e de borda para cargas de trabalho de gerenciamento de fabricação e depósito.
author: perlynne
ms.date: 03/03/2022
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-03-03
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 04fd79f3c582ae9ac51882f73410477efaa35496
ms.sourcegitcommit: b52ff5dfd32580121f74a5f262e5c2495e39d578
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376237"
---
# <a name="try-out-scale-units-in-a-distributed-hybrid-topology"></a>Experimentar unidades de escala em uma topologia híbrida distribuída

[!include [banner](../includes/banner.md)]

O processo de experimentar a topologia híbrida distribuída é simples. Durante o primeiro estágio, é necessário validar as personalizações para garantir que funcionem na topologia distribuída. Você tem duas opções.

## <a name="option-1-evaluate-customizations-in-development-environments"></a>Opção 1: avaliar personalizações em ambientes de desenvolvimento

Antes de começar a integrar os ambientes de área restrita, recomendamos explorar unidades de escala em uma configuração de desenvolvimento, como um ambiente de uma caixa (também conhecido como ambiente de 1 camada), para poder validar processos, personalizações e soluções. Durante esse estágio, os dados e as personalizações serão aplicadas a ambientes de uma caixa. Você pode executar em um único ambiente, que pode assumir a função de hub empresarial e unidade de escala. Como alternativa, você pode ter dois ambientes de desenvolvimento, um dos quais tem a função do hub, e o outro que tem a função de uma unidade de escala. Essa configuração oferece a melhor forma de identificar e corrigir problemas. A [compilação de acesso antecipado (PEAP)](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxURUFWTjQzTzg0UUk5RkJHMDFEMVlSSDFEQy4u) mais recente também pode ser usada para concluir esse estágio.

É necessário usar as [ferramentas de implantação da unidade de escala para ambientes de desenvolvimento de uma caixa](https://github.com/microsoft/SCMScaleUnitDevTools) para instalar e manter os ambientes. Essas ferramentas permitem configurar o hub e as unidades de escala em um ou dois ambientes de uma caixa. As ferramentas são fornecidas como uma versão binária e no código-fonte no GitHub. Estude a wiki do projeto, que inclui um [guia de uso passo a passo](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) que descreve como usar as ferramentas. Se você estiver [implantando unidades de escala de borda em hardware personalizado usando dados comerciais locais (LBD)](cloud-edge-edge-scale-units-lbd.md), deverá seguir um processo diferente.

## <a name="option-2-acquire-add-ins-and-deploy-in-your-sandbox-environments"></a>Opção 2: adquirir suplementos e implantar nos ambientes de área restrita

Para testar a topologia híbrida distribuída, é necessário ter dois ambientes de área restrita (nível 2), um dos quais tem seus dados (Hub empresarial), e o outro é destinado para a unidade de escala e tem "dados vazios".

É necessário adquirir suplementos para pelo menos uma unidade de escala de nuvem ou de borda. Os slots de projeto e de ambiente correspondentes serão concedidos nos [Lifecycle Services (LCS) do Microsoft Dynamics](https://lcs.dynamics.com/), de forma que os ambientes da unidade de escala possam ser implantados usando o [Portal do Gerente de Unidade de Escala](https://aka.ms/SCMSUM).

Contate o suporte da Microsoft para solicitar que os ambientes de área restrita sejam habilitados.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Usar novamente configurações de produto
description: Você pode especificar se deseja reutilizar automaticamente uma configuração existente para um produto. Então, quando o usuário concluir uma sessão de configuração, o sistema verifica se já existe uma configuração correspondente às seleções do usuário. Se uma configuração correspondente for encontrada, a ID de configuração, a lista de materiais (BOM) correspondente e o roteiro serão reutilizados.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f72d93600db3d9bf0a44ac1fe84111527bb31d0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209389"
---
# <a name="reuse-product-configurations"></a>Usar novamente configurações de produto

[!include [banner](../includes/banner.md)]

Você pode especificar se deseja reutilizar automaticamente uma configuração existente para um produto. Então, quando o usuário concluir uma sessão de configuração, o sistema verifica se já existe uma configuração correspondente às seleções do usuário. Se uma configuração correspondente for encontrada, a ID de configuração, a lista de materiais (BOM) correspondente e o roteiro serão reutilizados.

<a name="requirements-for-reusing-configurations"></a>Requisitos para reutilizar as configurações
---------------------------------------

Para habilitar as configurações a ser reutilizadas, você deve especificar as seguintes informações para os componentes e atributos na página **Detalhes do modelo de configuração de produto**:

-   **Componentes e subcomponentes** – Na Guia Rápida **Geral**, no campo **Configurações de reutilização**, selecione **Sim**.
-   **Atributos** – Na Guia Rápida **Atributos**, selecione a opção **Incluir reutilização**. Essa opção aparece somente quando o componente relacionado estiver habilitado para reutilização. Se você não selecionar nenhum atributo para reutilização, a configuração sempre será reutilizada, independentemente das seleções do usuário durante uma sessão de configuração. Os valores de atributos da configuração existente devem corresponder às seleções do usuário. Por exemplo, se o usuário selecionar a cor **Azul** durante uma sessão de configuração, o sistema verificará se uma configuração existente do componente tem a cor azul.

## <a name="resetting-configuration-reuse"></a>Redefinir reutilização da configuração
Quando você redefine a reutilização de configuração, as configurações criadas anteriormente são consideradas não. Talvez seja conveniente redefinir a reutilização de configuração se a BOM ou o roteiro foram alterados, mas nenhum atributo relacionada foi alterado. Você redefine a reutilização de configuração **Geral** em FastTab do componente.




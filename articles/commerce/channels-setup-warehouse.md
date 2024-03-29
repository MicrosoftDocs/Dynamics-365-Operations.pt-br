---
title: Configurar um depósito
description: Este artigo descreve como configurar um depósito a ser usado com um novo canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 476f78d7fe1bc61c2c9b783ed1f82bc660248b02
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273630"
---
# <a name="warehouse-set-up"></a>Configuração do depósito

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar um depósito a ser usado com um novo canal no Microsoft Dynamics 365 Commerce.

Cada canal do Commerce requer que um depósito configurado seja associado a ele. Os procedimentos a seguir fornecem a configuração mínima necessária para um depósito de um canal do Commerce. Para obter mais informações sobre configuração de depósitos, consulte a [Visão geral de gerenciamento de depósito](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).

## <a name="configure-a-warehouse-site"></a>Configurar um site de depósito

Antes de configurar um depósito, você precisa configurar um site de depósito.

Para configurar um site de depósito, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de canal \> Sites**.
1. No painel de ação, selecione **Novo**.
1. No campo **Site**, insira um valor.
1. No campo **Nome**, insira um valor.
1. Na seção **Geral**, defina o **Fuso horário** apropriado.
1. Na seção **Endereços**, insira um endereço.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de site de depósito.

![Exemplo de site de depósito.](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a>Configurar um depósito

Para configurar um depósito, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.
1. No painel de ação, selecione **Novo**.
1. No campo **Depósito**, insira um valor.  No caso de um mapeamento 1:1 para uma loja, use o nome da loja ou o nome de um centro de distribuição regional.
1. No campo **Nome**, insira um valor.
1. Na lista suspensa **Site**, selecione o site de depósito criado anteriormente.
1. No campo **Tipo**, selecione **Padrão**.
    - Se você quiser definir um **Depósito de quarentena**, primeiro, precisará seguir estas etapas para criar um depósito adicional no qual o **Tipo** seja definido como **Quarentena**.
    - Se você quiser definir um **Depósito de trânsito**, primeiro, precisará seguir estas etapas para criar um depósito adicional no qual o **Tipo** seja definido como **Trânsito**.
1. No painel de ação, selecione **Salvar**.

## <a name="set-up-inventory-aisles"></a>Configurar corredores do estoque

Para configurar corredores de estoque, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de canal \> Configuração de localização \> Corredores de estoque**.
1. No painel de ação, selecione **Novo**.
1. Na lista suspensa **Depósito**, selecione o depósito criado anteriormente.
1. No campo **Corredor**, insira um nome (por exemplo, "Padr").
1. No campo **Nome**, insira um nome (por exemplo, "Corredor padrão").
1. No painel de ação, selecione **Salvar**.

## <a name="set-up-warehouse-inventory-locations"></a>Configurar localizações de estoque no depósito

Para configurar localizações de estoque no depósito para estoque padrão, danificado e devolvido, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.
1. Selecione o estoque criado anteriormente.
1. No painel de ação, selecione **Editar**.
1. No painel de ação, selecione **Depósito** e, depois, **Localização de estoque**.
1. No painel de ação, selecione **Novo**. A lista suspensa **Depósito** deve usar como padrão o novo depósito.
    1. Na caixa **Corredor**, insira o nome do corredor especificado anteriormente. 
    1. Defina **Atualização manual** como **Sim**
    1. Na caixa **Localização**, insira o nome do depósito.
    1. No painel de ação, selecione **Salvar**.
 1. No painel de ação, selecione **Novo**.  A lista suspensa **Depósito** deve usar como padrão o novo depósito.
    1. Na caixa **Corredor**, insira o nome do corredor especificado anteriormente.  
    1. Defina **Atualização manual** como **Sim**
    1. Na caixa **Localização**, digite "Danificado".
    1. No painel de ação, selecione **Salvar**.
 1. No painel de ação, selecione **Novo**.  A lista suspensa **Depósito** deve usar como padrão o novo depósito.
    1. Na caixa **Corredor**, insira o nome do corredor especificado anteriormente. 
    1. Defina **Atualização manual** como **Sim**
    1. Na caixa **Localização**, digite "Devoluções".
    1. No painel de ação, selecione **Salvar**.
    
A imagem a seguir mostra uma configuração de localização de estoque no depósito de São Francisco.

![Exemplo de configuração de localização no estoque.](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a>Concluir a configuração de depósito

Para concluir a configuração do depósito, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.
1. Selecione o estoque criado anteriormente.
1. No painel de ação, selecione **Editar**.
1. Em **Gerenciamento de estoque e depósito**:
    1. Defina **Local de recebimento padrão** como o local padrão criado acima.
    1. Selecione **Local de saída padrão** como o local padrão criado acima.
1. Na seção **Endereços**, insira o endereço de um depósito.
1. Na seção **Varejo**: 
    1. Na caixa **Localização de devolução padrão**, insira a localização de devoluções criada anteriormente.
    1. Defina **Loja** como **Sim**.
    1. Defina **Peso** como **1,00**. 
    1. Na caixa **Dimensões de Armazenamento**, insira a localização padrão criada anteriormente.
1. Na seção **Depósito**, defina **Estoque físico negativo** como **Sim**.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra detalhes de um depósito configurado.

![Exemplo de depósito configurado.](media/warehouse-sample.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de gerenciamento de depósito](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Configurar um canal de varejo](channel-setup-retail.md)
    
[Configurar um canal online](channel-setup-online.md)

[Configurar um canal de call center](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Modelos de carga
description: Este artigo descreve como configurar modelos de carga e como associar um modelo de carga a uma nova carga.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 47b4925c528b64b835ce3e88659ee6ab0572eb2b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844170"
---
# <a name="load-templates"></a>Modelos de carga

[!include [banner](../../includes/banner.md)]

Ao criar uma carga, você pode atribuir um modelo de carga. O modelo de carga contém informações sobre equipamentos e medidas como altura, largura, profundidade e volume da carga.

Este artigo descreve como configurar modelos de carga e como associar um modelo de carga a uma nova carga.

## <a name="set-up-a-load-template"></a>Configurar um modelo de carga

1. Acesse **Gerenciamento de transporte \> Configuração \> Criação de carga \> Modelo de carga**.
1. No Painel de Ações, selecione **Novo** para adicionar um novo modelo ou **Editar** para editar um modelo existente.
1. Na linha do modelo novo ou existente, defina os seguintes campos:

    - **ID do modelo de carga** – Insira um identificador exclusivo (ID) para o modelo de carga.
    - **Equipamento** – Selecione o equipamento que deve ser usado para remeter a carga.
    - **Altura da carga**, **Largura da carga** e **Profundidade da carga** – Insira as dimensões da carga.
    - **Volume de carga máximo permitido** e **Peso de carga máximo permitido** – Insira o volume e o peso máximo permitido da carga.
    - **Peso bruto máximo permitido** – Insira o peso bruto máximo permitido da carga. O peso bruto de uma carga inclui a tara e o peso de carga.
    - **Número máximo de peças de frete permitido** – Insira o número máximo de peças de frete que a carga pode conter.
    - **Empilhar a carga sobre o piso** – Marque esta caixa de seleção para empilhar a carga sobre o piso. Em um cenário de carga sobre o piso, as caixas são empilhadas do piso ao teto e de parede a parede dentro do contêiner para maximizar a capacidade.

1. No Painel de ações, selecione **Salvar**.

## <a name="associate-a-load-template-with-a-new-load"></a>Associar um modelo de carga a uma nova carga

1. Acesse **Gerenciamento de transporte \> Planejamento \> Bancada de planejamento de carga**.
1. Na parte superior da página, selecione uma das guias a seguir, dependendo do tipo de documento de origem para o qual você está criando uma carga: **Remessas**, **Linhas de venda**, **Linhas de transferência** ou **Linhas de ordem de compra**. 
1. Selecione o documento específico para o qual planejar a carga.
1. No Painel de Ação, na guia **Oferta e demanda** , no grupo **Adicionar** , selecione **Para nova carga**.
1. Na caixa de diálogo **Modelo de carga**, no campo **ID do modelo de carga**, selecione o modelo a ser aplicado.
1. Selecione **OK** para aplicar o modelo.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
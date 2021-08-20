---
title: Perfis de classificação
description: Este tópico descreve como configurar dados para perfis de classificação.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de5789e1b8e36fc52f308967961fe12389628209ff423e26928d1fb15395a08f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772367"
---
# <a name="rating-profiles"></a>Perfis de classificação

Um perfil de classificação se assemelha a um contrato de logística (mas não a um contrato legal). É usado para determinar as tarifas de transporte de cargas. 

Cada perfil de classificação é exclusivo para uma transportadora. No perfil, você associa a transportadora a um mestre de taxa. O mestre de taxa define a atribuição de base da taxa e a base de taxa. A base da taxa determina a taxa da transportadora.

Você pode configurar um perfil de classificação usando uma página genérica que mostra uma visão geral de todos os perfis de classificação existentes. Como alternativa, você pode configurar um perfil de classificação diretamente da transportadora. Em ambos os casos, as informações que você configura para o perfil de classificação são as mesmas.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Criar ou editar um perfil de classificação na página Perfis de classificação

Na página **Perfis de classificação**, você pode revisar todos os perfis de classificação disponíveis. Você também pode editar perfis existentes e criar outros.

1. Acesse **Gerenciamento de transporte \> Configurar \> Classificação \> Perfil de classificação**.
1. No Painel de Ações, selecione **Novo** para adicionar um novo perfil de classificação à grade ou selecione **Editar** para editar um perfil existente.
1. Na linha do perfil de classificação novo ou existente, defina os seguintes campos:

    - **Perfil de classificação** - Insira um identificador (ID) exclusivo para o perfil de classificação.
    - **Nome** – Insira um nome descritivo para o perfil de classificação.
    - **Transportadora** – Selecione uma transportadora. O perfil de classificação que você está configurando também será mostrado na página **Transportadoras** da transportadora selecionada.
    - **Local** e **Depósito** – Selecione um local e depósito.
    - **Mecanismo de taxa** – Selecione o mecanismo de taxa para o perfil de classificação.
    - **Mestre de taxa** – Selecione o mestre de taxa para o perfil de classificação. Você pode usar o modelo de taxa para definir um tipo de base de taxa e uma base de taxa. Para obter mais informações, consulte [Configurar mestres de taxa](set-up-rate-masters.md).
    - **Mecanismo de tempo em trânsito** – Selecione o mecanismo de tempo de trânsito para o perfil de classificação.
    - **Índice de combustível da transportadora** – Selecione o índice de combustível da transportadora para o perfil de classificação.
    - **Data e hora de início de efetivação** e **Data e hora de término de efetivação** – Defina o período em que o perfil de classificação deve estar ativo.

1. No Painel de ações, selecione **Salvar**.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>Criar um perfil de classificação diretamente na página das transportadoras

1. Acesse **Gerenciamento de transporte \> Configurar \> Transportadoras \> Transportadoras**.
1. Selecione uma transportadora na lista.
1. Na FastTab **Perfis de classificação**, selecione **Novo** para criar um perfil de classificação.
1. Defina os campos para o novo perfil de classificação. Esses campos correspondem aos campos da página **Perfis de classificação**, conforme descrito na seção anterior deste tópico.

> [!NOTE]
> Os perfis criados na página **Transportadoras** também são exibidos na página **Perfis de classificação**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
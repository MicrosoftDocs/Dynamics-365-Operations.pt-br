---
title: Garantias em ativos e tipos de ativo
description: Este tópico explica como configurar garantias em ativos e tipos de ativos no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bcfbd56f5fa1491f13ea65c5fb3d70659c3b945276813d7c1c922c849bf8e3a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751161"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garantias em ativos e tipos de ativo

[!include [banner](../../includes/banner.md)]

 


Este tópico explica como configurar garantias em ativos e tipos de ativos no Gerenciamento de Ativos.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Configurar uma garantia em um tipo de ativo

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Tipos de ativo** \> **Tipos de ativo**.
2. No painel à esquerda, selecione o tipo de ativo ao qual deseja anexar o contrato de garantia do fornecedor, e depois selecione **Padrões de tipo de ativo**.
3. Na Guia Rápida **Geral**, no campo **Garantia do fornecedor**, selecione o contrato.

## <a name="set-up-a-warranty-on-an-asset"></a>Configurar uma garantia em um ativo

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos**.
2. Selecione o ativo, e depois **Editar**.
3. Na Guia Rápida **Fornecedor**, na seção **Garantia de fornecedor**, no campo **Garantia**, selecione o contrato de garantia.
4. Nos campos **Data de início de garantia** e **Data de término de garantia**, selecione as datas de início e de término.

    > [!IMPORTANT]
    > Se uma data for selecionada no campo **Início da garantia** em uma ordem de serviço, a garantia se torna válida para a ordem de serviço nessa data. Quando você cria uma ordem de serviço, o campo **Início da garantia** está automaticamente definido para o dia da criação. Entretanto, você pode alterar a data para que ela corresponda a, por exemplo, a data de início de um contrato de garantia.
    >
    > ![Página de ordens de serviço.](media/02-warranty.png)

> [!NOTE]
> Quando você cria uma ordem de serviço para um ativo que está incluído na garantia de um fornecedor, se a ordem de serviço tiver uma data de início esperada durante o período de garantia, você receberá uma notificação sobre o acordo da garantia. Então, você pode cancelar a ordem de serviço, conforme necessário.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
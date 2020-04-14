---
title: Criar provedores de configuração e marcá-los como ativos
description: Este tópico explica como um usuário atribuído à função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um provedor de configuração para relatórios eletrônicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5f238a492dbc3f9318b1bd1d3ea5657e92b33fb
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142100"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Criar provedores de configuração e marcá-los como ativos

[!include [banner](../../includes/banner.md)]

Este tópico explica como um usuário atribuído à função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um provedor de configuração para relatórios eletrônicos (ER). Cada configuração RE será referida ao fornecedor como o autor da configuração. Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.

## <a name="create-a-provider"></a>Criar um fornecedor
1. Vá para o **painel de navegação** no canto superior esquerdo e selecione **Administração da organização**.
2. Vá para **Espaços de trabalho > Relatório eletrônico**.
3. Vá para **Links relacionados > Provedores de configuração**.
4. Selecione **Novo**.
    - Um registro de fornecedor tem nome e URL exclusivos. Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (https://www.litware.com) já existir.  
5. No campo Nome, digite `Litware, Inc.`.
6. No campo Endereço na Internet, digite `https://www.litware.com`.
7. Selecione **Salvar**.
8. Feche a página.

## <a name="select-as-an-active-provider"></a>Selecione como um provedor ativo
1. Selecione o fornecedor "Litware, Inc.".
2. Selecione **Definir como ativo**.

![Página de espaço de trabalho de relatório eletrônico](../media/GER-Task-ActiveProvider-1.png)

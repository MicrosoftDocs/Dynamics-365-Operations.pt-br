---
title: Criar provedores de configuração e marcá-los como ativos
description: Este artigo explica como um usuário atribuído à função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um provedor de configuração.
author: kfend
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
ms.openlocfilehash: db5226720a4e0c0f167921a972429c0a5ecdd2e9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267803"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Criar provedores de configuração e marcá-los como ativos

[!include [banner](../../includes/banner.md)]

Este artigo explica como um usuário atribuído à função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um provedor de configuração para relatórios eletrônicos (ER). Cada configuração RE será referida ao fornecedor como o autor da configuração. Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.

## <a name="create-a-provider"></a>Criar um fornecedor
1. Acesse o **painel de navegação** no canto superior esquerdo e selecione **Administração da organização**.
2. Acesse **Espaços de trabalho > Relatório eletrônico**.
3. Acesse **Links relacionados > Provedores de configuração**.
4. Selecione **Novo**.
    - Um registro de fornecedor tem nome e URL exclusivos. Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (https://www.litware.com) já existir.  
5. No campo Nome, digite `Litware, Inc.`.
6. No campo Endereço na Internet, digite `https://www.litware.com`.
7. Selecione **Salvar**.
8. Feche a página.

## <a name="select-as-an-active-provider"></a>Selecione como um provedor ativo
1. Selecione o fornecedor "Litware, Inc.".
2. Selecione **Definir como ativo**.

![Página de espaço de trabalho de relatório eletrônico.](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

---
title: Configurar categorias de conta principal
description: Este artigo explica como configurar as categorias da conta principal no Dynamics 365 Finance.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c48011c9988bdca694851476540db574efef7909
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879553"
---
# <a name="set-up-main-account-categories"></a>Configurar categorias de conta principal

[!include [banner](../../includes/banner.md)]

Este artigo explica como configurar as categorias da conta principal. Categorias de conta principal são usadas para os relatórios padrão em relatórios financeiros e no Power BI. Categorias de conta principal que são criadas por padrão podem ser renomeadas, mas não excluídas. Categorias de conta adicional podem ser criadas e usadas para fins de relatório e análise. Este artigo usa a empresa de demonstração USMF.

## <a name="create-a-main-account-category"></a>Criar uma categoria de conta principal
1. No painel de navegação, acesse **Módulos > Contabilidade >Plano de contas > Contas > Categorias de conta principal**.
2. Selecione **Novo**.
3. No campo **Categoria de conta principal**, insira um nome exclusivo.
4. No campo **Descrição**, insira uma descrição para a categoria de conta principal.
5. No campo **Tipo de conta principal**, selecione o tipo de conta principal que será vinculado à categoria.

## <a name="link-main-accounts-to-account-category"></a>Vincular a conta principal à categoria de conta principal
1. Clicar em **Vincular contas principais**.
2. Na lista, selecione as contas principais para atribuir à categoria de conta principal marcando as caixas a coluna **Vinculado**. A atribuição de contas principais a uma categoria de conta principal agregará os saldos das contas quando essa categoria é usada para relatórios e análise financeiros.  
3. Marque ou desmarque a opção **Vinculada** para escolher as contas principais.
4. Selecione **OK**.
5. Selecione **Sim**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

---
title: Configurar o Warehouse Management mobile app para unidades de escala de nuvem e borda
description: Este tópico explica como configurar aplicativos móveis do Warehouse Management para depósitos que são servidos por uma unidade de escala de nuvem ou de borda.
author: perlynne
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 1fa00b40db2f6246029876964dca9d3229567848
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071616"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Configurar o Warehouse Management mobile app para unidades de escala de nuvem e borda

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar aplicativos móveis do Warehouse Management para que possam ser usados em depósitos que são servidos por uma unidade de escala de nuvem ou de borda.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar a configurar os dispositivos móveis para se conectar a uma unidade de escala de nuvem ou de borda, confirme se eles podem se conectar ao hub da empresa. Para obter instruções, consulte [Instalar e conectar o aplicativo móvel do Warehouse Management](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>Configuração adicional ao executar o aplicativo móvel do Warehouse Management em uma unidade de escala

Como parte do [processo de implantação de cargas de trabalho da unidade de escala de depósito](cloud-edge-landing-page.md#scale-unit-manager-portal), a maioria dos dados necessários para conectar dispositivos de aplicativo móvel do Warehouse Management são sincronizados automaticamente do hub empresarial para a unidade de escala. No entanto, você deve inserir os dados na página **Aplicativos do Azure Active Directory** (**Administração do sistema \> Configuração \> Aplicativos do Azure Active Directory**) na implantação da unidade de escala. Além disso, talvez você precise atualizar o valor padrão **Empresa** para a ID do usuário ou criar um novo usuário. Os usuários associados a uma empresa que não existem em uma implantação de unidade de escala não poderão fazer logon quando o aplicativo móvel do Warehouse Management estiver conectado a essa unidade de escala.

> [!NOTE]
> Como os dados na página **Aplicativos do Azure Active Directory** não são sincronizados, você deverá manter esses dados manualmente se desejar mover cargas de trabalho de depósito para outra unidade de escala.

Lembre-se de que, como parte da configuração de conexão de cada aplicativo móvel do Warehouse Management, a URL do recurso especificado do Azure Active Directory deve ser para a unidade de escala em vez do hub empresarial.

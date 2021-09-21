---
title: Configurar códigos de motivo
description: O Dynamics 365 Human Resources usa códigos de motivo para explicar por que os benefícios de um funcionário estão mudando.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5f89d6158f351e30376fc3f80c793f29734cdcbb
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431333"
---
# <a name="set-up-reason-codes"></a>Configurar códigos de motivo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O Dynamics 365 Human Resources usa códigos de motivo para explicar por que os benefícios de um funcionário estão mudando.

> [!NOTE]
> A partir de janeiro de 2021, os códigos de motivo foram migrados para o espaço de trabalho **Gerenciamento de pessoal** em vez do espaço de trabalho **Gerenciamento de benefícios**. Para obter mais informações, consulte [Migrar manualmente códigos de motivo para gerenciamento de pessoal](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Criar códigos de motivo

1. No espaço de trabalho **Gerenciamento de pessoal** (ou espaço de trabalho **Gerenciamento de benefícios** se os códigos de motivo não tiverem sido migrados), selecione **Links** e, depois, **Códigos de motivo**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Código de motivo** | Um nome exclusivo para identificar o motivo pelo qual um funcionário alteraria um registro de plano de benefícios. |
   | **Descrição** | Uma descrição do código de motivo. |

4. Em **Cenários aplicáveis**, defina **Gerenciamento de benefícios** como **Sim**. (Não aplicável se os códigos de motivo não tiverem sido migrados para o espaço de trabalho **Gerenciamento de pessoal**.)

5. Selecione **Salvar**.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Migrar manualmente códigos de motivo para Gerenciamento de pessoal

Em janeiro de 2021, os códigos de motivo foram migrados para o espaço de trabalho **Gerenciamento de pessoal** em vez do espaço de trabalho **Gerenciamento de benefícios**. A maioria dos dados de código de motivo migrarão automaticamente no seu ambiente. Alguns dados do código de motivo talvez não migrem. Por exemplo, os códigos de motivo agora têm no máximo 15 caracteres; portanto, qualquer código de motivo com mais de 15 caracteres não migrará automaticamente.

Você verá uma faixa na página **Links** do espaço de trabalho **Gerenciamento de benefícios** informando sobre a migração e se algum código de motivo não foi migrado.

1. Selecione **Códigos de motivo** para obter detalhes sobre o status da migração.

   [![Códigos de motivo.](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Selecione um código de motivo que falhou na migração.

   [![Status da migração do código de motivo.](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Selecione **Migrar código de motivo**.

   [![Migrar código de motivo.](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. No painel **Migração de código de motivo do benefício**, você tem duas opções para mapear um código de motivo de Gerenciamento de pessoal:

   - Para usar um código de motivo existente em Gerenciamento de pessoal, escolha um no menu suspenso **Usar código de motivo existente**.
     > [!NOTE]
     > Só será possível usar um código de motivo existente no Gerenciamento de pessoal se outro código de motivo de Gerenciamento de benefícios ainda não tiver migrado para ele.
   - Para criar um novo código de motivo no Gerenciamento de pessoal, insira um novo em **Novo código de motivo** e, depois, insira uma descrição em **Nova descrição**.

   [![Mapear para um código de motivo de Gerenciamento de pessoal.](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

Depois que os códigos de motivo migram para o Gerenciamento de pessoal, a opção para usá-los no Gerenciamento de benefícios é definida automaticamente como **Sim**.

[![Usar código de motivo em Gerenciamento de benefícios.](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

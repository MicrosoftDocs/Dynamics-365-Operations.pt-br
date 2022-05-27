---
title: Configurar o Autoatendimento para funcionários
description: No Microsoft Dynamics 365 Human Resources, você pode configurar blocos para navegação de alto nível no autoatendimento para funcionários.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7ddb1f1ea74a16265dac701151b2c25a4f9d4dc
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687153"
---
# <a name="configure-employee-self-service"></a>Configurar autoatendimento para funcionários


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

No Microsoft Dynamics 365 Human Resources, você pode configurar blocos para navegação de alto nível no **Autoatendimento para funcionários**. Os blocos do plano de benefícios direcionam os usuários a planos de benefícios para os quais eles são qualificados.

## <a name="set-up-a-benefit-plans-tile"></a>Configurar um bloco de planos de benefícios

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.

2. Selecione a guia **Configuração do bloco de planos de benefícios** e depois **Novo**.

3. Especifique valores para os seguintes campos.

   | Campo | Descrição |
   | --- | --- |
   | **Código do tipo de plano** | O tipo de plano que é exibido quando este bloco é selecionado em **Autoatendimento de benefícios**. |
   | **ID do bloco** | O identificador exclusivo para o bloco. |
   | **Texto de rótulo de bloco** | O texto que aparecerá para o bloco no **Autoatendimento de benefícios**. |
   | **Descrição** | Uma descrição do bloco. |
   | **Imagem de plano de fundo de bloco** | A URL da imagem a ser usada para o bloco (opcional). |
   | **Rastrear o registro aberto** | Selecione esta opção para rastrear o progresso do registro aberto para este tipo de plano. Por exemplo, você pode ter planos criados em que **Tipo de plano = Outro**. Esses planos podem ser planos opcionais para os quais você não deseja rastrear o andamento do registro. Se você não selecionar esse tipo de plano, ele será ignorado ao rastrear o progresso ou a conclusão do registro na guia **Registro aberto**. Essa configuração se aplica ao tipo de plano selecionado para todos os períodos e entidades legais. |

4. Selecione **Salvar**.

## <a name="set-up-a-flex-credit-plan-tile"></a>Configurar um bloco de plano de crédito flexível

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.

2. Selecione a guia **Configuração do bloco de plano de crédito flexível** e depois **Novo**.

3. Especifique valores para os seguintes campos.

   | Campo | Descrição |
   | --- | --- |
   | **ID do crédito do benefício** | Os planos do programa de crédito flexível que serão exibidos quando este bloco for selecionado em **Autoatendimento de benefícios**. |
   | **ID do bloco** | O identificador exclusivo para o bloco. |
   | **Texto de rótulo de bloco** | O texto que aparecerá para o bloco no **Autoatendimento de benefícios**. |
   | **Descrição** | Uma descrição do bloco. |
   | **Imagem de plano de fundo de bloco** | A URL da imagem a ser usada para o bloco (opcional). |
   | **Rastrear o registro aberto** | Selecione esta opção para rastrear o progresso do registro aberto para este tipo de plano. Por exemplo, você pode ter planos criados em que **Tipo de plano = Outro**. Esses planos podem ser planos opcionais para os quais você não deseja rastrear o andamento do registro. Se você não selecionar esse tipo de plano, ele será ignorado ao rastrear o progresso ou a conclusão do registro na guia **Registro aberto**. Essa configuração se aplica ao tipo de plano selecionado para todos os períodos e entidades legais. |

4. Selecione **Salvar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

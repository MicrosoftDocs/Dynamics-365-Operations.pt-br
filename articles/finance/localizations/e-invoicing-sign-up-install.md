---
title: Inscrever-se e instalar o serviço de Faturamento Eletrônico
description: Este artigo fornece informações sobre como se inscrever e instalar o serviço de faturamento eletrônico.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 99f484e5ab8821c78fde776a9d3195dade2a09d5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283947"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>Inscrever-se e instalar o serviço de Faturamento Eletrônico

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre como se inscrever e instalar o serviço de faturamento eletrônico. Este processo tem quatro etapas. As etapas 1 a 3 são necessárias e a etapa 4 é opcional.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>Etapa 1: inscreva-se no Regulatory Configuration Service

O Regulatory Configuration Service (RCS) fornece a experiência em configuração e design necessária para configurar o faturamento eletrônico. Recursos como ambientes e recursos de faturamento eletrônico são criados, mantidos e gerenciados no RCS. Quando os recursos estão prontos, eles são publicados no serviço de Faturamento eletrônico.

Para obter mais informações sobre RCS, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).

Para se inscrever no RCS, vá para a página [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>Etapa 2: instale o suplemento para microsserviços no Microsoft Dynamics Lifecycle Services

O serviço de Faturamento eletrônico é um conjunto de microsserviços hospedados nos datacenters da Microsoft. Por padrão, os clientes do Dynamics 365 Finance e do Dynamics 365 Supply Chain Management não têm acesso ao serviço de faturamento eletrônico. Você deve instalá-lo como um suplemento no Microsoft Dynamics Lifecycle Services (LCS). Quando você instala o suplemento, seu ambiente do Finance ou Supply Chain Management é inserido no registro de aplicativos que têm permissão para se conectar ao serviço de Faturamento eletrônico.

Para concluir esta etapa, consulte [Instalar o suplemento para microsserviços no Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>Etapa 3: configure o RCS

É necessário configurar a integração entre o RCS e o serviço de Faturamento eletrônico. Você também deve configurar os componentes principais.

Para concluir esta etapa, consulte [Configurar o RCS (Regulatory Configuration Service)](e-invoicing-set-up-rcs.md).

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>Etapa 4: referência do administrador do plug-in do Microsoft Power Platform

Alguns cenários exigem integração com o Dataverse no escopo do Microsoft Power Platform.

No momento, essa configuração é obrigatória se você usar soluções de Faturamento eletrônico para cenários de faturamento eletrônico indonésios. No entanto, é opcional para cenários de faturamento eletrônico da Arábia Saudita. Para obter mais informações, consulte [Disponibilidade de recursos de Faturamento eletrônico por país ou região](e-invoicing-country-specific-availability.md).

Para concluir esta etapa, consulte [Referência ao Microsoft Power Platform](e-invoicing-power-platform-plug-in.md) de administrador de plug-in.

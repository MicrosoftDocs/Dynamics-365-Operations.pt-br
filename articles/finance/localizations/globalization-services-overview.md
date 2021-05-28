---
title: Serviços de globalização do Dynamics 365
description: Este tópico oferece uma visão geral de serviços de globalização do Microsoft Dynamics 365.
author: JaneA07
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2ef942f7f6dac2c321a51800ade0bf25f2162304
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018798"
---
# <a name="dynamics-365-globalization-services"></a>Serviços de globalização do Dynamics 365

[!include [banner](../includes/banner.md)]

Os seguintes serviços de globalização podem ser configurados para estender os recursos existentes em alguns serviços do Microsoft Dynamics 365 Online:

- O **Regulatory Configuration Service (RCS)** oferece suporte à configuração de diferentes tipos de documentos eletrônicos e relatórios. O RCS fornece uma versão aprimorada do designer de Relatório Eletrônico (ER) em que o repositório de configuração é um serviço autônomo. Para obter mais informações, consulte [Regulatory Configuration Service](rcs-overview.md).
- O **faturamento eletrônico** reúne formatos configuráveis para transformações, assinaturas digitais e integrações configuráveis para a conectividade com serviços Web externos, incluindo a certificação e o tratamento de respostas. Para obter mais informações, consulte [Faturamento Eletrônico](e-invoicing-service-overview.md).
- O **Cálculo de Imposto** oferece maior flexibilidade, dando suporte a várias IDs de imposto, determinação de código de imposto, designer de cálculo de imposto e um mecanismo de tempo de execução para atender a regulamentações de impostos complexas no mundo inteiro. Para obter mais informações, consulte [Cálculo de Imposto](global-tax-calcuation-service-overview.md).

Esses serviços de globalização fornecem integração imediata com os serviços online do Dynamics 365 a seguir.

| Serviço online | SCR | Faturamento Eletrônico | Cálculo de Imposto (Versão preliminar) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | Sim | Sim | Sim | 
| Dynamics 365 Supply Chain Management | Sim | Sim | Sim | 
| Dynamics 365 Project Operations | Sim | Sim | Não Aplicável | 
| Dynamics 365 Commerce | Sim | Não Aplicável | Não Aplicável | 

> [!NOTE]
> Devido a diferenças na disponibilidade das localizações geográficas do Azure (áreas geográficas) para RCS, a configuração desse serviço pode fazer com que dados do cliente sejam transferidos para fora da área geográfica selecionada para o serviço online do Dynamics 365 aplicável. Para obter mais informações, consulte [Dynamics 365 e Power Platform: disponibilidade, local de dados, idioma e localização](https://aka.ms/rcs/D365Productavailabilityguide).
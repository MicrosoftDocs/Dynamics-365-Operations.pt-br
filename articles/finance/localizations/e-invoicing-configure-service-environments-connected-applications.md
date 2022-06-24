---
title: Configurar ambientes de serviço e aplicativos conectados
description: Este artigo fornece informações sobre como configurar os ambientes de serviço e os aplicativos conectados.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c1bb3f784148f04c01223ac4e280a18bacfe0e51
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853212"
---
# <a name="configure-service-environments-and-connected-applications"></a>Configurar ambientes de serviço e aplicativos conectados

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre como configurar os ambientes de serviço e os aplicativos conectados. Este processo tem três etapas. A etapa 1 é obrigatória, e as etapas 2 e 3 são opcionais.

## <a name="step-1-create-a-service-environment"></a>Etapa 1: criar um ambiente de serviço

Ao criar o ambiente de serviço, defina a lista de usuários que podem implantar recursos de globalização. Opcionalmente, para alguns dos cenários, defina a lista de aplicativos externos que podem se comunicar com o serviço de faturamento eletrônico. Configure sequências numéricas se forem usadas em seus cenários.

Para concluir esta etapa, consulte [Ambientes de serviço](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>Etapa 2: adicionar certificados e segredos

Adicione uma referência ao cofre de chaves do Microsoft Azure e aos segredos para usá-los em seus cenários. Esta etapa será obrigatória se as ações nos pipelines de processamento usarem certificados e segredos para a assinatura digital ou a comunicação com serviços Web externos.

Para concluir esta etapa, consulte [Certificados e segredos do cliente](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>Etapa 3: configurar aplicativos conectados

Para configurar a comunicação entre aplicativos do Dynamics 365 Finance ou Dynamics 365 Supply Chain Management e o faturamento eletrônico, você deve configurar o gerenciamento de Finance ou Supply Chain Management para construir a chamada ao serviço de faturamento eletrônico e preparar os dados de negócios em uma estrutura unificada que pode ser transformada no formato eletrônico necessário. Os aplicativos também devem processar corretamente as respostas do serviço. Você pode concluir essa configuração diretamente no seu ambiente do Finance ou Supply Chain Management environment ou pode concluí-la no Regulatory Configuration Service (RCS). Se você concluir a configuração no RCS, poderá implantá-la no seu ambiente do Finance ou Supply Chain Management. Nesta etapa, você registrará o aplicativo conectado para a implantação de parâmetros.

Para concluir esta etapa, consulte [Aplicativos conectados](e-invoicing-connected-applications.md).

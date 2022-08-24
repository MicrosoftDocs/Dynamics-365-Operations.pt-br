---
title: Configurar o faturamento eletrônico
description: Este artigo fornece uma visão geral do processo para preparar e configurar o faturamento eletrônico.
author: gionoder
ms.date: 02/28/2022
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
ms.openlocfilehash: de94843c1e98a8788375bd41def587a64baea07d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272169"
---
# <a name="electronic-invoicing-setup"></a>Configurar o faturamento eletrônico

[!include [banner](../includes/banner.md)]

O artigo fornece uma visão geral do processo para preparar e configurar o faturamento eletrônico. Você deve concluir as etapas de configuração na ordem especificada aqui. Se uma etapa for obrigatória, mas você a ignorar, o recurso não funcionará corretamente e várias falhas ocorrerão durante as etapas subsequentes ou quando você usar o recurso. 

Antes de começar, verifique se todos os componentes principais estão configurados corretamente, se você se inscreveu no Regulatory Configuration Service (RCS) e tem uma instância do RCS e se o suplemento de faturamento eletrônico está instalado no ambiente do Microsoft Dynamics 365 Finance ou do Dynamics 365 Supply Chain Management. Para obter mais informações, consulte [Inscrição e instalação do Faturamento eletrônico](e-invoicing-install-add-in-microservices-lcs.md).

Em seguida, configure os recursos do Azure que o faturamento eletrônico requer para realizar seu trabalho. Para obter mais informações, consulte [Configurar recursos do Azure para faturamento eletrônico](e-invoicing-set-up-azure-resources.md).

Depois que os componentes principais estiverem configurados, trabalhe com RCS para configurar os principais componentes lógicos do faturamento eletrônico. Primeiro, defina o número de ambientes de serviço que serão mantidos. Dessa forma, você define os dados lógicos e o particionamento de configuração para garantir que você tenha um limite entre um ambiente de desenvolvimento ou de teste e os ambientes de produção. Para configurar seu processo de desenvolvimento de forma flexível, você pode exigir vários ambientes separados de desenvolvimento e teste. Além de definir os ambientes de serviço, defina um link para os aplicativos comerciais, como Finance ou Supply Chain Management, diretamente do RCS, para configurar os parâmetros necessários à operação correta com o faturamento eletrônico. Para obter mais informações sobre os ambientes, consulte [Ambientes de serviço](e-invoicing-service-environments.md).

Depois que tudo estiver configurado, você pode criar seus próprios recursos de globalização que definem diferentes cenários para o processamento de documentos eletrônicos e transformação de dados, ou para a importação de documentos do repositório global. Para obter mais informações sobre como trabalhar com Recursos de globalização, consulte [Trabalhar com Recursos de globalização](e-invoicing-working-globalization-features.md).

Se os seus cenários exigem integração com email ou O SharePoint para processar documentos eletrônicos de entrada, consulte [Processa documentos eletrônicos de entrada](e-invoicing-process-incoming-electronic-documents.md) para obter informações sobre como configurar e usar esses canais.

---
title: Solucionar problemas relacionados ao reconhecimento da solução
description: Este tópico fornece informações sobre como solucionar problemas que são relacionados ao reconhecimento da solução.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: aa5ba0cfb127f20012237774fe948c23731eb56f8680d9fa23309e189683dbf3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736341"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Solucionar problemas relacionados ao reconhecimento da solução

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas que são relacionados ao reconhecimento da solução.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="error-on-the-dual-write-page"></a>Erro na página de gravação dupla

Na página **Gravação dupla**, você pode receber uma mensagem de erro parecida com o seguinte exemplo:

*A entidade com um nome "msdyn\_dualwriteentitymap" with namemapping="Logical" não foi encontrada no MetadataCache.*

Para corrigir o problema, verifique se a solução principal de gravação dupla está instalada no Dataverse. A solução principal de gravação dupla é um pré-requisito para o reconhecimento da solução.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
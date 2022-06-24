---
title: Solucionar problemas relacionados ao reconhecimento da solução
description: Este artigo fornece informações sobre como solucionar problemas que são relacionados ao reconhecimento da solução.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c280eef995664c640e382817dda9d6e1cde154c6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871485"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Solucionar problemas relacionados ao reconhecimento da solução

[!include [banner](../../includes/banner.md)]





Este artigo fornece informações de solução de problemas para a integração de gravação dupla entre aplicativos de finanças e operações e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas que são relacionados ao reconhecimento da solução.

> [!IMPORTANT]
> Alguns dos problemas que este artigo aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="error-on-the-dual-write-page"></a>Erro na página de gravação dupla

Na página **Gravação dupla**, você pode receber uma mensagem de erro parecida com o seguinte exemplo:

*A entidade com um nome "msdyn\_dualwriteentitymap" with namemapping="Logical" não foi encontrada no MetadataCache.*

Para corrigir o problema, verifique se a solução principal de gravação dupla está instalada no Dataverse. A solução principal de gravação dupla é um pré-requisito para o reconhecimento da solução.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
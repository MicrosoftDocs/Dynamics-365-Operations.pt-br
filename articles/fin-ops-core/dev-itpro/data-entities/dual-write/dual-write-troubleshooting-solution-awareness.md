---
title: Solucionar problemas relacionados ao reconhecimento da solução
description: Este artigo fornece informações sobre como solucionar problemas que são relacionados ao reconhecimento da solução.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c70287cb8ec29fb622f3aefff971b884339e4205
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289414"
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

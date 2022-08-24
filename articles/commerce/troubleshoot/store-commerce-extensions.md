---
title: Solucionar problemas de extensão do Store Commerce
description: Este artigo explica como solucionar problemas de extensão no aplicativo do Store Commerce do Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1a2d6a68b7556d8b4d05529efd90f9e66f0c5925
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269772"
---
# <a name="troubleshoot-store-commerce-extension-issues"></a>Solucionar problemas de extensão do Store Commerce

[!include [banner](../includes/banner.md)]

Este artigo explica como solucionar problemas de extensão no aplicativo do Store Commerce do Microsoft Dynamics 365 Commerce.

## <a name="extensions-packages-arent-loaded"></a>Os pacotes de extensões não são carregados

### <a name="extensions-packages-dont-appear-on-the-pos--settings-page"></a>Os pacotes de extensões não aparecem na página \> Configurações do PDV

Os gatilhos do Commerce Runtime (CRT) talvez não tenham sido atualizados para incluir o pacote de extensão ou não foram implantados. Para obter mais informações, consulte [Extensibilidade e gatilhos do Commerce runtime (CRT)](../dev-itpro/commerce-runtime-extensibility-trigger.md).

### <a name="extensions-packages-appear-on-the-pos--settings-page-but-the-manifest-isnt-loaded"></a>Os pacotes de extensões são exibidos na página Configurações do PDV \>, mas o manifesto não está carregado

Confirme se os pacotes de extensões existem na pasta **C:\\Arquivos de Programas\\Microsoft Dynamics 365\\10.0\\Store Commerce\\Extensões**. Se os pacotes existirem, deve haver uma pasta **PDV** que contém o manifesto.

Se não houver nenhuma pasta **PDV**, confirme se o projeto do Store Commerce referencia corretamente o projeto de extensão do ponto de venda (PDV). Valide o caminho de referência do projeto e verifique se ele existe. 

Na ilustração do exemplo a seguir, o projeto do instalador está tendo problemas com o projeto de extensão referenciado.

![A referência do projeto do instalador do Store Commerce não é válida.](media/ReferenceNotValid.png)

Se a referência para o projeto de extensão for adicionada corretamente, não haverá qualquer problema de aviso ou de dependência no projeto do instalador, conforme mostrado na ilustração de exemplo a seguir.

![A referência do projeto do instalador do Store Commerce não é válida.](media/ReferenceValid.png)

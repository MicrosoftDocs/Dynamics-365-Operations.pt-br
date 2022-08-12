---
title: Solucionar problemas de configuração e instalação do Store Commerce
description: Este artigo explica como solucionar problemas de configuração e instalação no aplicativo do Store Commerce do Microsoft Dynamics 365 Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 8af2c476ced05fc159a53131f8b51ad914a6c7c3
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2022
ms.locfileid: "9168938"
---
# <a name="troubleshoot-store-commerce-setup-and-installation-issues"></a>Solucionar problemas de configuração e instalação do Store Commerce

[!include [banner](../includes/banner.md)]

Este artigo explica como solucionar problemas de configuração e instalação no aplicativo do Store Commerce do Microsoft Dynamics 365 Commerce.

## <a name="i-cant-activate-the-app-and-i-receive-a-connectivity-error-message"></a>Não consigo ativar o aplicativo e recebo uma mensagem de erro de conectividade

Depois de inserir a URL válida de Ponto de Venda (CPOS) da Nuvem, você pode receber uma mensagem de erro de conectividade semelhante ao seguinte exemplo:

> Ocorreu um erro de conectividade e seu dispositivo não pode se conectar ao CPOS. A URL do CPOS digitada pode ter alguns problemas.

Nesse caso, revise a URL em busca de erros tipográficos ou determine se o CPOS não pode ser alcançado porque está offline.

Além disso, verifique se a versão de Cloud Scale Unit (CSU) é 10.0.25 (9.35.\*.\*) ou mais recente. A versão de CPOS 10.0.25 ou posterior é necessária para usar o aplicativo Store Commerce.

## <a name="i-cant-install-the-app-because-modern-pos-is-already-installed"></a>Não consigo instalar o aplicativo porque o Store Commerce já está instalado

Durante a instalação, talvez você receba uma mensagem de erro, como a do seguinte exemplo:

> Uma versão (9.\*.\*.\*) deste produto (Modern POS) foi instalada anteriormente por meio do instalador herdado.

Para corrigir o erro, você deve desinstalar o aplicativo Modern Point of Sale (MPOS) para todos os usuários na máquina e, em seguida, tentar novamente. Você pode confirmar se o MPOS foi removido de todos os usuários, executando o seguinte comando do PowerShell.

```PowerShell
Get-AppxPackage | Where-Object {$_.PackageFullName -like "Microsoft.Dynamics.*.Pos"} | Remove-AppxPackage -Allusers
```

## <a name="i-cant-activate-the-app-because-of-an-invalid-url-or-an-error-state"></a>Não consigo ativar o aplicativo por causa de uma URL inválida ou um estado de erro

Se a URL de CPOS inserida não for válida e você quiser alterá-la, ou se o aplicativo Store Commerce estiver em um estado de erro durante a ativação, você poderá reiniciar o processo redefinindo o aplicativo. O aplicativo Store Commerce salvará somente uma URL de CPOS válida.

Para redefinir o aplicativo Store Commerce, siga estas etapas.

1. No menu **Iniciar** do Windows, selecione e mantenha pressionado (ou clique com o botão direito do mouse) o aplicativo e selecione **Mais \> Configurações do aplicativo**.
2. Role para baixo na página configurações do aplicativo até encontrar o botão **Redefinir**.
3. Selecione **Redefinir**. Depois, quando solicitado, confirme se você deseja redefinir o aplicativo.

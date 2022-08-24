---
title: Instalar o tema da Adventure Works
description: Este artigo descreve como instalar o tema Adventure Works no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: f5c195694633c96a473f0f824c1f182903082bff
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274277"
---
# <a name="install-the-adventure-works-theme"></a>Instalar o tema da Adventure Works

[!include [banner](includes/banner.md)]

Este artigo descreve como instalar o tema Adventure Works no Microsoft Dynamics 365 Commerce. 

> [!IMPORTANT]
> O tema Adventure Works e os módulos estão disponíveis a partir da versão 10.0.20 do Dynamics 365 Commerce. Eles estão disponíveis no Microsoft AppSource.

## <a name="prerequisites"></a>Pré-requisitos

Antes de instalar o tema Adventure Works, é necessário ter um ambiente do Dynamics 365 Commerce (Commerce versão 10.0.20 ou posterior) que inclui o Retail Cloud Scale Unit (RCSU), o kit de desenvolvimento de software (SDK) online para o Commerce e a biblioteca de módulos do Commerce. Para obter informações sobre como instalar o SDK e a biblioteca de módulos do Commerce, consulte [Configurar um ambiente de desenvolvimento](e-commerce-extensibility/setup-dev-environment.md). 

## <a name="installation-steps"></a>Etapas de instalação

### <a name="install-the-adventure-works-theme-in-your-application"></a>Instalar o tema Adventure Works em seu aplicativo

O pacote de temas Adventure Works está disponível no feed **dynamics365-commerce**, como **@msdyn365-commerce-theme/adventureworks-theme-kit**. No entanto, embora o pacote de tema Adventure Works faça parte desse feed, ele está em um namespace diferente. Portanto, é necessário seguir estas etapas para adicionar entradas do registro ao namespace.

1. Atualize o arquivo **.npmrc** para que ele inclua a seguinte entrada de registro (se a entrada não estiver incluída):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Atualize o arquivo **.yarnrc** para que ele inclua a seguinte entrada de registro (se a entrada não estiver incluída):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Para instalar o pacote no seu ambiente local, execute o comando `yarn add THEME_PACKAGE@VERSION` no prompt de comando, em que **THEME_PACKAGE** é o pacote de tema (@msdyn365-commerce-theme/adventureworks-theme-kit) e **VERSION** é o número de versão da biblioteca de módulos que está sendo usada. É importante que as versões do pacote de tema e da biblioteca de módulos sejam correspondentes. Para encontrar o número de versão correto da biblioteca de módulos a ser usada, abra o arquivo package.json e localize o valor **starter-pack** na seção **dependências**. No exemplo a seguir, o arquivo package.json usa a versão 9.32 da biblioteca de módulos que é mapeada para a versão 10.0.22 do Dynamics 365 Commerce.  

```json
"dependencies": {
    "@msdyn365-commerce-modules/starter-pack": "9.32",
}
```

O exemplo a seguir mostra como executar o comando `yarn add` para adicionar a versão 9.32 do tema Adventure Works. O comando atualiza automaticamente o arquivo package.json de forma que inclua a dependência.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit@9.32`

Para obter mais informações sobre como atualizar a versão da biblioteca de módulos, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md). 

> [!IMPORTANT]
> - A versão do tema deve corresponder à versão da biblioteca do módulo para garantir que todos os recursos funcionem conforme o esperado. 
> - A versão mínima para o SDK e a biblioteca de módulos do Commerce deve ser 10.0.20 (9.31). 

### <a name="add-the-font-files-for-the-adventure-works-theme"></a>Adicionar os arquivos de fonte para o tema Adventure Works

Depois que o tema Adventure Works estiver instalado em seu aplicativo, será necessário adicionar os arquivos de fonte necessários para ele. Para concluir esta etapa, copie todos os arquivos de fonte em **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\public\webfonts** para o caminho do diretório público do aplicativo do parceiro **\public\webfonts**.

### <a name="set-up-the-resources-for-the-adventure-works-theme"></a>Configurar os recursos para o tema Adventure Works

A próxima etapa é atualizar o recurso padrão necessário para o tema. Para concluir esta etapa, copie o conteúdo do arquivo global.json em **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\resources\modules** para o arquivo global.json do aplicativo do parceiro em **\src\resources\modules**. Se o diretório de destino **\src\resources** não existir, ele poderá ser copiado completamente do diretório de origem **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks** para o diretório de destino **\src**.

### <a name="pull-updates-and-validate-the-theme"></a>Receber atualizações e validar o tema

Para obter informações sobre como receber o SDK, a biblioteca de módulos e outras atualizações de dependência mais recentes, consulte a seção "Receber atualizações" de [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#pull-updates).

Depois que as dependências mais recentes forem removidas, você pode executar o comando **yarn start** para iniciar o servidor Node no seu ambiente de desenvolvimento e testar o novo tema Adventure Works. Navegue no aplicativo localmente usando o parâmetro da cadeia de caracteres de consulta `?theme=adventureworks` (por exemplo, `https://localhost:4000/?theme=adventureworks`).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do tema Adventure Works](adventure-works-theme.md)

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

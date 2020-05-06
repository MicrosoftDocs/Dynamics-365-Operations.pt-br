---
title: Introdução ao serviço de contabilidade de custos
description: Este tópico oferece detalhes de licenciamento e instruções de instalação do serviço de contabilidade de custos.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276888"
---
# <a name="get-started-with-the-cost-accounting-service"></a>Introdução ao serviço de contabilidade de custos

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> A funcionalidade que é descrita neste tópico está disponível como parte de uma versão prévia particular. O conteúdo deste tópico e a funcionalidade nele descrita estão sujeitos a alterações. Para obter informações sobre as versões prévias, consulte [Perguntas frequentes sobre as atualizações de serviço One Version](../../fin-ops-core/fin-ops/get-started/one-version.md).

O serviço de contabilidade de custos permite realizar múltiplas contabilidades de estoque nos razões de contabilização de custos configurados. Associe cada razão de contabilização de custos a uma *convenção*. Uma convenção é uma coleção dos seguintes tipos de políticas de contabilidade:

- Objeto de custo
- Base de medida de entrada
- Pressuposição de fluxo de custos
- Elemento de custo

> [!NOTE]
> Mesmo depois de ativar o serviço de contabilização de custos, ainda é possível realizar a contabilidade de estoque no Microsoft Dynamics 365 Supply Chain Management, como de costume.

O serviço de contabilização de serviço é um complemento. Para disponibilizar os recursos, é necessário instalá-los a partir do Lifecycle Services (LCS) Microsoft Dynamics. Portanto, é possível optar por avaliá-lo em um ambiente de teste antes de ativá-lo em ambientes de produção.

O serviço de contabilidade de custos atualmente não oferece suporte a todos os recursos de gerenciamento integrados ao Dynamics 365 Supply Chain Management. Portanto, é importante que você avalie se o conjunto de recursos disponível no momento atenderá aos seus requisitos.

## <a name="licensing"></a>Licenciamento

O serviço de contabilidade de custos é licenciado com os recursos padrão de contabilidade de estoque que estão disponíveis para o Supply Chain Management. Não é necessário comprar uma licença adicional para usar o serviço de contabilidade de custos.

## <a name="install-the-add-in"></a>Instalar o suplemento

> [!IMPORTANT]
> Para usar o serviço de contabilidade de custos, é necessário ter um ambiente de alta disponibilidade habilitado para LCS (não um ambiente OneBox) com o Dynamics 365 Supply Chain Management versão 10.0.11 ou posterior.

Para usar o serviço de contabilidade de custos, instale o complemento do serviço de contabilidade de custos para o Supply Chain Management conforme descrito no procedimento a seguir.

1. Entre no LCS.

1. Vá para **Gerenciamento da versão prévia do recurso**.

1. Selecione o sinal de mais (**+**).

1. No campo **Código**, insira a chave beta do complemento do serviço de contabilidade de custos. (Você deve ter recebido a chave por email.)

1. Selecione **Desbloquear**.

1. Abra o ambiente LCS ao qual deseja adicionar o serviço.

1. Vá para **Detalhes completos**.

1. Role para baixo até a FastTab **Suplementos de ambiente**.

1. Selecione **Instalar um novo suplemento**.

1. Selecione **Serviço de contabilidade de custos**.

1. Acompanhe o guia de instalação e concorde com os termos e condições.

1. Selecione **Instalar**.

1. Na FastTab **Complementos do ambiente**, você verá que o serviço de contabilidade de custos está sendo instalado. Após alguns minutos, o status deve mudar de **Instalando** para **Instalado**. (Talvez seja necessário atualizar a página para ver essa alteração.) Nesse momento, o serviço de contabilidade de custos já está pronto para uso.

## <a name="set-up-the-integration"></a>Configurar a integração

Para configurar a integração entre o serviço de contabilidade de serviços e o Dynamics 365 Supply Chain Management:

1. Vá para **Administração do sistema > Gerenciamento de Recursos**.

1. Selecione **Verificar se há atualizações**.

1. Abra a guia **Todos** e procure o recurso chamado de *Serviço de contabilidade de custos*.

1. Selecione **Habilitar agora**.

1. Vá para **Gerenciamento de custos > Serviço de contabilidade de custos > Configuração > Parâmetros do serviço de contabilidade de custos > Parâmetros de integrações**.

1. No campo **ID do aplicativo**, insira o seguinte código:<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. No campo **Ponto de extremidade do serviço de dados**, insira a seguinte URL:<br>https://operationsdataservice.operations365.dynamics.com/

1. No campo **Ponto de extremidade do serviço de contabilidade de custos**, insira a seguinte URL:<br>https://costaccountingservice.operations365.dynamics.com/

1. Agora o serviço de contabilidade de custos está pronto para uso.

## <a name="related-resources"></a>Recursos relacionados

[Home page do serviço de contabilidade de custos](cost-accounting-service-home.md)

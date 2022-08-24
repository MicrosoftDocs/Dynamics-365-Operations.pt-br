---
title: Usando os portais do Microsoft Power Apps com o modelo de dados de participantes
description: Este artigo descreve as alterações nas funções Web para os portais do Microsoft Power Apps devido ao modelo de dados do participante em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: 8d7a6ae48834ddd5f06f73bfe3129e44d14d86b8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288976"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>Usando os portais do Microsoft Power Apps com o modelo de dados de participantes

[!INCLUDE[banner](../../includes/banner.md)]



A versão 2.0.999.0 da solução de orquestração de aplicativos de gravação dupla e posterior inclui alterações no modelo de dados para o participante e para o catálogo de endereços global das tabelas Conta e Contato. As alterações permitem relacionamentos muitos para muitos que oferecem suporte a cenários comerciais avançados. Essas alterações não são compatíveis com as funções Web do portal, incluindo o portal do cliente, que são enviadas prontas ou que já estavam no seu ambiente antes de instalar a gravação dupla. Para que as funções Web funcionem conforme o esperado, é necessário criar funções Web usando o novo modelo de dados. 

Em resumo, a forma como as tabelas interagem mudou, mas as permissões de tabela no portal do cliente não mudaram. Este artigo explica como criar funções Web que funcionam com o novo modelo de dados avançado.

Este diagrama mostra a relação da tabela **sem** o modelo de dados do catálogo de endereços global e do participante:

   ![sem o modelo do participante.](media/without-party-model.PNG)

Este diagrama mostra a relação da tabela **com** o modelo de dados do catálogo de endereços global e do participante:

   ![com o modelo do participante.](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Criar uma permissão de tabela

Para criar essas permissões de tabela, siga estas etapas:

1. Entre em [Power Apps](https://make.powerapps.com) e acesse seus aplicativos.
2. Selecione o aplicativo de gerenciamento de portal.
3. Na barra lateral, selecione **Segurança > Permissões de tabela**.

    Você deve criar três permissões:

    + Conexão de tabela de **Contato** e **Participante**
    + Conexão de tabela de **Participante** e **Conta**
    + Conexão de tabela de **Conta** e **Ordem**

4. Crie e salve uma permissão para a conexão de Contato com Participante, definindo estes parâmetros:

    + **Nome**: conexão de tabela de **Participante** e **Conta** (ou o que você escolher)
    + **Nome da tabela**: msdyn_contactforparty
    + **Site**: Portal do cliente
    + **Escopo**: contato
    + **Privilégios**: selecionar tudo
    + **Funções Web**: usuários autenticados, representante do cliente (ou o que você escolher)

5. Crie e salve uma permissão para a conexão de Participante com Conta, definindo estes parâmetros:

    + **Nome**: conexão de Participante com Conta (ou o que você escolher)
    + **Nome da tabela**: conta
    + **Site**: Portal do cliente
    + **Escopo**: responsável
    + **Privilégios**: selecionar tudo
    + **Permissão da tabela principal**: conexão de Participante e Contato

6. Crie e salve uma permissão para a conexão de Conta com Pedido, definindo estes parâmetros:

    + **Nome**: conexão de Conta e Pedido (ou o que você escolher)
    + **Nome da tabela**: salesorder
    + **Site**: Portal do cliente
    + **Escopo**: responsável
    + **Privilégios**: selecionar tudo
    + **Permissão da tabela principal**: conexão de Participante e Conta

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

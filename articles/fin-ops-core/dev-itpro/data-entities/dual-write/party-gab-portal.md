---
title: Usar o Power Portal com o modelo de dados do participante
description: Este tópico descreve as alterações nas funções Web do Power Portal devido ao modelo de dados do participante em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833081"
---
# <a name="using-power-portal-with-the-party-data-model"></a>Usar o Power Portal com o modelo de dados do participante

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

A versão 2.0.999.0 da solução de orquestração de aplicativos de gravação dupla e posterior inclui alterações no modelo de dados para o participante e para o catálogo de endereços global das tabelas Conta e Contato. As alterações permitem relacionamentos muitos para muitos que oferecem suporte a cenários comerciais avançados. Essas alterações não são compatíveis com as funções Web do portal, incluindo o portal do cliente, que são enviadas prontas ou que já estavam no seu ambiente antes de instalar a gravação dupla. Para que as funções Web funcionem conforme o esperado, você precisa criar funções Web usando o novo modelo de dados. 

Em resumo, a forma como as tabelas interagem mudou, mas as permissões de tabela no portal do cliente não mudaram. Este tópico explica como criar funções Web que funcionam com o novo modelo de dados avançado.

Este diagrama mostra a relação da tabela **sem** o modelo de dados do catálogo de endereços global e do participante:

   ![sem o modelo do participante](media/without-party-model.PNG)

Este diagrama mostra a relação da tabela **com** o modelo de dados do catálogo de endereços global e do participante:

   ![com o modelo do participante](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Criar uma permissão de tabela

Para criar essas permissões de tabela, siga estas etapas:

1. Entre em [Power Apps](https://make.powerapps.com) e acesse seus aplicativos.
2. Selecione o aplicativo de gerenciamento de portal.
3. Na barra lateral, selecione **Segurança > Permissões de tabela**.

    Você deve criar três permissões:

    + Conexão de Contato com Participante
    + Conexão de Participante com Conta
    + Conexão de Conta com Pedido

4. Crie e salve uma permissão para a conexão de Contato com Participante, definindo estes parâmetros:

    + **Nome**: conexão de Participante com Conta (ou o que você escolher)
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

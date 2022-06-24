---
title: Configurar o RCS (Regulatory Configuration Service)
description: Este artigo explica como configurar o Regulatory Configuration Service (RCS).
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 085d430cbd03df9a950b8b8d5fd80f7557a03301
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893972"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>Configurar o RCS (Regulatory Configuration Service)

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar o Regulatory Configuration Service (RCS).

## <a name="turn-on-globalization-features"></a>Ativar os Recursos de globalização

1. Entre em sua conta do RCS.
2. Selecione o bloco **Gerenciamento de recursos**.
3. No espaço de trabalho **Gerenciamento de recursos** , selecione **Recursos de globalização** na lista e, em seguida, selecione **Habilitar agora**.

Um bloco para o espaço de trabalho **Recursos de globalização** agora deve aparecer no painel principal do RCS.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Configure os parâmetros da integração do RCS com o Faturamento eletrônico

1. No espaço de trabalho **Recursos de globalização**, na seção **Configurações relacionadas**, selecione **Parâmetros de relatório eletrônico**.
2. Na guia **Faturamento eletrônico**, no campo **URI de ponto de extremidade de serviço**, digite o ponto de extremidade de serviço apropriado para sua geografia do Microsoft Azure, conforme mostrado na tabela a seguir.

    | Geografia do data center Azure | URI do ponto de extremidade do serviço |
    |----------------------------|----------------------|
    | Estados Unidos              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Reino Unido             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Ásia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japão                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Suíça                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasil                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Emirados Árabes Unidos       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Austrália                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canadá                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | França                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Índia                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Verifique se o campo **ID do Aplicativo** está definido como **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Esse valor é um valor fixo. Verifique se apenas um GUID (identificador global exclusivo) foi inserido e se o valor não inclui nenhum outro símbolo, como espaços, vírgulas, pontos ou aspas.
4. No campo **ID de Ambiente do LCS**, insira a ID do ambiente do Microsoft Dynamics Lifecycle Services (LCS). Esse valor é a referência ao ambiente do Finance ou Supply Chain Management que será usado com o serviço de faturamento eletrônico. Para obter sua ID, faça login no [LCS](https://lcs.dynamics.com/), abra seu projeto e, em seguida, na guia **Gerenciar ambiente**, na seção **Detalhes do ambiente**, examine o campo **ID do ambiente**.

    > [!IMPORTANT]
    > Se o suplemento de Faturamento eletrônico estiver instalado em vários ambientes do Finance ou Supply Chain Management no LCS, sempre use a ID de ambiente do ambiente mais recentemente instalado. Se você decidir instalar o suplemento em um novo ambiente depois de configurar e trabalhar com a funcionalidade de faturamento eletrônica, atualize o campo **ID de ambiente do LCS** no RCS para o valor mais recente.

5. Selecione **Salvar** e feche a página.

## <a name="configuration-providers"></a>Provedores de configuração

Você pode usar os provedores de configuração para distinguir os proprietários das configurações de Relatório eletrônico (ER) que são usados em processos de faturamento eletrônico e os recursos de globalização de proprietários. Para todos os recursos de globalização fornecidos pela Microsoft e publicados no repositório global, o provedor de configuração é definido como **Microsoft** (`http://microsoft.com`).

Você pode ajustar somente configurações de ER e recursos de globalização que pertencem ao provedor de configuração ativo. Você pode usar essas configurações e recursos como modelos para criar configurações e recursos que pertencem ao provedor de configuração ativo, para que você possa ajustá-los.

Primeiro, crie os provedores de configuração. Em seguida, defina um deles como ativo. Não é possível definir o provedor de configuração **Microsoft** como ativo.

### <a name="create-a-configuration-provider"></a>Criar um provedor de configuração

1. No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Provedores de configuração**.
2. Selecione **Novo**.
3. No campo **Nome**, insira um nome exclusivo para o provedor de configuração.
4. No campo **Endereço de Internet**, insira o URL exclusivo do provedor de configuração.
5. Selecione **Salvar** e feche a página.

### <a name="select-a-configuration-provider-as-active"></a>Selecione um provedor de configuração como ativo

1. Na lista de provedores de configuração, selecione o provedor de configuração que deseja definir como ativo.
2. Selecione **Definir como ativo**.

## <a name="import-er-configurations-from-the-global-repository"></a>Importar configurações de ER do repositório global

1. No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Provedores de configuração**.
2. Na lista de provedores de configuração, selecione **Microsoft** e depois selecione **Repositórios**.
3. Selecione **Global** e então, no Painel de Ações, selecione **Abrir**.
4. Importe os seguintes modelos de ER:

    - **Modelo de contexto de fatura de cliente**
    - **Modelo de fatura**
    - **Documentos fiscais** (para cenários brasileiros, se necessário)
    - **Modelo de mensagem de resposta**

5. Se **Mapeamento de modelo de fatura** não tiver sido importado automaticamente, importe-o.
6. Feche a página.

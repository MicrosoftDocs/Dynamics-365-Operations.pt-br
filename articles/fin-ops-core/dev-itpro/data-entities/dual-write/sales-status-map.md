---
title: Configurar o mapeamento dos campos de status da ordem de venda
description: Este tópico explica como configurar os campos de status da ordem de venda para a gravação dupla.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4449729"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a>Configurar o mapeamento dos campos de status da ordem de venda

[!include [banner](../../includes/banner.md)]

Os campos que indicam o status da ordem de venda têm diferentes valores de enumeração no Microsoft Dynamics 365 Supply Chain Management e no Dynamics 365 Sales. Uma configuração adicional é necessária para mapear esses campos em gravação dupla.

## <a name="fields-in-supply-chain-management"></a>Campos no Supply Chain Management

No Supply Chain Management, dois campos refletem o status da ordem de venda. Os campos que você deve mapear são **Status** e **Status do Documento**.

A enumeração **Status** especifica o status geral da ordem. Esse status é mostrado no cabeçalho da ordem.

A enumeração **Status** tem os seguintes valores:

- Ordem em Aberto
- Entregues
- Faturadas
- Cancelado

A enumeração **Status do Documento** especifica o documento mais recente que foi gerado para a ordem. Por exemplo, se a ordem for confirmada, este documento será uma confirmação de ordem de venda. Se uma ordem de venda for parcialmente faturada e a linha restante for confirmada, o status do documento permanecerá como **Fatura**, pois a fatura será gerada posteriormente no processo.

A enumeração **Status do Documento** tem os seguintes valores:

- Confirmação
- Lista de Separação
- Guia de remessa
- Fatura

## <a name="fields-in-sales"></a>Campos em Vendas

Em Vendas, dois campos indicam o status da ordem. Os campos que você deve mapear são **Status** e **Status de Processamento**.

A enumeração **Status** especifica o status geral da ordem. Tem os seguintes valores:

- Ativos
- Envio feito
- Atendidos
- Faturadas
- Cancelado

A enumeração **Status de Processamento** foi introduzida para que o status possa ser mapeado mais precisamente com o Supply Chain Management.

A tabela a seguir mostra o mapeamento do **Status de Processamento** no Supply Chain Management.

| Status do processamento   | Status no Supply Chain Management | Status do Documento no Supply Chain Management |
|---------------------|-----------------------------------|--------------------------------------------|
| Ativos              | Ordem em Aberto                        | Nenhuma                                       |
| Confirmada           | Ordem em Aberto                        | Confirmação                               |
| Separada              | Ordem em Aberto                        | Lista de Separação                               |
| Parcialmente entregue | Ordem em Aberto                        | Guia de remessa                               |
| Entregues           | Entregues                         | Guia de remessa                               |
| Parcialmente faturada  | Entregues                         | Fatura                                    |
| Faturadas            | Faturadas                          | Fatura                                    |
| Cancelado           | Cancelado                         | Não Aplicável                             |

A tabela a seguir mostra o mapeamento do **Status de Processamento** entre Vendas e o Supply Chain Management.

| Status do processamento   | Status em Vendas | Status no Supply Chain Management |
|---------------------|-----------------|-----------------------------------|
| Ativos              | Ativos          | Ordem em Aberto                        |
| Confirmada           | Envio feito       | Ordem em Aberto                        |
| Separada              | Envio feito       | Ordem em Aberto                        |
| Parcialmente entregue | Ativos          | Ordem em Aberto                        |
| Parcialmente faturada  | Ativos          | Ordem em Aberto                        |
| Parcialmente faturada  | Atendidos       | Entregues                         |
| Faturadas            | Faturadas        | Faturadas                          |
| Cancelado           | Cancelado       | Cancelado                         |

## <a name="setup"></a>Configurar

Para configurar o mapeamento dos campos de status da ordem de venda, você deve habilitar os atributos **IsSOPIntegrationEnabled** e **isIntegrationUser**.

Para habilitar o atributo **IsSOPIntegrationEnabled**, siga estas etapas.

1. Em um navegador, vá para `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`. Substitua **\<test-name\>** pelo link da sua empresa para Vendas.
2. Na página que está aberta, localize **organizationid** e anote o valor.

    ![Localizando organizationid](media/sales-map-orgid.png)

3. Em Vendas, abra o console do navegador e execute o seguinte script. Use o valor **organizationid** da etapa 2.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Código JavaScript no console do navegador](media/sales-map-script.png)

4. Verifique se **IsSOPIntegrationEnabled** está definido como **true**. Use a URL da etapa 1 para verificar o valor.

    ![IsSOPIntegrationEnabled está definido como true](media/sales-map-integration-enabled.png)

Para habilitar o atributo **isIntegrationUser**, siga estas etapas.

1. Em Vendas, vá para **Configuração \> Personalização \> Personalizar o Sistema**, selecione **Entidade do usuário** e abra **Formulário \> Usuário**.

    ![Abrindo o formulário do usuário](media/sales-map-user.png)

2. No Explorador do Campo, localize o **modo de usuário integração** e clique duas vezes nele para adicioná-lo ao formulário. Salve sua alteração.

    ![Adicionando o campo modo de usuário de integração ao formulário](media/sales-map-field-explorer.png)

3. Em Vendas, vá para **Configuração \> Segurança \> Usuários** e altere a exibição de **Usuários Habilitados** para **Usuários do Aplicativo**.

    ![Alterando a exibição de Usuários Habilitados para Usuários de Aplicativos](media/sales-map-enabled-users.png)

4. Selecione as duas entradas para **DualWrite IntegrationUser**.

    ![Lista de usuários do aplicativo](media/sales-map-user-mode.png)

5. Altere o valor do campo **Modo de usuário de integração** como **Sim**.

    ![Alterar o valor do campo Modo de usuário de integração](media/sales-map-user-mode-yes.png)

Suas ordens de venda agora estão mapeadas.

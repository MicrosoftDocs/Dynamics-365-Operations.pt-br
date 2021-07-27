---
title: Cálculo de Imposto (Versão preliminar)
description: Este tópico explica o escopo geral e os recursos do recurso Cálculo de Imposto.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bab6e0e0ea1b9fb7f598e37843b52e3ba9c7f94e
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6336623"
---
# <a name="tax-calculation-preview"></a>Cálculo de Imposto (Versão preliminar)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

O Cálculo de Imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto. O mecanismo de cálculo de imposto é totalmente configurável. Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto. O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.

O Cálculo de Imposto é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management. Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.

> [!IMPORTANT]
> Ao habilitar o serviço de cálculo de imposto, algumas operações em dados relacionados podem ser executadas em um data center diferente do data center que mantém os dados do serviço. Revise os [Termos e Condições](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) antes de habilitar o serviço de cálculo de imposto. Sua privacidade é importante para nós. Para saber mais, leia nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=521839).

O Cálculo de Imposto é um mecanismo de cálculo de imposto baseado em microsserviço que oferece escalabilidade exponencial. Ele pode ajudar você a executar as seguintes tarefas:

- Configure o Cálculo de Imposto com o Regulatory Configuration Service (RCS). O RCS é uma versão aprimorada do designer do Relatório eletrônico (ER) e está disponível como serviço autônomo.
- Configure a matriz de impostos para determinar os códigos e as taxas de impostos automaticamente.
- Configure a matriz de impostos para determinar o número de registro do imposto.
- Configure o designer de cálculo de imposto para definir fórmulas e condições.
- Compartilhe a determinação e solução de cálculo de imposto nas entidades legais.

Para usar o serviço de cálculo de imposto, instale o suplemento do serviço de cálculo de imposto do projeto no Microsoft Dynamics Lifecycle Services (LCS). Em seguida, conclua a configuração no RCS e habilite o serviço de cálculo de imposto no Finance e no Supply Chain Management. Para obter mais informações, consulte [Introdução ao serviço de imposto](./global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilidade

O Cálculo de Imposto está disponível somente em ambientes de área restrita e para alguns clientes, por meio de um programa de versão preliminar pública. Futuramente, ele será disponibilizado de modo geral para todos os clientes e em ambientes de produção.

Novos recursos continuarão a ser entregues; portanto, verifique a documentação mais recente para saber mais sobre a cobertura e o escopo dos recursos compatíveis.

O Cálculo de Imposto é implantado nas regiões do Azure a seguir. Ele também será implantado em mais regiões do Azure, de acordo com as necessidades dos clientes:

- Estados Unidos
- Europa

> [!NOTE]
> O Cálculo de Imposto não é compatível com implantações locais do Dynamics 365. Ele também não oferece suporte a versões anteriores, como o Dynamics AX 2012.

## <a name="feature-highlights"></a>Destaques do recurso

- Uma matriz de impostos configurável para determinar e calcular impostos automaticamente
- Suporte para vários números de registro de imposto
- Suporte para ordem de transferência de determinação e cálculo de imposto
- Suporte para ordem de transferência para a determinação de vários números de registro de imposto

## <a name="supported-transactions"></a>Transações com suporte

O Cálculo de Imposto pode ser habilitado por entidade legal e transação. As seguintes transações são compatíveis:

- Processo de Vendas

    - Cotação de Venda
    - Ordem de Venda
    - Confirmação
    - Lista de Separação
    - Guia de Remessa
    - Fatura de venda
    - Nota de Crédito
    - Ordem de retorno
    - Encargos diversos do cabeçalho
    - Encargos diversos da linha

- Processo de compra

    - Ordem de Compra
    - Confirmação
    - Lista de Recebimentos
    - Recebimento de produtos
    - Fatura de compra
    - Encargos diversos do cabeçalho
    - Encargos diversos da linha
    - Nota de Crédito
    - Ordem de retorno
    - Requisição de Compra
    - Encargos diversos da linha de requisição de compra
    - Solicitação de cotação
    - Encargos diversos do cabeçalho da solicitação de cotação
    - Encargos diversos da linha da solicitação de cotação

- Processo de estoque

    - Ordem de transferência – enviar
    - Ordem de transferência – receber

## <a name="related-resources"></a>Recursos relacionados

[Introdução ao serviço de imposto](./global-get-started-with-tax-calculation-service.md)

[Vários números de registro de IVA](./emea-multiple-vat-registration-numbers.md)

[Suporte ao recurso de imposto para a ordem de transferência](./tasks/tax-feature-support-for-transfer-order.md)

[Como criar uma extensão no serviço de imposto](./tax-service-add-data-fields-tax-integration-by-extension.md)

---
title: Visão geral do Cálculo de Imposto
description: Este tópico explica o escopo geral e os recursos do recurso Cálculo de Imposto.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 72895cc18368ebf38818f30510cec999391c7910
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394577"
---
# <a name="tax-calculation-overview"></a>Visão geral do Cálculo de Imposto

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

O Cálculo de Imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto. O mecanismo de cálculo de imposto é totalmente configurável. Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto. O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.

O Cálculo de Imposto é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management. Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.

> [!IMPORTANT]
> Ao habilitar o Cálculo de Imposto, algumas operações em dados relacionados podem ser executadas em um data center diferente do data center que mantém os dados do serviço. Revise os [Termos e Condições](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) antes de habilitar o Cálculo de Imposto. Sua privacidade é importante para nós. Para saber mais, leia nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=521839).

O Cálculo de Imposto é um mecanismo de imposto baseado em microsserviço que oferece escalabilidade exponencial e pode ajudá-lo a executar as seguintes tarefas:

- Determinar automaticamente o grupo de impostos sobre vendas, o grupo de impostos sobre vendas do item e os códigos de imposto corretos por meio de um mecanismo de determinação aprimorado.
- Suportar vários números de registro de imposto em uma entidade legal e determine automaticamente o número de registro de imposto correto em transações tributáveis.
- Dar suporte a determinação, cálculo, lançamento e liquidação de impostos para ordens de transferência.
- Definir fórmulas e condições de cálculo de imposto configuráveis para suas necessidades comerciais específicas.
- Compartilhar a determinação de imposto e a solução de cálculo em entidades legais para economizar esforços de manutenção e evitar erros.
- Dar suporte à determinação de número de registro de imposto do cliente e do fornecedor.
- Suportar a determinação de código de lista.
- Dar suporte a parâmetros de cálculo de imposto no nível da jurisdição de impostos.

Para usar o Cálculo de Imposto, instale o suplemento de Cálculo de Imposto do projeto no Microsoft Dynamics Lifecycle Services. Em seguida, conclua a configuração no [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) e habilite o Cálculo de Imposto no Finance and Supply Chain Management. Para obter mais informações, consulte [Introdução ao serviço de imposto](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilidade

O Cálculo de Imposto está geralmente disponível em ambientes de produção para todos os clientes a partir da versão 10.0.21.

Novos recursos continuarão sendo entregues. Verifique frequentemente o plano de versão mais atualizado para aprender sobre a cobertura e o escopo dos recursos com suporte.

O Cálculo de Imposto é implantado nas regiões do Azure a seguir. Mais regiões do Azure serão adicionadas, de acordo com as necessidades dos clientes.

- Pacífico Asiático
- Austrália
- Canadá
- Europa
- Japão
- Reino Unido
- Estados Unidos

> [!NOTE]
> O Cálculo de Imposto não oferece suporte à versões anteriores do Dynamics 365, como Dynamics AX 2012 ou implantações locais do Dynamics 365.

## <a name="data-flow"></a>Fluxo de dados

Aqui está uma descrição do processo de fluxo de dados para o Cálculo de Imposto. 

1. No RCS, exiba e importe configurações de modelo de documento tributável e configurações de mapeamento de modelos. Se você deve estender as configurações para um cenário avançado, consulte [Adicionar campos de dados em configurações de imposto](tax-service-add-data-fields-tax-configurations.md).
2. No RCS, crie ou mantenha os recursos de imposto. Você pode usar os recursos de imposto para manter taxas de imposto e regras de aplicabilidade de imposto.
3. Depois que a configuração do recurso de imposto for concluída, publique as configurações de imposto e os recursos de imposto do RCS para o repositório Global.
4. No Finance, selecione a versão de configuração do recurso de imposto a ser usada para uma entidade legal específica.
5. No Finance and Supply Chain Management, opere as transações como de costume. Quando o Cálculo de Imposto é necessário, o cliente coleta informações da transação, como a ordem de venda ou a ordem de compra, e empacota as informações como conteúdo. Uma solicitação será enviada para calcular o imposto.
6. A solicitação de cálculo de imposto é recebida do cliente e o cálculo é concluído. O resultado do imposto será devolvido para o cliente.
7. O cliente do Dynamics 365 recebe o resultado do imposto e apresenta o resultado do cálculo de imposto em uma página de imposto.

## <a name="supported-transactions"></a>Transações com suporte

O Cálculo de Imposto pode ser habilitado por transações. 

As seguintes transações são compatíveis na versão 10.0.21: 

- Vendas

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

- Compra

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

- Inventário

    - Ordem de transferência – enviar
    - Ordem de transferência – receber

## <a name="supported-countriesregions"></a>Países/regiões com suporte

O Cálculo de Imposto pode ser habilitado por entidade legal. 

Os seguintes países/regiões do endereço principal de uma entidade legal têm suporte na versão 10.0.21:

- Áustria
- Bélgica
- Dinamarca
- Estônia
- Finlândia
- França
- Alemanha
- Hungria
- Islândia
- Itália
- Letônia
- Lituânia
- Países Baixos
- Noruega
- Polônia
- Suécia
- Suíça
- Reino Unido
- Estados Unidos

## <a name="related-resources"></a>Recursos relacionados

[Introdução ao serviço de imposto](./global-get-started-with-tax-calculation-service.md)

[Vários números de registro de IVA](./emea-multiple-vat-registration-numbers.md)

[Suporte ao recurso de imposto para a ordem de transferência](./tasks/tax-feature-support-for-transfer-order.md)

[Como criar uma extensão no serviço de imposto](./tax-service-add-data-fields-tax-integration-by-extension.md)

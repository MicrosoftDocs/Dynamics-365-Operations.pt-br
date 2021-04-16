---
title: Serviço de cálculo de imposto (Versão preliminar)
description: Este tópico explica o escopo geral e os recursos do serviço de cálculo de imposto.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818215"
---
# <a name="tax-calculation-service-preview"></a>Serviço de cálculo de imposto (Versão preliminar)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

O serviço de cálculo de imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto. O mecanismo de cálculo de imposto é totalmente configurável. Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto. O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.

O serviço de cálculo de imposto é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management. Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.

O serviço de cálculo de imposto é um mecanismo de cálculo de imposto baseado na Microsoft que oferece escalabilidade exponencial. Ele pode ajudar você a executar as seguintes tarefas:

- Configure o serviço de cálculo de imposto com o Regulatory Configuration Service (RCS). O RCS é uma versão aprimorada do designer do Relatório eletrônico (ER) e está disponível como serviço autônomo.
- Configure a matriz de impostos para determinar os códigos e as taxas de impostos automaticamente.
- Configure a matriz de impostos para determinar o número de registro do imposto.
- Configure o designer de cálculo de imposto para definir fórmulas e condições.
- Compartilhe a determinação e solução de cálculo de imposto nas entidades legais.

Para usar o serviço de cálculo de imposto, instale o suplemento do serviço de cálculo de imposto do projeto no Microsoft Dynamics Lifecycle Services (LCS). Em seguida, conclua a configuração no RCS e habilite o serviço de cálculo de imposto no Finance e no Supply Chain Management. Para obter mais informações, consulte [Introdução ao serviço de imposto](https://go.microsoft.com/fwlink/?linkid=2138482).

## <a name="availability"></a>Disponibilidade

O serviço de cálculo de imposto está disponível somente em ambientes de área restrita e para alguns clientes, por meio de um programa de versão preliminar pública. Futuramente, ele será disponibilizado de modo geral para todos os clientes e em ambientes de produção.

Novos recursos continuarão sendo entregues no serviço de cálculo de imposto. Portanto, verifique a documentação mais recente para saber mais sobre a cobertura e o escopo dos recursos compatíveis.

O serviço de cálculo de imposto é implantado nas seguintes regiões do Azure. Ele também será implantado em mais regiões do Azure, de acordo com as necessidades dos clientes:

- Estados Unidos
- Europa
- França
- Reino Unido

> [!NOTE]
> O serviço de cálculo de imposto não é compatível com implantações locais do Dynamics 365. Ele também não oferece suporte a versões anteriores, como o Dynamics AX 2012.

## <a name="feature-highlights"></a>Destaques do recurso

- Uma matriz de impostos configurável para determinar e calcular impostos automaticamente
- Suporte para vários números de registro de imposto sobre valor agregado (IVA)
- Suporte para ordem de transferência de determinação e cálculo de imposto
- Suporte para ordem de transferência para a determinação de vários números de registro de IVA

## <a name="supported-transactions"></a>Transações com suporte

O serviço de cálculo de imposto pode ser habilitado por entidade legal e transação. As seguintes transações são compatíveis:

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

[Introdução ao serviço de imposto](https://go.microsoft.com/fwlink/?linkid=2138482)

[Vários números de registro de IVA](https://go.microsoft.com/fwlink/?linkid=2153387)

[Suporte ao recurso de imposto para a ordem de transferência](https://go.microsoft.com/fwlink/?linkid=2153388)

[Como criar uma extensão no serviço de imposto](https://go.microsoft.com/fwlink/?linkid=2138483)

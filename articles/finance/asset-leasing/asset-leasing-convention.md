---
title: Convenções de arrendamento de ativos
description: Este tópico descreve convenções ativos arrendados.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 67c4d2b7162cf6bda2eedfecef43ff0b216e6e6c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881799"
---
# <a name="asset-leasing-conventions"></a>Convenções de arrendamento de ativos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve convenções ativos arrendados. As convenções de arrendamento são usadas para determinar a data de início de um registro de arrendamento. Se a convenção de arrendamento estiver definida como **Nenhum**, a data de início será a mesma que a data inicial do arrendamento (ou seja, o valor do campo **Data de início do arrendamento**). Se a convenção de arrendamento for definida como **Mês completo**, a data de início será o primeiro dia do mês em que a data inicial do arrendamento cairá.

A data de início determina a data inicial do período para as agendas de amortização de passivos e depreciação de ativos. Despesas de juros e despesas de depreciação são lançadas na data de término do período das agendas correspondentes. A entrada de diário de reconhecimento e ajuste inicial é lançada na data de início.

> [!NOTE]
> O recurso de convenções de arrendamento precisa ser ativado por meio do Gerenciamento de Recursos. No espaço de trabalho **Gerenciamento de recursos**, localize e selecione o recurso denominado **Convenção de arrendamento para arrendamento de ativos** e selecione **Habilitar agora**.

As convenções de arrendamento são atribuídas à configuração de um registro de ativos de arrendamento.

Para exibir ou atribuir a convenção de arrendamento, siga estas etapas.

1. Acesse **Arrendamento de ativo \> Configuração \> Registros de arrendamento**.
2. No campo **Convenção de arrendamento**, selecione um dos valores a seguir.

    | Convenção de arrendamento | descrição |
    |--------------------|-------------|
    | Nenhuma               | As agendas de amortização de responsabilidade e de depreciação de ativos começam na data de início da concessão porque a data de início equivale à data de início do arrendamento. A data final é um mês depois. Essa convenção de arrendamento não garante que os juros serão lançados no último dia de cada mês. |
    | Mês inteiro         | Para arrendamentos com uma data de início que ocorre a qualquer momento do mês, as agendas de amortização de passivos e depreciação de ativos começam a acumular despesas no primeiro dia do mês. Essa convenção de arrendamento garante que os juros sejam acumulados no último dia de cada mês para o mês inteiro. |

3. Selecione **Salvar**.

Quando um arrendamento é criado, a data de início de cada registro é inserida automaticamente com base na data inicial inserida para o arrendamento e a convenção de arrendamento especificada para o registro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

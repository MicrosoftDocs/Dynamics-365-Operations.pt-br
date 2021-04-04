---
title: Configurar registros de arrendamento
description: Este tópico descreve as informações que são mantidas em registros de arrendamento. Os registros de arrendamento contêm as políticas contábeis que determinam como um arrendamento é contabilizado no sistema.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f5eac47448835dae5837b31c59a72833652f63bf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249644"
---
# <a name="set-up-lease-books"></a>Configurar registros de arrendamento

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Os registros de arrendamento contêm as políticas contábeis que determinam como um arrendamento é contabilizado no sistema. Além da contabilidade base do caixa, o Arrendamento de ativo oferece suporte aos seguintes padrões:

- Princípios Contábeis Geralmente Aceitos nos Estados Unidos (US GAAP)
- Tópico 842 da Codificação de Padrões Contábeis (ASC 842)
- ASC 840
- Padrão Internacional de Relatórios Financeiros 16 (IFRS 16)
- Padrão Internacional Contábil 17 (IAS 17)

Para criar um registro de arrendamento, siga estas etapas.

1. Acesse **Arrendamento de ativo \> Configuração \> Registros de arrendamento**.
2. Selecione **Novo** para adicionar um registro.
3. Defina os campos a seguir.

    | Organização                                     | descrição |
    |------------------------------------------|-------------|
    | Nível de lançamento                            | Selecione o nível de lançamento a ser usado. Cada registro anexado a um arrendamento é configurado para um nível de lançamento específico. Cada nível de lançamento tem finalidades de lançamento diferentes. |
    | Tipo de arrendamento                               | Selecione se o arrendamento deve ser classificado automaticamente ou se deve ser predefinido como um Arrendamento mercantil ou operacional. |
    | Estrutura contábil                     | Selecione a estrutura associada ao registro. |
    | Configuração de Prazo do arrendamento/Vida útil          | O sistema classificará o arrendamento como mercantil se o tipo de arrendamento tiver sido definido como **Automático** e se o prazo de arrendamento sobre a vida útil do ativo for maior ou igual ao percentual inserido nesse campo.  |
    | Configuração de Valor presente/Valor justo do ativo   | Insira um número inteiro para definir o limite que determinará o tipo de arrendamento. Se o valor presente de pagamentos de arrendamento mínimos futuros for maior do que o valor definido pelo usuário na configuração do registro e se a classificação de arrendamento do registro estiver definida como automático, o sistema classificará o arrendamento como um arrendamento mercantil. |
    | Limite de curto prazo                     | Digite o número de meses a ser usado como limite para arrendamentos de curto prazo. Se o prazo do arrendamento for menor ou igual ao número de meses inseridos aqui, o sistema classificará a concessão como um arrendamento de curto prazo e o tratamento do arrendamento diferido será aplicado. |
    | Limite de valor baixo                      | Insira um valor a ser usado como limite para arrendamentos de baixo valor. Se o valor justo do ativo for menor ou igual ao valor inserido aqui, o sistema classificará o arrendamento como um arrendamento de baixo valor, e o tratamento do arrendamento diferido será aplicado. |
    | Pagar ao fornecedor                            | Defina essa opção como **Sim** para permitir que os pagamentos de arrendamento sejam lançados, como uma fatura, na conta de fornecedor especificada em cada arrendamento. Quando um pagamento de arrendamento for lançado, a conta do fornecedor será creditada. Se essa opção for definida como **Não**, a conta especificada para o tipo de lançamento de **Pagamento de arrendamento** na página **Parâmetros de lançamento de arrendamento** será creditada. |
    | Convenção de arrendamento                       | Selecione a convenção para a data de início do arrendamento:<ul><li><b>Nenhum</b> – Use a data inicial do arrendamento como a data de início.</li><li><b>Mês inteiro</b> - Use o primeiro dia do mês em que a data inicial do arrendamento cairá como a data de início.</li></ul><p>Se você selecionar <b>Nenhum</b>, haverá um risco de que os agendamentos de amortização de passivos e de depreciação de ativos sejam acumulados e lançados no meio do mês, e não no final do mês. Ao selecionar o <b>Mês inteiro</b>, você garante que o sistema começará a levar em conta o arrendamento no primeiro dia do mês e que a despesa do mês inteiro será acumulada e lançada no último dia do mês.</p><p><strong>Observação:</strong> o recurso de convenções de arrendamento precisa ser ativado por meio do Gerenciamento de recursos. No espaço de trabalho <b>Gerenciamento de recursos</b>, localize e selecione o recurso denominado <b>Convenção de arrendamento para arrendamento de ativos</b> e selecione <b>Habilitar agora</b>.</p> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
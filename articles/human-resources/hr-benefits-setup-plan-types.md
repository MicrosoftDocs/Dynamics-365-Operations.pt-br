---
title: Visão geral do tipo de plano
description: Um tipo de plano no Microsoft Dynamics 365 Human Resources é um agrupamento de alto nível de tipos específicos de benefícios. Cada tipo de plano tem um código de tipo de plano que determina as regras para o tipo de plano.
author: andreabichsel
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 806b3839feb1e1bf889747986388a56113c3ebe1
ms.sourcegitcommit: 08797bc43e93ea05711c5a70dd7cdb82cada667a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6558264"
---
# <a name="plan-type-overview"></a>Visão geral do tipo de plano

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Um tipo de plano é um agrupamento de alto nível de tipos específicos de benefícios. Cada tipo de plano tem um código de tipo de plano que determina as regras para o tipo de plano. Por exemplo, o tipo de plano **Vida básica** terá o código de tipo de plano **Vida** porque é um tipo de plano de seguro de vida e deve seguir as regras que foram estabelecidas para o código de tipo de plano **Vida**. Outro tipo de plano pode ser **Vida complementar**. Este tipo de plano também terá o código de tipo de plano **Vida**.

Cada tipo de plano indica se um funcionário pode se inscrever em um plano desse tipo ou em vários. Por exemplo, um funcionário provavelmente poderá registrar tanto a vida básica quanto as políticas de vida suplementares do tipo de plano Vida. Um funcionário provavelmente terá permissão para inscrever-se em apenas uma política do tipo médico.

Se um tipo de plano envolver contatos, o tipo de plano indicará se os contatos são beneficiários ou dependentes. Por exemplo, um tipo de plano de vida básico teria os beneficiários, enquanto um tipo de plano médico básico teria dependentes. Em alguns casos, um plano pode não ter contatos pessoais. Por exemplo, uma conta de despesas flexível ou bonificação de estacionamento.

Um tipo de plano pode definir opções de cobertura. As opções de cobertura são definidas no formulário opção de cobertura. Uma opção de cobertura pode especificar o valor do benefício ou os contatos qualificados para o tipo de plano. Por exemplo, se o tipo de contato for beneficiário, a opção de cobertura deverá definir os termos do que o beneficiário está qualificado para receber quando o benefício é utilizado. Se o tipo de contato for dependente, a opção de cobertura deverá definir o relacionamento entre o dependente e o funcionário. 

> [!IMPORTANT]
> O formulário inclui dados-chave que afetam as opções disponíveis quando um novo plano de benefícios é criado:
>
> - **Código de tipo de plano** – Este campo afeta o que é mostrado na guia **Configuração** quando o benefício real é configurado.  
> - **Registro simultâneo** – Este campo determina se vários registros são permitidos. (Em um plano médico, este campo é tipicamente definido como **Um registro**.)
> - **Tipo de contato** – Este campo permite que dependentes ou beneficiários sejam adicionados a um plano. Se for definido como **Nenhum**, os funcionários que se inscreverem nos benefícios não terão a opção de selecionar um beneficiário ou um dependente.
> - **Opções de cobertura** – Use este campo para vincular as opções de cobertura com os tipos de plano. Ele define as pessoas que receberão cobertura desse tipo de plano ou os valores de cobertura que estão disponíveis para este tipo de plano. Por exemplo, você pode especificar que a cobertura para um tipo de plano médico estará disponível apenas para o funcionário, para o funcionário e uma outra pessoa ou para o funcionário e sua família.

## <a name="create-plan-types"></a>Criar tipos de plano

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Tipos de plano**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Tipo de plano** | Um nome exclusivo que identifica o tipo de plano. |
   | **Descrição** | Uma descrição do tipo de plano. |
   | **Código do tipo de plano** | Selecione um código do tipo de plano na lista suspensa de valores. A lista de códigos do tipo de plano exibe todos os tipos de plano que têm suporte na versão atual. |
   | **Inscrição simultânea** | Especifica se um funcionário pode se inscrever em vários planos de benefícios do mesmo tipo de plano ou somente um plano de benefício por tipo de plano. |
   | **Tipo de contato** | Especifica a função do contato pessoal. Os valores são em branco, dependente e beneficiário. Você poderá deixar o **Tipo de contato** em branco se o tipo de plano não exigir um dependente ou beneficiário com base na opção de cobertura. |

4. Para configurar opções de evento de vida, selecione **Ações** e **Opções de evento de vida**. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Tipo de plano** | O tipo de plano no qual configurar opções de evento de vida. |
   | **ID do tipo de evento de vida** | A ID do tipo de evento de vida. |
   | **Permitir cancelamento** | Especifica se um funcionário pode cancelar um plano de benefícios durante o evento de vida. |
   | **Alterar opção de cobertura** | Especifica se um funcionário pode alterar opções de cobertura durante o evento de vida. |
   | **Alterar para um novo plano** | Especifica se um funcionário pode alterar planos durante o evento de vida. |
   | **Cancelar plano automaticamente** | Especifica se o plano deve ser cancelado automaticamente durante o evento de vida. |
   | **Verificação de qualificação para reabertura automática** | Especifica se a verificação de qualificação de inscrição no benefício será reaberta automaticamente durante o evento de vida. |
   | **Janela do relatório** | Especifica a janela do relatório, em dias, do evento de vida. **Observação**: se você não inserir um valor, o sistema assumirá que a janela de relatório é zero e não processará o evento de vida. |

5. Selecione **Salvar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

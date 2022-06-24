---
title: Encerrar agendas de cobrança
description: Este artigo explica como encerrar agendas de cobrança e linhas da agenda de cobrança na Cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 4fce23f3cf35ef8c388ce13fc422f268a2bd8e32
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872547"
---
# <a name="terminate-billing-schedules"></a>Encerrar agendas de cobrança

[!include [banner](../includes/banner.md)]

Este artigo explica como encerrar agendas de cobrança e linhas da agenda de cobrança na Cobrança de assinatura. Quando você encerra uma agenda de cobrança, ela deve ter o status **Ativo**. Ela não pode ter o status **Em espera**. Da mesma forma, quando você encerra uma linha da agenda de cobrança, ela deve ter o status **Ativo**. A seção de cabeçalho da agenda de cobrança não é afetada quando você encerra uma linha da agenda de cobrança.

Para encerrar uma agenda de cobrança ou linha da agenda de cobrança, acesse um dos seguintes locais:

- A página de listagem **Todas/Agendas de cobrança ativas**
- Uma agenda de cobrança específica na página **Todas as agendas de cobrança**
- Uma linha específica da agenda de cobrança na página **Todas as agendas de cobrança**

> [!NOTE]
> Se desejar encerrar várias agendas de cobrança ao mesmo tempo, use a página **Processamento de encerramento em massa**.

## <a name="terminate-a-billing-schedule-or-line"></a>Encerrar uma linha ou agenda de cobrança

Para encerrar uma agenda de cobrança ou linha da agenda de cobrança, siga estas etapas.

1. Selecione uma agenda de cobrança ou uma linha da agenda de cobrança e escolha **Encerrar**. 
2. Defina os campos **Data de encerramento**, **Tipo de encerramento** e **Código de motivo**.
3. Defina o campo **Opção de crédito** como **Emitir crédito**.
4. Selecione **Encerrar**.

O status da agenda de cobrança é alterado com base no tipo de encerramento selecionado. Se você selecionou **Cobranças restantes** como o tipo de encerramento, o status de todas as linhas da agenda de cobrança será **Última cobrança**. O status da agenda de cobrança permanecerá **Ativo** até a última fatura ser processada. Depois que a última fatura for processada, o status será atualizado para **Encerrado**. Se você selecionou **Ajustar agenda** como o tipo de encerramento, o status da agenda de cobrança será imediatamente atualizado para **Encerrado**.

## <a name="terminate-a-billing-schedule-or-line-and-apply-a-refund"></a>Encerrar uma linha ou agenda de cobrança e aplicar um reembolso

Para encerrar uma agenda de cobrança ou linha da agenda de cobrança e aplicar um reembolso, siga estas etapas.

1. Selecione uma agenda de cobrança ou uma linha da agenda de cobrança e escolha **Encerrar**.
2. Defina os campos **Data de encerramento**, **Tipo de encerramento**, **Código de motivo** e **Opção de crédito**.
3. Selecione **Encerrar com reembolso**. A página **Processamento de encerramento em massa** é exibida e filtrada para mostrar a agenda de cobrança.
4. Selecione **Exibir pré-visualização** para exibir as linhas das agendas de cobrança e, em seguida, selecione **Processar**.

Depois que o crédito for processado, abra a página **Exibir detalhe de cobrança** para revisar o crédito aplicado à agenda de cobrança. Se o valor de crédito for maior que 0 (zero), todas as linhas futuras não faturadas serão excluídas e substituídas pelas linhas de detalhe da cobrança que mostram os valores negativos para o crédito que foi aplicado à agenda de cobrança.

### <a name="view-example"></a>Exibir exemplo

Uma agenda de cobrança tem as seguintes informações:

- A data de início é 1º de janeiro de 2020.
- A data de término é 31 de dezembro de 2020.
- O valor do período de cobrança é 100,00 por mês.
- As faturas foram criadas para períodos de cobrança de janeiro a julho.
- A data de encerramento do contrato é 15 de junho de 2020.

Quando o ajuste de crédito é processado, todos os períodos de cobrança futuros (de agosto a dezembro) são removidos da página **Exibir detalhe de cobrança**. Uma linha de ajuste de crédito é adicionada após o período de cobrança de julho:

- 16 de junho a 31 de julho, com um valor de crédito de 150,00

Se o recurso de receita não faturada for usado, a página **Auditoria de entrada de diário de receita não faturada** será atualizada com a entrada de encerramento.

## <a name="terminate-a-billing-schedule-or-line-without-applying-a-credit"></a>Encerrar uma linha ou agenda de cobrança sem aplicar um crédito

Para encerrar uma agenda de cobrança ou linha da agenda de cobrança sem aplicar um crédito, siga estas etapas.

1. Selecione uma agenda de cobrança ou uma linha da agenda de cobrança e escolha **Encerrar**.
2. Defina o campo **Data de encerramento**.
3. Defina o campo **Tipo de encerramento** como **Sem ajuste**. O campo **Opção de crédito** é automaticamente definido como **Sem crédito**.
3. Defina o campo **Código de motivo**.
4. No campo **Notas de encerramento**, insira observações adicionais necessárias.
5. Selecione **Encerrar**. 

Quando o encerramento é processado, todas as linhas de detalhe de cobrança datadas após data de encerramento serão removidas. (Essas linhas incluem a linha que contém a data de encerramento.) Não é possível criar faturas para as linhas encerradas. Se o encerramento for removido, todas as linhas encerradas serão adicionadas novamente à página **Exibir detalhes de cobrança** e estarão disponíveis para o faturamento.

## <a name="fields"></a>Campos

A página **Exibir detalhes de cobrança** contém os campos a seguir.

| Campo | Descrição |
|-------|-------------| 
| Data da rescisão | Selecione a data em que deseja encerrar uma linha da agenda de cobrança ou agenda de cobrança. |
| Tipo de finalização | <p>Selecione o tipo de encerramento:</p><ul><li>**Ajustar agenda** – corta os períodos de cobrança da linha na data de encerramento e altera o status da linha para **Última cobrança**. Se houver uma agenda de adiamento para o item de linha, ela será ajustada pela reversão do valor que não deve mais ser reconhecido. Se a data de início da cobrança for posterior à data de encerramento, os períodos de cobrança restantes serão removidos.</li><li>**Cobrança restante** – adiciona qualquer valor que resta do período de cobrança ao período de encerramento e altera o status da linha para **Última cobrança**. Se houver uma agenda de adiamento para o item de linha, a data de término de adiamento será atualizada. Se a data de início da cobrança for posterior à data de encerramento, o valor total de todos os períodos de cobrança restantes será adicionado ao período de cobrança e os períodos de cobrança restantes serão removidos.</li><li>**Nenhum ajuste** – encerra os períodos de cobrança da linha na data de encerramento especificada. Nenhum ajuste é feito. Quando esse tipo de encerramento é selecionado, o campo **Opção de crédito** é definido como **Sem crédito** e o campo **Rateio diário** é definido como **Não**. Os dois campos se tornarão somente leitura e não poderão ser alterados.</li></ul> |
| Opção de crédito | <p>Selecione como o crédito é aplicado ao encerrar uma linha da agenda de cobrança:</p><ul><li>**Ajuste de crédito** – cria um ajuste de crédito para uma agenda de cobrança quando uma linha é encerrada. O ajuste de crédito é exibido em um período de cobrança futuro para a agenda de cobrança. O ajuste também adapta automaticamente o valor da fatura para o próximo período de cobrança até que o crédito tenha sido aplicado à agenda de cobrança.</li><li>**Emitir crédito** – cria uma nota de crédito quando uma agenda de cobrança ou linha de agenda de cobrança é encerrada.</li><li>**Sem crédito** – não cria um ajuste de crédito ou uma nota de crédito quando uma agenda de cobrança ou linha de agenda de cobrança é encerrada. Esta opção está disponível somente quando você usa um encerramento do tipo **Sem ajuste** para encerrar uma agenda de cobrança.</li></ul><p>A opção padrão é da página **Parâmetros de cobrança recorrente de contrato**.</p> |
| Código do motivo | Selecione o código do motivo para o encerramento. |
| Descrição do motivo | A descrição do código de motivo. |
| Notas de finalização | Faça observações sobre o encerramento. |

<!--## Additional information-->

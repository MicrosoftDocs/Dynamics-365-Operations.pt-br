---
title: Redefinir números de recibo
description: Este tópico descreve como redefinir os números de recibo usados para várias ações em uma data desejada (por exemplo, o ano fiscal ou o ano civil).
author: ShalabhjainMSFT
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: a08d14369057ceb9b23e9d6f9a79847c6175f88e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345073"
---
# <a name="reset-receipt-numbers"></a>Redefinir números de recibo 

[!include [banner](includes/banner.md)]

> [!NOTE]
> Será necessário selecionar a propriedade **Sequência independente** para todos os tipos de recibos no perfil de funcionalidade antes de usar este recurso. Além disso, o fuso horário do sistema do dispositivo, no qual o PDV está sendo usado, deve corresponder ao fuso horário da loja correspondente. Devido a essas limitações, recomendamos que você não use este recurso na produção enquanto trabalhamos para corrigir esses problemas em uma versão futura. 

Os varejistas geram números de recibo para várias ações na loja, como transações cash and carry, transações de devolução, ordens de cliente, cotações e pagamentos. Embora os varejistas definam seus próprios formatos de recibo, alguns países ou regiões têm regulamentos que colocam restrições nesses formatos de recibo. Por exemplo, esses regulamentos podem limitar o número de caracteres no recebimento, exigir números de recibo consecutivos, restringir alguns caracteres especiais ou exigir a redefinição de números de recibo no início do ano. O Microsoft Dynamics 365 Commerce torna o processo de gerenciar números de recibo muito flexível, para ajudar os varejistas a cumprirem requisitos de regulamentação. Este tópico explica como usar a funcionalidade para redefinir números de recibo.

No Commerce, os formatos de recibo podem ser alfanuméricos. Você pode colocar conteúdo estático e conteúdo dinâmico neles. O conteúdo estático inclui caracteres alfabéticos, números e caracteres especiais. O conteúdo dinâmico inclui um ou mais caracteres que representam informações como o número da loja, o número do terminal, a data, o mês, o ano e as sequências numéricas que são incrementadas automaticamente. Os formatos são definidos na seção **Numeração do recibo** do perfil de funcionalidade. A tabela a seguir descreve os caracteres que representam o conteúdo dinâmico.

| Caracteres | Descrição |
|------------|-------------|
| S          | O caractere **S** é usado para o número da loja. Por exemplo, se uma loja for numerada HOUSTON1, o formato **SSS** mostrará "ON1" no recibo. O formato **SSSSS** mostra "STON1" no recibo. |
| T          | O caractere **T** é usado para o número do terminal. Por exemplo, se um terminal for numerado 0001, o formato **TTTT** mostrará "0001" no recibo. |
| C          | O caractere **C** é usado para o número da ID da equipe. Por exemplo, se um membro da equipe tiver uma ID de 000160, o formato **CCCC** mostrará "0160" no recibo. |
| ddd        | Os caracteres **ddd** correspondem ao dia do ano, de 1 a 366. Por exemplo, em 15 de Janeiro, o formato **ddd** mostra "015" no recibo. |
| MM         | Os caracteres **MM** são usados para o mês de dois dígitos. Por exemplo, em janeiro, o formato **MM** mostra "01" no recibo. |
| DD         | Os caracteres **DD** são usados para o dia do mês de dois dígitos. Por exemplo, em 15 de janeiro, o formato **DD** mostra "15" no recibo. |
| AA         | Os caracteres **AA** são usados para o ano de dois dígitos. Por exemplo, em qualquer mês durante o ano de 2020, o formato **AA** mostra "20" no recibo. |
| \#         | Um sinal numérico (**\#**) é usado na numeração sequencial. Por exemplo, o formato **####** mostra "0001", "0002", "0003" e assim por diante no recibo. |

Você pode redefinir a numeração sequencial do recibo em uma data específica. Em seguida, para a primeira transação que ocorre após 12:00 AM na data de redefinição selecionada, o sistema redefine a sequência numérica do recibo como 1. Você também pode especificar se a redefinição ocorre apenas uma vez ou se ela se repete a cada ano. Se a recorrência anual for especificada, a redefinição ocorrerá automaticamente a cada ano até que o varejista decida pará-la. 

Para ativar a redefinição, siga estas etapas.

1. Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**.
1. Na Guia Rápida **Numeração de recibo**, selecione **Redefinir data de redefinição de número**.
1. Na caixa de diálogo suspensa, no campo **Redefinir data**, selecione uma data futura em que a redefinição deverá ocorrer.
1. No campo **Redefinir tipo de recibo**, selecione **Apenas uma vez** ou **Anual**.
1. Selecione **OK**.

![Selecionando uma data de redefinição de recibo.](media/Enable_receipt_reset.png "Seleção de uma data de redefinição de recibo")

Depois que você seleciona uma data, ela aparece na coluna **Próxima data de redefinição do número do recibo**. A data de redefinição é aplicável a todos os tipos de transação de recibo. Portanto, a sequência numérica do recibo será redefinida para todos os tipos de recibo.

Quando a data de redefinição chega, o número do recibo é redefinido para a primeira transação de cada tipo. Além disso, no perfil de funcionalidade, a data de redefinição é movida da coluna **Próxima data de redefinição do número do recibo** para a coluna **Data de redefinição de número de recibo atual**. Essa alteração indica que, se um registro não for usado na data de redefinição, o número do recibo será redefinido na próxima vez que esse registro *for* usado. Por exemplo, em 3 de dezembro de 2019, você seleciona **1º de janeiro de 2020** como a data de redefinição. Em 1º de janeiro, quando os registradores fazem a primeira transação, o número do recibo é redefinido. No entanto, um registro não é usado em dezembro e janeiro, mas começa a ser usada em fevereiro. Nesse caso, como uma ação de redefinição foi definida, o número do recibo desse registro será redefinido quando o registro fizer a primeira transação em fevereiro.

Você pode usar a funcionalidade **Limpar data de redefinição** para limpar datas de redefinição futuras. No entanto, se a data de redefinição tiver ocorrido no passado, ela não poderá ser desfeita. Portanto, a redefinição ainda ocorrerá para todos os registros em que a redefinição ainda não ocorreu.

> [!NOTE]
> Dependendo da data de redefinição selecionada e do formato de recibo, você pode ter números de recibo duplicados. Embora o sistema do ponto de venda (PDV) possa lidar com essas situações, elas aumentam o tempo exigido para processar devoluções, pois parceiros de vendas devem selecionar entre os recibos duplicados. Outras complicações relativas à limpeza de dados poderiam ocorrer se os recibos duplicados não fossem uma consequência planejada. Portanto, é recomendável usar caracteres de data dinâmica (por exemplo **ddd**, **MM**, **DD** e **AA**) para ajudar a evitar números de recebo duplicados após uma redefinição.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
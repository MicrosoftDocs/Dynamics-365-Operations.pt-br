---
title: Verificador de consistência das transações de varejo
description: Este tópico descreve a funcionalidade do verificador de consistência das transações no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: eb5c7389ba29d50232f9321e40bccceecd5f5fc6
ms.sourcegitcommit: 02640a0f63daa9e509146641824ed623c4d69c7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "3265609"
---
# <a name="retail-transaction-consistency-checker"></a>Verificador de consistência das transações de varejo

[!include [banner](includes/banner.md)]

Este tópico descreve a funcionalidade do verificador de consistência das transações no Microsoft Dynamics 365 Commerce. O verificador de consistência identifica e isola as transações inconsistentes antes que elas sejam coletadas pelo processo de lançamento de demonstrativo.

Quando um demonstrativo é lançado, pode haver falha no lançamento devido a dados inconsistentes nas tabelas de transações de comércio. O problema nos dados pode ser causado por imprevistos no aplicativo de ponto de venda (PDV) ou pela importação incorreta das transações de sistemas POS de terceiros. Exemplos de como essas inconsistências podem ser exibidas: 

- O total da transação na tabela do cabeçalho não corresponde ao total da transação nas linhas.
- A contagem de linhas na tabela do cabeçalho não corresponde ao número de linhas na tabela de transações.
- Os impostos na tabela do cabeçalho não correspondem ao valor do imposto nas linhas. 

Quando transações inconsistentes são coletadas pelo processo de lançamento de demonstrativo, diários de pagamentos e faturas de vendas inconsistentes são criados e, consequentemente, o processo inteiro falha. Recuperar os demonstrativos desse estado envolve correções complexas de dados em várias tabelas de transações. O verificador de consistência das transações evita esses problemas.

O gráfico a seguir ilustra o processo de lançamento com o verificador de consistência das transações.

![Processo de lançamento do demonstrativo com verificador de consistência de transação](./media/validchecker.png "Processo de lançamento do demonstrativo com verificador de consistência de transação de varejo")

O processo em lote **Validar transações de loja** verifica a consistência das tabelas de transações de comércio para os cenários a seguir.

- **Conta de cliente** - valida se a conta de cliente nas tabelas de transações de varejo existe no cliente mestre da matriz.
- **Contagem de linhas** - valida se o número de linhas, como capturado na tabela de cabeçalho de transações, corresponde ao número de linhas nas tabelas de transações de vendas.
- **Preço incluindo imposto** — valida se o parâmetro **Preço incluindo imposto** é consistente nas linhas de transação.
- **Valor do pagamento** — valida se os registros de pagamento corresponderem ao valor do pagamento no cabeçalho.
- **Valor bruto** — valida se o valor bruto no cabeçalho é a soma dos valores líquidos nas linhas mais o valor do imposto.
- **Valor líquido** — valida se o valor líquido no cabeçalho é a soma dos valores líquidos nas linhas mais o valor do imposto.
- **Pagamento a maior/a menor** — valida se a diferença entre o valor bruto no cabeçalho e o valor do pagamento não excede a configuração de pagamento maior/a menor máximo.
- **Valor de desconto** - valida se o valor de desconto nas tabelas do desconto e o valor de desconto na linha das tabelas de transações são consistentes, e se o valor de desconto no cabeçalho é a soma dos valores dos descontos nas linhas.
- **Desconto de linha** - valida se o desconto de linha na linha de transação é a soma de todas as linhas na tabela de desconto que corresponde à linha de transação.
- **Item do cartão-presente** - o Commerce não oferece suporte à devolução de itens do cartão-presente. No entanto, o saldo em um cartão-presente pode ser resgatado. Haverá falha no processo de lançamento de demonstrativo em qualquer item de cartão-presente que seja processado como uma linha de devolução em vez de uma linha de resgate. O processo de validação de itens de cartão-presente ajuda a garantir que somente os itens de cartão-presente devolvidos nas tabelas de transação sejam linhas de resgate de cartão-presente.
- **Preço negativo** - valida se não há nenhum preço negativo nas linhas de transação.
- **Item e grade** — valida se os itens e as grades nas linhas de transação existem no item e no arquivo mestre da grade.
- **Valor do imposto** — valida se os registros de impostos correspondem aos valores de imposto nas linhas.
- **Número de série** — valida se o número de série. está presente nas linhas de transação dos itens que são controlados por número de série.
- **Sinal** — valida se o sinal na quantidade e no valor líquido são iguais em todas as linhas de transação.
- **Data comercial** - valida se os períodos financeiros para todas as datas comerciais para as transações estão abertos.

## <a name="set-up-the-consistency-checker"></a>Configurar o verificador de consistência

Configure o processo em lote "Validar transações de loja" em **Varejo e Comércio \> TI de Varejo e Comércio \> Lançamento do PDV** para execuções periódicas. O trabalho em lotes pode ser agendado com base na hierarquia da organização da loja, semelhante a como os processos "Calcular demonstrativos em lote" e "Lançar demonstrativos em lote" são configurados. É recomendável configurar esse processo em lote para ser executado várias vezes em um dia e agendá-lo de forma que isso ocorra ao final de cada execução de trabalho P.

## <a name="results-of-validation-process"></a>Resultados do processo de validação

Os resultados da verificação de validação pelo processo em lote são marcados na transação apropriada. O campo **Status de validação** do registro de transação é definido como **Êxito** ou **Erro** e a data da última execução de validação aparece no campo **Hora da última validação**.

Para exibir um texto de erro mais descritivo referente a uma falha de validação, selecione o registro de transação da loja relevante e clique no botão **Erros de validação**.

As transações que forem reprovadas na verificação de validação e as que ainda não tiverem sido validadas não serão incluídas nos demonstrativos. Durante o processo "Calcular demonstrativo", os usuários serão notificados se houver transações que poderiam ter sido incluídas no demonstrativo, mas não foram.

Se um erro de validação for encontrado, a única maneira de corrigi-lo é entrar em contato com o Suporte da Microsoft. Em uma versão futura, será adicionado um recurso para que os usuários possam corrigir os registros com falha por meio da interface do usuário. Recursos de registro e auditoria também serão disponibilizados para rastrear o histórico de modificações.

> [!NOTE]
> Regras de validação adicionais para oferecer suporte a mais cenários serão adicionadas em uma versão futura.

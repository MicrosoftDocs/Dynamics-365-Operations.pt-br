---
title: Verificador de consistência das transações de varejo
description: Este tópico descreve a funcionalidade do verificador de consistência das transações de varejo no Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
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
ms.openlocfilehash: 972c4d6b244eebc85cc801353ce8fb25ecbc0655
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517000"
---
# <a name="retail-transaction-consistency-checker"></a>Verificador de consistência das transações de varejo


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

Este tópico descreve a funcionalidade do verificador de consistência das transações de varejo introduzido no Microsoft Dynamics 365 for Finance and Operations versão 8.1.3. O verificador de consistência identifica e isola as transações inconsistentes antes que elas sejam coletadas pelo processo de lançamento de demonstrativo.

Quando um demonstrativo é lançado no Retail, o lançamento pode falhar devido a dados inconsistentes nas tabelas de transações de varejo. O problema nos dados pode ser causado por imprevistos no aplicativo de ponto de venda (PDV) ou pela importação incorreta das transações de sistemas POS de terceiros. Exemplos de como essas inconsistências podem ser exibidas: 

  - O total da transação na tabela do cabeçalho não corresponde ao total da transação nas linhas.
  - A contagem de linhas na tabela do cabeçalho não corresponde ao número de linhas na tabela de transações.
  - Os impostos na tabela do cabeçalho não correspondem ao valor do imposto nas linhas. 
  
Quando transações inconsistentes são coletadas pelo processo de lançamento de demonstrativo, diários de pagamentos e faturas de vendas inconsistentes são criados e, consequentemente, o processo inteiro falha. Recuperar os demonstrativos desse estado envolve correções complexas de dados em várias tabelas de transações. O verificador de consistência das transações de varejo evita esses problemas.

O gráfico a seguir ilustra o processo de lançamento com o verificador de consistência das transações.

![Processo de lançamento de demonstrativo com o verificador de consistência das transações de varejo](./media/validchecker.png "Processo de lançamento de demonstrativo com o verificador de consistência das transações de varejo")

O processo em lote **Validar transações de loja** verifica a consistência das tabelas de transações de varejo para os seguintes cenários.

- Conta de cliente – valida que a conta de cliente nas tabelas de transações de varejo existe no cliente mestre da sede.
- Contagem de linhas – valida que o número de linhas, como capturado na tabela do cabeçalho de transações, corresponde ao número de linhas nas tabelas de transações de vendas.

## <a name="set-up-the-consistency-checker"></a>Configurar o verificador de consistência
Configure o processo em lote "Validar transações de loja" em **Varejo \> TI de Varejo \> Lançamento do PDV** para execuções periódicas. O trabalho em lotes pode ser agendado com base na hierarquia da organização da loja, semelhante a como os processos "Calcular demonstrativos em lote" e "Lançar demonstrativos em lote" são configurados. É recomendável configurar esse processo em lote para ser executado várias vezes em um dia e agendá-lo de forma que isso ocorra ao final de cada execução de trabalho P.

## <a name="results-of-validation-process"></a>Resultados do processo de validação
Os resultados da verificação de validação pelo processo em lote são marcados na transação de varejo apropriada. O campo **Status de validação** do registro de transação de varejo é definido como **Êxito** ou **Erro** e a data da última execução de validação aparece no campo **Hora da última validação**.

Para exibir um texto de erro mais descritivo referente a uma falha de validação, selecione o registro de transação de loja de varejo relevante e clique no botão **Erros de validação**.

As transações que forem reprovadas na verificação de validação e as que ainda não tiverem sido validadas não serão incluídas nos demonstrativos. Durante o processo "Calcular demonstrativo", os usuários serão notificados se houver transações que poderiam ter sido incluídas no demonstrativo, mas não foram.

Se um erro de validação for encontrado, a única maneira de corrigi-lo é entrar em contato com o Suporte da Microsoft. Em uma versão futura, será adicionado um recurso para que os usuários possam corrigir os registros com falha por meio da interface do usuário. Recursos de registro e auditoria também serão disponibilizados para rastrear o histórico de modificações.

> [!NOTE]
> Regras de validação adicionais para oferecer suporte a mais cenários serão adicionadas em uma versão futura.

---
title: Reavaliar pagamentos do arrendamento vinculados a uma taxa indexada
description: Este tópico descreve o ajuste feito para responsabilidade com arrendamento de um ativo de direito de uso (DDU) quando os pagamentos de arrendamento variáveis são alterados por causa de uma alteração na taxa indexada.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 79e8922a6118693db941ec259a2a1004e3522954
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241361"
---
# <a name="revalue-lease-payments-that-are-linked-to-an-index-rate"></a>Reavaliar pagamentos do arrendamento vinculados a uma taxa indexada

[!include [banner](../includes/banner.md)]

Este tópico descreve o ajuste feito para a responsabilidade com arrendamento de um ativo de direito de uso (DDU) quando os pagamentos de arrendamento variáveis são alterados por causa de uma alteração na taxa indexada. A responsabilidade com arrendamento e o ativo de direito de uso serão ajustados para os novos valores de pagamento. Sob o Tópico 842 da Codificação de Padrões Contábeis (ASC 842), que é o padrão nos Princípios Contábeis Geralmente Aceitos nos Estados Unidos (US GAAP), somente os pagamentos variáveis são alterados quando os pagamentos aumentam ou diminuem por causa de uma alteração na taxa indexada, a menos que haja alterações adicionais nos fluxos de caixa. Essas alterações adicionais podem incluir uma alteração nos prazos de arrendamento relacionados às taxas de juros. Para obter mais informações, consulte ASC 842-10-55-225 e o parágrafo 42(b) do Padrão Internacional de Relatórios Financeiros 16 (IFRS 16).

## <a name="adjust-lease-payments"></a>Ajustar pagamentos do arrendamento

Siga estas etapas para reavaliar pagamentos do arrendamento vinculados a uma taxa indexada.

1. Para executar o processo de reavaliação do índice de arrendamento, acesse **Arrendamento de ativo \> Periódico \> Reavaliação de taxa indexada**.

    A página **Reavaliação da taxa indexada** é exibida e mostra todos os processos anteriores de reavaliação do índice de arrendamento que foram executados. As informações nesta página incluem a ID do processo gerada da configuração da sequência numérica, a entidade legal, o número de registros de arrendamento que foram ajustados, o ajuste do total de passivos para arrendamentos IFRS 16 e total de pagamentos variáveis que foram ajustados para arrendamentos ASC 842.

2. Para executar a reavaliação, no Painel de Ações, selecione **Reavaliação do índice de arrendamento**.

    A caixa de diálogo **Parâmetros de reavaliação de índice** é exibida. Aqui, você pode filtrar e selecionar quais arrendamentos, grupos de arrendamento ou outros critérios devem ser usados quando você seleciona os arrendamentos a serem reavaliados. Além disso, na guia **Executar em segundo plano**, você pode configurar o processo de reavaliação do índice para que ele seja executado em um lote.

4. Selecione os filtros para selecionar arrendamentos que devem ser incluídos no processamento em segundo plano e selecione **OK**.

    A caixa de diálogo **Versão preliminar da reavaliação da taxa indexada** aparece e mostra os arrendamentos que serão reavaliados. Também mostra os ajustes de ativos e passivos ou os ajustes de pagamentos variáveis.
    
5. Para evitar que os arrendamentos sejam reavaliados, selecione os arrendamentos que **devem** ser reavaliados. Se você não selecionar um arrendamento, todos os arrendamentos serão reavaliados. Quando terminar, selecione **OK** para reavaliar os pagamentos do arrendamento.
6. Para exibir as transações que foram criadas para um processo de reavaliação do índice específico, selecione a ID do processo e, em seguida, selecione **Transações**.

    Será exibida uma caixa de diálogo mostrando os detalhes das transações criadas durante o processamento.

> [!NOTE]
> Somente os arrendamentos com uma data de reavaliação na data do sistema ou antes dela podem ser reavaliados. O sistema ignora automaticamente todos os arrendamentos com uma data de reavaliação posterior à data do sistema.

## <a name="asc-842-leases--index-revaluation"></a>Arrendamentos ASC 842 – reavaliação do índice

Para exibir os efeitos do processo de reavaliação do arrendamento em arrendamentos ASC 842, abra a agenda de pagamento para um arrendamento. A página mostra somente os pagamentos variáveis que foram feitos na alteração da data de reavaliação ou depois dela devido à reavaliação do índice. As agendas de amortização e depreciação permanecem inalteradas. Quando você cria uma fatura com um pagamento variável, o pagamento variável é debitado na conta de lançamento de Pagamento variável. Além disso, o valor do pagamento variável é adicionado à entrada de crédito que é lançada diretamente para o fornecedor ou lançado na conta de Notas a pagar, dependendo da configuração do registro de arrendamento.

As linhas da agenda de pagamento na página detalhes do arrendamento são atualizadas automaticamente com uma nova linha que indica a nova taxa indexada. Além disso, uma coluna mostra se a linha foi criada manualmente ou por meio do processo de reavaliação do índice.

## <a name="ifrs-16-leases--index-revaluation"></a>Arrendamentos IFRS 16 – reavaliação do índice

Para exibir os efeitos do processo de reavaliação do arrendamento em arrendamentos IFRS 16, abra os detalhes do arrendamento para um arrendamento ajustado. Os campos **Prazo de arrendamento** e **Tempo de vida útil do ativo** foram atualizados para refletir a passagem de tempo da data de início ou da data de modificação para a data de reavaliação. Além disso, as linhas da agenda de pagamento foram atualizadas para refletir os novos pagamentos no arrendamento, a nova taxa indexada e como a linha foi criada.

Você pode exibir a agenda de pagamento recém-gerada que começa na data de reavaliação e mostra o valor de pagamento total atualizado. Uma nova agenda de amortização de responsabilidade com arrendamento e uma agenda de depreciação de ativos também foram criadas para refletir a agenda de pagamento ajustada.

A entrada de diário lançou automaticamente a entrada do diário de ajuste na conta para a alteração nos pagamentos de arrendamento que estão relacionados à reavaliação do índice.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
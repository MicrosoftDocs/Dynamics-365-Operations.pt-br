---
title: Associar ativos fixos a arrendamentos
description: O tópico explica como associar um ativo fixo existente a um novo arrendamento.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bd55d433b0961b8b210b9c28d7340ff880635a85
ms.sourcegitcommit: 3af457fc216bd0020843291ca57fd379acb53c96
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2021
ms.locfileid: "7392465"
---
# <a name="associate-fixed-assets-with-leases"></a>Associar ativos fixos a arrendamentos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O tópico explica como associar um ativo fixo existente a um novo arrendamento. Quando você associa um ativo fixo a um arrendamento, o valor de ativo DDU (direito de uso) no reconhecimento inicial será o custo de aquisição do ativo fixo.

Para poder associar um ativo fixo a um arrendamento, você deve criar um registro para o ativo fixo em Ativos fixos. Em seguida, na página **Resumo da arrendamento**, você deve criar um arrendamento e vincular o ativo a esse arrendamento.

1. Adicione um arrendamento seguindo as etapas em [Adicionar ou copiar arrendamentos](add-lease.md). Na página **Adicionar leasing**, no campo **Número de ativo fixo**, selecione o ativo que ainda não foi adquirido.
2. Selecione **Livros** e confirme a agenda de pagamento.
3. Selecione **Reconhecimento inicial**.
4. Selecione **Diário de arrendamento de ativo**.

    A entrada de diário de reconhecimento inicial para os débitos de leasing do ativo fixo para o valor que geralmente é debitado na conta de ativo DDU.

    Agora você pode exibir o tipo de transação e o registro para o ativo fixo.

5. Selecione **Detalhes do diário**.
6. Selecione **Linhas** para exibir as linhas individuais da entrada de diário.
7. Selecione a linha do diário que contém o ativo e, em seguida, selecione a guia **Ativos Fixos**.

    A guia **Ativos fixos** mostra o tipo de transação e o registro. Por padrão, o campo **Tipo de transação** é definido como **Aquisição**, e o campo **Livro** é definido como o livro atual do ativo fixo.

Depois de lançar a entrada inicial do diário de reconhecimento, a transação aparece como uma transação de aquisição para o ativo fixo. Para exibir a tabela de transações, Acesse **Ativos fixos \> Ativos fixos \> Ativos fixos**, selecione o ativo apropriado e depois **Avaliações**. Você verá que a entrada inicial do diário de reconhecimento criou uma transação de aquisição para o ativo fixo especificado.

O ativo fixo agora pode ser depreciado usando a funcionalidade de depreciação padrão em Ativos fixos. Para obter mais informações depreciação, consulte [Métodos e convenções de depreciação](../fixed-assets/depreciation-methods-conventions.md).

Quando uma concessão é associada a um ativo fixo, o campo **Duração do serviço** no registro de ativos fixos será atualizado para alinhar com o menor valor dos seguintes critérios: 

 - A vida útil do ativo
 - O prazo de arrendamento do registro de arrendamento associado

Se o campo **Transferência de propriedade** estiver definido como **Sim** para o registro de arrendamento, o valor no campo **Vida útil** será sempre a vida útil do ativo. 
 
A vida útil será atualizada sempre que o arrendamento for ajustado para garantir que o ativo de uso correto seja depreciado no prazo do arrendamento, como se fosse depreciado no arrendamento ativo.

> [!NOTE]
> Se você associar um ativo fixo a um arrendamento, os botões **Depreciação de ativo** e **Redução ao valor recuperável de arrendamento** serão desabilitados no arrendamento do Ativo. Você pode exibir as transações de depreciação de ativo e de deficiência de arrendamento de Ativos fixos. O botão **Transações de ativos** que abre um formulário de consulta também é desabilitado. Você também pode abrir o formulário de **Transações do ativo** nos Ativos fixos.  

As páginas **Ativos fixos** e **Registro de ativos fixos** exibirão a ID de arrendamento associada a um ativo fixo. Se um ativo fixo for associado a um arrendamento, a ID de arrendamento e a descrição do arrendamento serão exibidas na FastTab **Informações de arrendamento** na página **Ativos fixos**. Para registros de ativos fixos associados a registros de arrendamento, os campos **ID de Arrendamento**, **Descrição do arrendamento** e **Tipo de livro** exibirão informações para o registro de ativos fixos selecionado na FastTab **Informações de arrendamento**, para indicar que estão associados a um registro de arrendamento.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

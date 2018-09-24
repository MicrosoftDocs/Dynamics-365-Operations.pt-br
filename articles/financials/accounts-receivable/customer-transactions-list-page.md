---
title: "Página Lista de transações do cliente"
description: "Este tópico fornece informações sobre a página Lista de transações do cliente para o Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e828cb292ad48bb4690117b41589b25edcdf28bc
ms.contentlocale: pt-br
ms.lasthandoff: 08/31/2018

---

# <a name="customer-transaction-list-page"></a>Página Lista de transações do cliente

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Exibir liquidações

A guia **Exibir liquidações** no painel de ações fornece acesso rápido ao histórico de liquidações e mais informações sobre toda a transação de liquidação. Também é possível exibir transações adicionais relacionadas à transação selecionada, porque elas faziam parte da mesma liquidação ou porque são pagamentos criados no mesmo diário de pagamento.

1. Selecione **Contas a receber \> Clientes**.
2. Selecione um cliente com transações e, em seguida, selecione **Cliente \> Transações**.
3. Selecione uma transação para pesquisar.
4. Selecione a guia **Exibir liquidações** no painel de ações.

    A caixa de diálogo **Exibir liquidações** mostra a transação selecionada e todos os documentos que foram liquidados em relação a ela. Essa caixa de diálogo é semelhante à exibição do histórico de liquidações, mas inclui todos os documentos relacionados. 

5. Você pode executar várias tarefas nessa caixa de diálogo. Selecione um ou mais comprovantes e, em seguida, selecione um dos seguintes menus:

   - **Exibir contabilidade** – Todos os comprovantes relacionados aos documentos selecionados são exibidos. Selecione **Fechar** para fechar a caixa de diálogo.
   - **Exportar** – Exportar os comprovantes selecionados para o Microsoft Excel.
   - **Exibir pagamentos relacionados** – Todas as transações do diário de pagamento criadas no diário de pagamento relacionado ao documento selecionado são exibidas. Além disso, todas as liquidações relacionadas a esses pagamentos são exibidas. O rótulo desse menu também muda para **Exibir liquidações**. Selecione **Exibir liquidações** para mostrar apenas as transações que foram exibidas quando você abriu a caixa de diálogo **Exibir liquidações**.
    - **Liquidar transações** – Este menu aparece se o documento original selecionado não foi totalmente liquidado. Ao selecioná-lo, é exibida a caixa de diálogo **Liquidar transações**, na qual você pode selecionar transações para liquidação.
    - **Desfazer liquidações** – Este menu aparece se o documento original selecionado foi totalmente liquidado. Ao selecioná-lo, é exibida a caixa de diálogo **Desfazer liquidações**, na qual você pode desfazer as liquidações que foram feitos para esse documento.
    

